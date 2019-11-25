网页就是一个文本文件，文件扩展名一般为.html或.htm，俗称静态网页，可以直接在浏览器中预览；也可以是.asp、.aspx、.php或.jsp等，俗称为动态网页，需要服务器解析之后，浏览器才能够浏览。

从HTML5开始，对于文件的字符编码推荐使用UTF-8

在HTML5中，元素标记可以分为3个类型：不允许写结束标记，可以省略技术标记，开始标记和结束标记都可以省略。
1. 不允许写结束标记：area、base、br、col、command、embed、hr、img、input、keygen、link、meta、param、source、track、wbr
2. 可以省略结束标记的元素有：li、dt、dd、p、rt、rp、optgroup、option、colgroup、thead、tbody、tfoot、tr、td、th
3. 可以省略全部标记的元素有：html、head、body、colgroup、tbody
注：不允许写结束标记的元素指的是，不允许使用开始标记与结束标记将元素括起来的形式，只允许使用<元素/>的形式进行书写。可以省略全部标记的元素是指元素可以完全被省略。

<!-- TOC -->

- [布尔值:](#布尔值)
- [属性值:](#属性值)
- [<meta>网页元信息:](#meta网页元信息)
- [使用div和span](#使用div和span)
- [使用id和class](#使用id和class)
- [article 定义文章快](#article-定义文章快)
- [section 定义区块](#section-定义区块)
- [nav 定义导航栏](#nav-定义导航栏)
- [aside 定义边栏](#aside-定义边栏)
- [main 定义主要区域](#main-定义主要区域)
- [header 定义标题栏](#header-定义标题栏)
- [footer 定义页脚栏](#footer-定义页脚栏)

<!-- /TOC -->

### 布尔值:

当只写属性而不指定属性值时，表示属性值为true；如果属性值为false，可以不使用该属性值。
1. <!-- 只写属性，不写属性值，代表属性为true -->
	<input type="checkbox" checked>
2. <!-- 不写属性，代表属性为false -->
	<input type="checkbox">
3. <!-- 属性值=属性名，代表属性为true -->
	<input type="checkbox" checked="checked">
4. <!-- 属性值=空字符串，代表属性为true -->
	<input type="checkbox" checked="">


### 属性值:

属性值可以加双引号，也可以加单引号。当属性值不包括空字符串、<、>、=、单引号、双引号等字符时，属性值两边的引号可以省略。

### <meta>网页元信息:

使用<meta>标签可以定义网页的元信息，例如，定义针对搜索引擎的描述和关键词，一般网站都必须设置这两条元信息，以方便搜索引擎检索。

<meta>标签位于文档头部，<head>标签内。

<center><meta>标签属性列表</center>

|属性|说明|
|:---:|:---|
|content|必需的，定义与`http-equiv`或`name`属性相关的元信息|
|http-equiv|把`content`属性关联到`HTTP`头部。取值有：`content-type`、`expires`、`refresh`、`set-cookie`|
|name|把`content`属性关联到一个名称。取值包括：`author`、`description`、`keywords`、`generator`、`revised`等|
|scheme|定义用于翻译`content`属性值的格式|
|charset|定义文档的字符编码|

例如：

```html
<!-- 设置UTF-8编码 -->
<meta http-equiv="content-type" content="text/html";charset="UTF-8" />
<!-- 设置简体中文gb2312 -->
<meta http-equiv="content-type" content="text/html";charset="gb2312" />
<!-- 使用content-language属性定义页面语言的代码 -->
<meta http-equiv="content-language" content="zh-CN" />
<!-- 使用refresh属性值可以设置页面刷新时间或跳转页面，例如5秒钟之后刷新页面 -->
<meta http-equiv="refresh" content="5" />
<!-- 5秒之后跳转到百度首页 -->
<meta http-equiv="refresh" content="5";url="https://www.baidu.com/" />
<!-- 使用expires属性值设置网页缓存时间 -->
<meta http-equiv="expires" content="Sunday 20 October 2019 01:00 GMT" />
<!-- 设置页面不缓存 -->
<meta http-equiv="pragma" content="no-cache" />
<!-- 设置禁止搜索引擎检索 -->
<meta name="robots" content="none" />
```


定义文档视口:
<meta name="viewport" />

	标签的设置代码如下：

	<meta id="viewport" name="viewport" content="width=device-width; initial-scal=1.0 ; maximum-scale=1 ; user-scalable=no;" />

<meta name="viewport" />标签的设置说明

|属性|取值|说明|
|:---:|:---|:---|
|width|正整数或`device-width`|定义视口的宽度，单位为像素|
|height|正整数或`device-height`|定义视口的高度，单位为像素，一般不用|
|initial-scale|[0.0-10.0]|定义初始缩放值|
|minimum-scale|[0.0-10.0]|定义缩小最小比例，它必须小于或等于`maximum-scale`设置|
|maximum-scale|[0.0-10.0]|定义放大最大比例，它必须大于或等于`minimum-scale`设置|
|user-scalable|yes/no|定义是否允许用户手动缩放页面，默认值为yes|


### 使用div和span

div表示区块，没必要在<ul>外包裹一层<div>标签。

span元素可以直接对行内元素进行分组。


### 使用id和class

文档结构大部分是使用<div>标签来完成的，为了能够识别不同的结构，一般通过定义id或class给它们赋予额外的语义。

使用id表示页面上的元素时，id名必须是唯一的。id可以用来标识持久的结构性元素，例如主导航或内容区域；id还可以用来标识一次性元素，如某个链接或表单元素。

与id不同，同一个class可以应用于页面上任意数量的元素，因此class非常适合表示样式相同的对象。

class和id名称需要区分大小写，虽然CSS不区分大小写，但是在标签中是否区分大小写取决于HTML文档类型。


### article 定义文章快

article表示文章，用来标识页面中一块完整的、独立的、可以被转发的内容。

article内容块通常包含标题，放在header元素里面，有时还包括footer，定义附加信息。

article元素可以嵌套使用，原则上内容要与外层的内容向关联。


### section 定义区块

section表示区块，用于标识文档中的节，在页面上多对内容进行分区。例如：章节、页眉、页脚或文章中的其他部分。

	div元素也可以用来对页面进行分区，但section元素并非一个普通的容器。当一个容器需要被直接定义样式或通过脚本定义行为时，推荐使用div，而非section元素。
	div元素关注结构的独立性，而section元素关注内容的独立性，section元素包含的内容可以单独存储到数据库中，或输出到Word文档中。

section元素包含cite属性，用来定义section的URL。如果section摘自web，可以设置该属性。<section cite="http://music.baidu.com/">

	article和section都是HTML5新增的元素，他们都是用来区分不同的内容，用法也相似，从语义角度分析两者区分很大。

	article代表文章、页面或者应用程序中独立、完整的，可以被外部引用的内容。因为article是一段独立的内容，所以article通常包含header和footer结构。

	section用于对网站或者应用程序中页面上的内容进行分块。一个section通常由内容和标题组成。因此，需要包含一个标题，一般不用包含header或者footer结构。

	通常使用section元素为那些有标题的内容进行分段，类似文章分段操作。相邻的section内容应该是相关的，而不像article之间相互独立。

	使用HTML5大纲工具（http://gsnedders.html5.org/outliner/）来检查页面中是否没有标题的section，如果使用该工具进行检查后，发现某个section的说明中有“untitiled section”（没有标题的section）文字，这个section就有可能使用不当，但是nav元素和aside元素没有标题是合理的。


### nav 定义导航栏

nav表示导航条，用来标识页面导航的链接组。一个页面中可以拥有多个nav，作为页面整体或不同部分的导航。应用场景如下：

1. 主菜单导航。一般网站都会设置有不同层级的导航条，其作用是在站内快速切换，如主菜单、置顶戴航条、主导航图标等。
2. 侧边栏导航。现在主流博客网站及商品网站上都有侧边栏导航，其作用是将页面从当前文章或当前商品跳转到相关文章或相关商品的页面上去。
3. 页内导航。就是业内锚点连接，其作用是在本页面几个重要组成部分之间进行跳转。
4. 翻页操作。翻页操作是指在多个页面的前后页或博客网站的前后篇文章滚动。

```html
<nav draggable="true">
	<a href="#">首页</a>
	<a href="#">图书</a>
	<a href="#">论坛</a>
</nav>
```

并不是所有的链接组都要被放进nav里面，只需要将主要的、基本的链接组放进nav元素中即可。

	不要用menu元素代替nav元素。menu主要用在一系列交互命令的菜单，如快捷菜单。


### aside 定义边栏

aside表示侧边，用来标识所处内容之外的内容。aside内容应该与所处的附近内容相关。例如：当前页面或文章的附属信息部分，他可以包括与当前页面或主要页面相关的引用、侧边广告、导航条，以及其他类型的有别于主要内容的部分。

aside元素主要有两种用法：

1. 作为主题内容的附属信息部分，包含在article中，aside内容可以是与当前内容有关的参考资料、名词解释等。
2. 作为页面或站点辅助功能，在article之外使用。最典型的是侧边栏，其中内容可以是友情链接、最新文章列表、最新评论列表、历史存档、日历等。

下面代码是使用aside元素为个人博客添加一个友情链接辅助板块。

```html
<aside>
	<nave>
		<h2>友情链接</h2>
			<ul>
				<li><a href="#">网站1</a></li>
				<li><a href="#">网站2</a></li>
				<li><a href="#">网站3</a></li>
			</ul>
		
	</nave>
</aside>
```


### main 定义主要区域

main表示主要，用来标识网页中的主要内容。main内容对于文档来说应该是唯一的，它不应包含在网页中重复出现的内容，如侧栏、导航栏、版权信息、站点标志或搜索表单等。

简单来说，在一个页面中，不能出现一个以上的main元素。main元素不能被包裹在article、aside、footer、header或nav中。

由于main元素不对页面内容进行分区或分块，所以不会对网页大纲产生影响。

使用main元素包裹页面主要区域，这样更有利于网页内容的语义分区，同时搜索引擎也能主动抓取主要信息，避免被次要信息干扰。


### header 定义标题栏

header表示页眉，用来标识页面标题栏。header元素是一种具有引导和导航作用的结构元素，通常用来放置整个页面，或者一个内容块的标题。

header也可以包含其他内容，如数据表格、表单或相关的LOGO信息，一般整个页面的标题应该放在页面的前面。

 在HTML5中，header内部可以包括h1~h6元素，也可以包括hgroup、table、form、nav等元素，只要应该先是在头部区域的标签，都可以包含在header元素中。


### footer 定义页脚栏

footer表示脚注，用来标识文档或节的页脚。footer元素应当含有其包含元素的信息。例如，也叫通常包含文档的作者、版权信息、使用条款链接、联系信息等。

同一个页面，可以使用多个footer元素。同时，可以为article或section内容添加footer。

下面示例分别在article、section和body区域内添加footer信息。

```html
<header>
	<h1>网页标题内容</h1>
</header>
<article>
	<h2>文章标题</h2>
	<p>文章标题内容</p>
	<footer>注释</footer>
</article>
<section>
	<h2>段落标题</h2>
	<p>正文</p>
	<footer>段落标记</footer>
</section>
<footer>网页版权信息</footer>
```
