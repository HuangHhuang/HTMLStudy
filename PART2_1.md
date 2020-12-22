# PART2_1

### 1.HTML 与 XHTML区别

​	  DOCTYPE文档及编码
​      元素大小写 
​      属性布尔值
​      属性引号
​      图片的alt属性
​      单标签写法
​      双标签闭合

### 2.strong与b、em与i

表现形态都是 文本加粗  和  文本斜体

区别：是否具备语义化

使用不同形式的标签可以减少class的使用

### 3.引用标签

blockquote  :  引用大段的段落解释
q  :  引用小段的短语解释
abbr  :  缩写或首字母缩略词
address  :  引用文档地址信息
cite  :  引用著作的标题

    “死而后已”一语出自诸葛亮《出师表》：
    <blockquote>“凡事如此，难可逆见，臣鞠躬尽瘁，死而后已，至于成败利钝，非臣之明所能见能逆睹也。”</blockquote>
    WWF的目标是：<q>构建人与自然和谐共存的世界。</q>
    <br>
    <abbr title="World Health Organization">WHQ</abbr>成立于1948年。
    <address>网易北京公司</address>
    <cite>资治通鉴</cite>由北宋司马光主编的一部多卷本编年体史书
### 4.iframe标签

可以引入其他的html到当前html中显示。

主要是利用iframe的属性进行样式的调节。

iframe元素会创建包含另外一个文档的内联框架（即行内框架）。

|    属性     |             含义             |
| :---------: | :--------------------------: |
| frameborder |  规定是否显示框架周围的边框  |
|    width    |       定义iframe的宽度       |
|   height    |       定义iframe的高度       |
|  scrolling  | 规定是否在iframe中显示滚动条 |
|     src     |   规定在iframe中引入的url    |
|   srcdoc    | 规定在iframe中显示的页面内容 |

应用场景：数据传输、共享代码，局部刷新、第三方介入等

### 5.br 与 wbr

br 就是换行、  wbr 就是软换行（在指定时机进行换行）

### 6.pre 与 code

针对程序中软件代码的显示效果。

使用方法

```html
<pre>
	<code>
	...
	</code>
</pre>
```



### 7.map 与 object

给特殊图形添加链接，area能添加的热区形状：矩形、圆形、多边形。

### 8.embed 与  object

给flash和一些插件进行渲染操作的标签。

### 9.audio 与 video

引入音频与视频的标签。属于H5的功能。

controls：显示控件

loop：循环播放

autoplay：自动播放

source：备选视频

例：

```html
<audio src="./img/johann_sebastian_bach_air.mp3" controls loop autoplay></audio>
    <video src="./img/Intermission-Walk-in_512kb.mp4" controls></video>

    <video controls>
        <source src="./img/Intermission-Walk-in.ogv"></source>
        <source src="./img/Intermission-Walk-in_512kb.mp4"></source>
    </video>
```

### 10.文字注解

ruby  、 rt 这样一个组合

bdo : 更改文字顺序 

​	默认dir="ltr"

​	倒叙dir="rlt"

例

```html
	span{direction: rtl; unicode-bidi: bidi-override;}
			//通过css方式
	
	<ruby>
        寒<rt>han</rt>
    </ruby>
    <p>
        <bdo dir="rtl">爱神的箭</bdo>
    </p>
    <p>
        <span>爱神的箭</span>
    </p>
```

### 11.link扩展学习

添加网址标题栏前的小图标：
    <link rel="icon" type="/image/x-icon" href="http://www.mobiletrain.org/favicon.ico">
    DNS预解析：
    <link rel="dns-prefetch" href="//static.360buyimg.com">

加在head里面

### 12.meta扩展学习

meta添加一些辅助信息。

```html
<meta name="description" content="大连美团网精选大连美食餐厅,酒店预订,电影票,旅游景点,外卖订餐,大连团购信息,您可查询商家评价店铺信息。大连生活,下载美团官方APP ,吃喝玩乐1折起。">
	//描述信息
    <meta name="keywords" content="大连美食,大连酒店,大连团购">
    <meta name="renderer" content="webkit">
    //针对渲染双内核
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    //让ie浏览器以最高版本进行渲染
    <meta http-equiv="refresh" content="3" url="">
    //过指定秒数刷新
    <meta http-equiv="expires" content="Wed, 20 Jun 2019 22:33:00 GMT">
    //在规定时间内走缓存
```

### 13.Html5新的语义化标签

    header : 页眉
    footer : 页脚
    main : 主体
    hgroup : 标题组合
    nav : 导航
注：header、footer、main 在一个网页中只能出现一次。

    article : 独立的内容
    aside : 辅助信息的内容
    section : 区域
    figure : 描述图像或视频
    figcaption : 描述图像或视频的标题部分
    datalist : 选项列表
    details / summary : 文档细节 / 文档标题
    progress / meter : 定义进度条 / 定义度量范围
    time : 定义日期或时间
    mark : 带有记号的文本
```html
<header>
        <hgroup>
            <h1>主标题</h1>
            <h2>副标题</h2>
        </hgroup>
        <nav>
            <ul>
                <li>首页</li>
                <li>论坛</li>
                <li>关于</li>
            </ul>
        </nav>
    </header>
    <main>
        <article>
            <section>
                <input type="text" list="elemt">
                <datalist id="elemt">
                    <option value="a"></option>
                    <option value="abc"></option>
                    <option value="adffd"></option>
                    <option value="hsdkfksj"></option>
                    <option value="asdfhhskfh"></option>
                </datalist>
            </section>
            <section>
                <details>
                    <summary>超文本标记语言</summary>
                    <p>HTML</p>
                </details>
                <progress min="0" max="10" value="5"></progress>
                <meter min="0" max="100" value="5" low="10" high="60"></meter>
                <p><time title="2.14">情人节</time>快乐！</p>
                <p><mark>情人节</mark>快乐！</p>
            </section>
            <section>
                <ul>
                    <li>
                        <figure>
                            <img src="./img/youku.jpg" alt="">
                            <figcaption>
                                    新水果篮子❤️高甜   
                                    <br>
                                    十二生肖恋上美少女！
                            </figcaption>
                        </figure>
                    </li>
                </ul>
            </section>
        </article>
        <aside></aside>
    </main>
    <footer></footer>
```

### 14.表格扩展学习

    添加单线 : border-collapse : collapse
    隐藏空单元 : empty-cells : hide
    斜线分类 : border / rotate
    列分组 : colgroup / col

### 15.表单扩展学习

美化表单控件： 1. label + :checked    2. position + opacity

```html
<style>
        <-- 利用label标签加：check 1 -->
        /* label input{display: none;}
        label div{ width: 28px; height: 28px; background: url(./img/checkbox.png) 0 -28px ;}
        label input:checked + div{ background-position: 0 0;} */
    
        <-- 利用label标签加：check 2 -->
        /* label input{display:none}
        label div{width: 86px; height: 34px; background: url(./img/upload.png);} */
    
        /* 利用透明度为上传按钮添加样式 */
        .upload{ width: 86px; height: 34px; position: relative;}
        .upload div{width: 100%; height: 100%; background: url(./img/upload.png);}
        .upload input{ width: 100%; height: 100%; position: absolute; opacity: 0; left: 0; top: 0;}
    </style>
</head>
<body>
    /* 利用label标签加：check 1*/
    <!-- <label>
        <input type="checkbox">
        <div></div>
    </label> -->
    
    /* 利用label标签加：check 2*/
    <!-- <label>
        <input type="file">
        <div></div>
    </label> -->
    
    <div class="upload">
        <input type="file">
        <div></div>
    </div>
</body>
```

#####  新的input控件

​	   email  :  电子邮件地址输入框
​	   url  :  网址输入框
​	   number  :  数值输入框
​	   range  :  滑动条
​	   date / month / week  :  日期控件	
​	   search  :  搜索框
​	   color  :  颜色控件
​	   tel  :  电话号码输入框  ( 在移动端会默认调起数字键盘 )
 	   time  :  时间控件

##### 表单属性

​	   autocomplete  :  自动完成  默认 on  /  off
​	   autofocus  :  获取焦点
​	   required  :  不能为空
​	   pattern  :  正则验证

​	   method  :  数据传输方式
​	   enctype  :  数据传输类型
​	   name / value  :  数据的键值对

##### 扩展标签

​	   fieldset  :  表单内元素分组 
​	   legend  :  为fieldset元素定义标题
​	   optgroup  :  定义选项组

### 16.BFC规范

​		Formatting context（格式化上下文）是W3CCSS21规范中的一个概念它是页面中的一块渲染区域，并且有一套渲染规则，它决定了其子元素将如何定位，以及和其他元素的关系和相互作用。
​		BFC即 Block Formatting Contexts（块级格式化上下文），它属于上述中的其中—种规范。具有BFC特性的元素可以看作是隔离了的独立容器，容器里面的元素不会在布局上影响到外面的元素，并且BFC具有普通容器所没有的一些特性。

​		简单来说，就是触发BFC规范的元素，可以形成一个独立的容器。不受外界的影响，从而解决一些布局的问题。

触发的样式：

* 浮动元素：foat除none以外的值

* 绝对定位元素：position（ absolute、fxed）

* display为 inline- block、 table- cells. flex

* overflow除了 visible以外的值（ hidden、auto、 scroll）

BFC的特性及应用

* 解决margin叠加问题：给元素外面加个div容器再给div设置overflow:hidden属性

* 解决margin传递问题：直接给不需要受影响的加overflow:hidden属性

* 解决浮动问题：直接给不需要受影响的加overflow:hidden属性

* 解决覆盖问题（达到一列固定，一列自适应效果）：直接给不需要受影响的加overflow:hidden属性



