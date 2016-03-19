---
title: laravel手动删除migration文件
layout: post
guid: urn:uuid:f491f6d0-cfeb-0133-e7cd-63916fd8f332
tags:
  - Laravel
---

### 症状

在创建migration文件的时候，不小心创建错了，然后就删除掉并重新创建了一个同名的文件的migration文件，发现在执行

```
php artisan migrate:rollback
```

这条命令的时候，提示

```
failed to open stream: No such file or directory
```

### 原因

因为是 `同名` 的migration文件，所以在第二次创建的时候，

```
vendor\composer\autoload_classmap.php
```

文件里的发现已经存在了这个自动加载项了，所以就不会去重新添加或者更新它为新的migration文件名。

因此出现执行命令的时候找不到类文件的错误！

### 解决方案

手动更改

```
vendor\composer\autoload_classmap.php
```

文件里的对应的migration文件的类记录。

### 拓展

搜索了下，如何删除migration文件，找到了[这篇文章][1]。

大意是分3步：

1.删除

```
database/migrations/xxx.php
```

2.重置composer 自动加载文件，执行命令

```
php composer dump-autoload
```

3.如果已经执行过这条migration文件，那么还得去数据库 `migrations` 表里删除对应xxx.php名字的记录。



[1]: https://milostrickovic.wordpress.com/2014/01/28/laravel-manually-delete-migration/