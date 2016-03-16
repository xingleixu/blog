---
title: markdown标签
layout: post
guid: urn:uuid:83015b80-cb3c-0133-e7c9-63916fd8f332
tags:
  - markdown
---

<div class="bs-callout bs-callout-info">
	<h4>无序列表/有序列表</h4><p>
<code>-</code> 表示无序列表，数字加 <code>.</code> 表示有序列表,如 <code>1.</code>。用 <kbd>Tab</kbd> 缩进表示子级列表。
</p>
</div>

- 无序列表
	- 列表1
	- 列表2
	- 列表3

- 有序列表
	1. 列表1
	2. 列表2
	3. 列表3

<br/>

	- 无序列表
		- 列表1
		- 列表2
		- 列表3

	- 有序列表
		1. 列表1
		2. 列表2
		3. 列表3

<div class="bs-callout bs-callout-info">
	<h4>水平尺</h4>
<p>
<code>***</code> 表示水平尺
</p>
</div>


***

<div class="bs-callout bs-callout-info">
	<h4>标题</h4>
<p>
文字前加 <code>#</code> 表示标题，几级标题就几个<code>#</code>，如
<code>###测试标题</code> 相当于 &lt;h3&gt; 
</p>
</div>

# 标题1

## 标题2

### 标题3

#### 标题4

##### 标题5

###### 标题6


	# 标题1

	## 标题2

	### 标题3

	#### 标题4

	##### 标题5

	###### 标题6

<div class="bs-callout bs-callout-info">
	<h4>超链接和图片</h4>
<p>
超链接用 <code>[链接名称](链接网址 "链接提示")</code> 的形式来表达，这里的 <code>"链接提示"</code> 是可以省略的。
</p>
</div>
比如以下两个超链接：

[百度](http://www.baidu.com) `[百度](http://www.baidu.com)`

[谷歌](http://www.google.com "这是谷歌") `[谷歌](http://www.google.com "这是谷歌")`

超链接也支持索引的写法如

	[百度][1]和[谷歌][2]都是搜索引擎公司。
	[1]:http://www.baidu.com "链接提示"
	[2]:http:www.google.com "链接提示"
	同理后面的“链接提示”也可以省略。

链接后面的索引可以是任意字母，也可以省略，省略的话，就跟链接名是一样的。

	[百度][baidu]和[谷歌][]都是搜索引擎公司。
	[baidu]:http://www.baidu.com "链接提示"
	[谷歌]:http:www.google.com "链接提示"

**在所有超链接前面加上一个 `!` 就表示图片链接。**
如 `![图片名称](图片地址)`

<div class="bs-callout bs-callout-info">
	<h4>粗体和斜体</h4>
<p>
<code>**</code> 表示加粗， <code>*</code> 表示倾斜，<code>***</code> 表示加粗倾斜。
</p>
</div>

这是一个**加粗**的标记。

这是一个*倾斜*的标记。

这是一个***加粗倾斜***的标记。


	这是一个**加粗**的标记。

	这是一个*倾斜*的标记。

	这是一个***加粗倾斜***的标记。

<div class="bs-callout bs-callout-info">
	<h4>代码</h4>
<p>
用 <code>`</code> 标签包裹文字实现代码效果。

在段落前按 <kbd>Tab</kbd> 或者四个空格缩进。

或者用<code>```</code> 标签包裹，也可以用	<code>{ % highlight javascript % }</code> <code> { % endhighlight % } </code> 标签包裹。其中 <code>javascript</code> 是语言类型，可以自己指定或者省略不写。
</p>
</div>



这是一个简单的 `代码` 效果。
下面是一大段代码效果：

{% highlight javascript %}
import {x, y} as p from 'point';
const ANSWER = 42;

class Car extends Vehicle {
  constructor(speed, cost) {
    super(speed);

    var c = Symbol('cost');
    this[c] = cost;

    this.intro = `This is a car runs at
      ${speed}.`;
  }
}

for (let num of [1, 2, 3]) {
  console.log(num + 0b111110111);
}

function $initHighlight(block, flags) {
  try {
    if (block.className.search(/\bno\-highlight\b/) != -1)
      return processBlock(block.function, true, 0x0F) + ' class=""';
  } catch (e) {
    /* handle exception */
    var e4x =
        <div>Example
            <p>1234</p></div>;
  }
  for (var i = 0 / 2; i < classes.length; i++) { // "0 / 2" should not be parsed as regexp
    if (checkCondition(classes[i]) === undefined)
      return /\d+[\s/]/g;
  }
  console.log(Array.every(classes, Boolean));
}

export  $initHighlight;
{% endhighlight %}

<div class="bs-callout bs-callout-info">
	<h4>引用</h4>
<p>
用 <code>`</code> 标签包裹文字实现代码效果。

在段落前添加 <code>></code> 符号表示引用,多次添加 <code>></code> 符号实现引用多级嵌套。
<mark>注意,github 的markdown解析器不支持多级引用 </mark>
</p>
</div>


> 这是一段应用的内容。
> > 这是一段子引用


	> 这是一段应用的内容。
	>  > 这是一段子引用
	
<div class="bs-callout bs-callout-info">
	<h4>表格</h4>
<p>
<mark>注意,原生的markdown语法并不支持表格。 </mark>
</p>
</div>


| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |


	| Tables        | Are           | Cool  |
	| ------------- |:-------------:| -----:|
	| col 3 is      | right-aligned | $1600 |
	| col 2 is      | centered      |   $12 |
	| zebra stripes | are neat      |    $1 |


<div class="bs-callout bs-callout-danger">
	<h4>补充Bootstrap html 标签</h4>
<p>
<mark>注意,以下标签用法不属于markdown，仅作为排版的补充而设置的HTML标签和CSS和样式。</mark>
</p>
</div>


### 键盘/高亮/缩写/上下标/删除线

- 键盘： `<kbd>` 

- 高亮： `<mark>` 

- 缩写： `<abbr>` 

- 上下标： `<sup>` `<sub>`

- 缩写： `<del>` 


To switch directories, type <kbd>cd</kbd> followed by the name of the directory.
To edit settings, press <kbd><kbd>ctrl</kbd> + <kbd>,</kbd></kbd> ,

这是一段带有 <mark>高亮</mark> 的文字。

<abbr title="HyperText Markup Language">HTML</abbr>是HyperText Markup Language的缩写。

这是<sup>[上标]</sup>效果，这是<sub>[下标]</sub>效果。

<del>这是删除线效果</del>

Markdown中用 `~~` 标签表示删除线，由于有些编辑器没有支持，所以这里没有列出来。如：~~这是Markdown的写法~~。

	To switch directories, type <kbd>cd</kbd> followed by the name of the directory.<br>
	To edit settings, press <kbd><kbd>ctrl</kbd> + <kbd>,</kbd></kbd>

	这是一段带有<mark>高亮</mark>的文字。

	<abbr title="HyperText Markup Language">HTML</abbr>是HyperText Markup Language的缩写。


	这是<sup>[上标]</sup>效果，这是<sub>[下标]</sub>效果。

	<del>这是删除线效果</del>

	Markdown中用`~~`标签表示删除线，由于有些编辑器没有支持，所以这里没有列出来。如：~~这是Markdown的写法~~。

### 提示/警告/危险 卡片效果和对应的HTML CSS

<div class="bs-callout bs-callout-info">
    <h4>这是标题</h4>
    <p>这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明</p>
</div>

	<div class="bs-callout bs-callout-info">
    	<h4>这是标题</h4>
    	<p>这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明</p>
	</div>

<div class="bs-callout bs-callout-warning">
    <h4>这是标题</h4>
    <p>这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明</p>
</div>

	<div class="bs-callout bs-callout-warning">
    	<h4>这是标题</h4>
    	<p>这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明</p>
	</div>

<div class="bs-callout bs-callout-danger">
    <h4>这是标题</h4>
    <p>这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明</p>
</div>

	<div class="bs-callout bs-callout-danger">
    	<h4>这是标题</h4>
    	<p>这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明这是一内容说明</p>
	</div>

<p class="bg-primary">Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
<p class="bg-success">Duis mollis, est non commodo luctus, nisi erat porttitor ligula.</p>
<p class="bg-info">Maecenas sed diam eget risus varius blandit sit amet non magna.</p>
<p class="bg-warning">Etiam porta sem malesuada magna mollis euismod.</p>
<p class="bg-danger">Donec ullamcorper nulla non metus auctor fringilla.</p>

    <p class="bg-primary">Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
    <p class="bg-success">Duis mollis, est non commodo luctus, nisi erat porttitor ligula.</p>
    <p class="bg-info">Maecenas sed diam eget risus varius blandit sit amet non magna.</p>
    <p class="bg-warning">Etiam porta sem malesuada magna mollis euismod.</p>
    <p class="bg-danger">Donec ullamcorper nulla non metus auctor fringilla.</p>
