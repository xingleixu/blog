---
title: 如何判断php://input输入文件的MIME类型
layout: post
guid: urn:uuid:bb605c70-0228-0134-e7cf-63916fd8f332
tags:
  - php://input
  - MIME
---

一直没找到合适的方法，看了stackoverflow的答案才恍然大悟。
其实都一样，关键是文件先接收过来，然后再判断就是了。

#### 保存临时文件

````
$temp_file = tempnam(sys_get_temp_dir(), 'Tux');  
file_put_contents($temp_file , $source); 
```

#### 判断

```
$finfo = finfo_open(FILEINFO_MIME_TYPE);  
$content_type = finfo_file($finfo, $temp_file);
```
