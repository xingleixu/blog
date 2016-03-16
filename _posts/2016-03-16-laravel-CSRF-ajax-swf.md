---
title: Laravel用ajax或swf向服务器POST数据出现500错误
layout: post
guid: urn:uuid:5b87e660-cda7-0133-e7cb-63916fd8f332
tags:
  - Laravel
---

## 症状
Laravel用Ajax或swf向服务器POST数据出现500错误。

## 原因
Laravel5默认中间件里包含CSRF的验证。

也就说，所有的POST提交的表单都需要包含 `csrf_token`。

Ajax或swf向服务器提交数据的时候，构造数据的时候是没有带上 `csrf_token` 的数据的。

## 解决
1. 构造 `csrf_token` 发送
	- 如果是Ajax,可以将数据生成在某个网页的隐藏节点里，然后用JS脚本去读取，并构造发送，可以参考[这里][1]，或者参考[Laravel Ajax 500 Internal Server error – 5+ Reasons – Quick Fix][2]这篇文章。

	- swf跟Ajax道理一样，建议可以在构造swf结构的时候，以swf参数属性的方式传至给swf。如果是swf自发POST数据就无能为力了。

2. 禁用 `csrf_token`
	- 全局禁用方法参考[这篇文章][3]，但是考虑安全因素这里 <mark>并不推荐</mark>。
	
	- 可以在 `app\Http\Middleware\VerifyCsrfToken.php` 文件里定义的 `VerifyCsrfToken` 类里的 `$except` 属性数组里添加例外的路由，以下代码中的两个路由 `/album/upload` `/album/replace`,将取消CSRF的验证。

```
namespace App\Http\Middleware;

use Illuminate\Foundation\Http\Middleware\VerifyCsrfToken as BaseVerifier;

class VerifyCsrfToken extends BaseVerifier
{
    /**
     * The URIs that should be excluded from CSRF verification.
     *
     * @var array
     */
    protected $except = [
        '/album/upload',
        '/album/replace'
    ];
}
```


[1]:http://stackoverflow.com/questions/32256969/laravel-5-ajax-post-500-internal-server-error

[2]:http://abbasharoon.me/how-to-fix-laravel-ajax-500-internal-server-error/

[3]:http://www.cnblogs.com/HD/p/4555369.html
