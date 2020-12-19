# CSS

#### CSS基本语法

选择器 { 属性1 : 值1 ; 属性2 : 值2 }

    width : 宽
    height : 高
    background-color : 背景色
    
    长度单位 : 
        1. px -> 像素
        2. % -> 百分比    
            外容器1 -> 600px  当前容器 50% -> 300px
            外容器2 -> 400px  当前容器 50% -> 200px


#### CSS样式的引入方式

1. 内联样式
       style属性

2. 内部样式
    style标签
    区别：
        内部样式的代码可以复用、复合W3C的规范标准，进行让结构和样式分开处理。    
3. 外部样式
    引入一个单独的CSS文件，name.css

    通过link标签引入外部资源，rel属性指定资源跟页面的关系，href属性资源的地址。
    通过@import方式引入外部样式 ( 这种方式有很多问题，不建议使用 )

```
link的rel属性： http://www.w3school.com.cn/tags/att_link_rel.asp

link与@import区别：https://www.cnblogs.com/my--sunshine/p/6872224.html
```

#### css中的颜色表示法

1. 单词表示法 : red blue green yellow ...

2. 十六进制表示法：#000000   #ffffff
    0 1 2 3 4 5 6 7 8 9 a b c d e f
    
3. rgb三原色表示法：rgb(255,255,255);
    取值范围 0 ~ 255

#### CSS背景样式

* background-color 背景色
*  background-image 背景图
  * url(背景地址)
  * 默认：会水平垂直都铺满背景图
* background-repeat 平铺方式
  * repeat-x   x轴平铺
  * repeat-y   y轴平铺
  * repeat ( x , y 都进行平铺，默认值 )
  * no-repeat  都不平铺
*   background-position : 背景位置
  * x y : number(px、%) | 单词
  * x : left、center、right
  * y : top、center、bottom
*   background-attachment : 背景图随滚动条移动的方式
  * scroll : 默认值  ( 背景位置是按照当前元素进行偏移的 )
  * fixed ( 背景位置是按照浏览器进行偏移的 )

#### CSS边框样式

* border-style : 边框样式
  * solid：实线
  * dashed：虚线
  * dotted：点线
* border-width : 边框大小
  * px ...
* border-color : 边框颜色
  * red #ff0000 ...

边框也可以针对某一天边进行单独设置 : border-left-style : 中间是方向 left、right、top、bottom

颜色：透明颜色 transparent

#### CSS文字样式

* font-family : 字体类型
  * 英文、中文
  * 衬线体、非衬线体
  *  注意点：
                1.多个字体类型的设置目的（备选）
                2.字体名称里带有空格的需要加引号
* font-size : 字体大小
  * 默认 : 16px
  * 写法 : number(px) | 单词 ( small large ... 不推荐使用)

* font-weight : 字体粗细
  * 模式： 正常( normal )   加粗 ( bold )
  * 写法：单词(normal、bold)   |  number ( 100 200 .....  900 , 100到500都是正常的，600都900都是加粗的 )  
* font-style : 字体样式
  * 模式： 正常 ( normal )   斜体 ( italic )
  * 写法：单词 (  normal 、 italic )
    * 注：oblique也是表示斜体，用的比较少，一般了解即可。
  * 区别：1.italic 带有倾斜属性的字体的才可以设置倾斜操作。
                  2.oblique 没有倾斜属性的字体也可以设置倾斜操作。



#### CSS段落样式

* text-decoration：文本装饰
  * 下划线 : underline
  * 删除线 :line-through
  * 上划线 : overline
  * 不添加任何装饰 : none
  * 注：添加多个文本修饰：line-through underline overline（用空格隔开）
* text-transform：文本大小写 （ 针对英文段落 ）
  * 小写：lowercase
  * 大写：uppercase
  * 只针对首字母大写：capitalize
* text-indent : 文本缩进
  * 首行缩进
  * em单位：相对单位，1em永远都是跟字体大小相同
* text-align : 文本对齐方式
  * 对齐方式 : left 、right、center、justify（两端点对齐）
* line-height : 定义行高
  * 什么是行高，一行文字的高度，上边距和下边距的等价关系。
  * 默认行高：不是固定值，而是变化的。根据当前字体的大小再不断的变化。
  * 取值：1. number( px )   |  scale ( 比例值 , 跟文字大小成比例的，没有单位 )
* letter-spacing : 字之间的间距
* word-spacing : 词之间的间距  ( 针对英文段落的 )
* 英文和数字不自动折行的问题：
  * word-break : break-all; (非常强烈的折行)
  * word-wrap : break-word;(不是那么强烈的折行 ，会产生一些空白区域)  

#### CSS复合样式

​		复合的写法，是通过空格的方式实现的。复合写法有的是不需要关心顺序，例如background、border；有的是需要关心顺序，例如font。

1. background : red url() repeat 0 0;

2. border : 1px red solid;

3. font :

   注：最少要有两个值 size family，且这两个值必须排在最后，size后可加/line-height表示行高

   ​			weight style size family  √

   ​			style weight size family  √

   ​			weight style size/line-height family √

   注：如果非要混合去写的话，那么要先写复合样式，再写单一样式，这样样式才不会被覆盖掉。



#### CSS选择器

1. ID选择器

   #elem{}      id="elem"

   注：

   1. ID是唯一值，在一个页面中只能出现一次，出现多次是不符合规范的。

   2. 命名的规范，由字母、下划线、中划线、字母（并且第一个不能是数字）

   3. 驼峰写法 : searchButton (小驼峰)  SearchButton (大驼峰)  searchSmallButton

      短线写法：search-small-button

      下划线写法：search_small_button

   快捷键：div#ID名称+tab

2. CLASS选择器

   .elem{}      class="elem"

   注：

   1. class选择器是可以复用的
   2. 可以添加多个class样式
   3. 多个样式时，样式的优先级根据css决定（写在后面的优先级高），而不是class属性中的顺序。
   4. 标签+类的写法（例如：只想要p标签中的class生效那就p.class名。

3. 标签选择器(TAG选择器)

   ```html
   div{}          <div></div>
   ```

   使用的场景：

   	1. 去掉某些标签的默认样式时
    	2. 复杂的选择器中，如 层次选择器

4. 群组选择器(分组选择器)

   可以通过逗号的方式，给多个不同的选择器添加统一的CSS样式，来达到代码的复用.

5. 通配选择器

   *{  } ->  div,ul,li,p,h1,h2....{} 

   注：尽量避免使用通配选择器，因为会给所有的标签添加样式，慎用。

   使用的场景：

               1. 去掉所有标签的默认样式时

6. 层次选择器

   后代  M N { }

   父子  M > N { }

   兄弟  M ~ N { }  当前M下面的所有兄弟N标签

   相邻  M + N { }  当前M下面相邻的N标签

7. 属性选择器

   M[attr] {}

   = : 完全匹配

   *= : 部分匹配

   ^= : 起始匹配

   $= : 结束匹配

   ```
   [][][] : 组合匹配
   ```

8. 伪类选择器

   M:伪类{}

   :link       访问前的样式    ( 只能添加给a标签 )

   :visited    访问后的样式    ( 只能添加给a标签 )

   :hover      鼠标移入时的样式  (可以添加给所有的标签)

   :active     鼠标按下时的样式  (可以添加给所有的标签)

   注：

   ​	一般的网站都只设置

   ​	a{}   ( link visited active )    a:hover{}

   

   :after、:before    通过伪类的方式给元素添加一段文本内容，使用content属性

   :checked、:disabled 、:focus 都是针对表单元素的

   

   结构性伪类选择器

   ​	nth-of-type()   nth-child()

   ​	角标是从1开始的，1表示第一项，2表示第二项 | n值 表示从0到无穷大

   ​	first-of-type

   ​	last-of-type

   ​	only-of-type

   

   ​	nth-of-type()和nth-child()之间的区别

   ​			type : 类型

   ​			child : 孩子

9. CSS继承

   文字相关的样式可以被继承
   	布局相关的样式不能被继承 ( 默认是不能继承的，但是可以设置继承属性 inherit 值 )

10. CSS优先级

    1. 相同样式优先级

       当设置相同样式时，后面的优先级比较高，但不建议出现重复设置样式的情况。

    2. 内部样式与外部样式

       内部样式与外部样式优先级相同，如果都设置了相同样式，那么后写的引入方式优先级高。

    3. 单一样式优先级

       style行间 >id>class>tag>*>继承

       注：

       style行间	权重 1000

       id				   权重 100

       class			权重 10

       tag				权重 1

    4. !important

       提升样式优先级，非规范方式，不建议使用。( 不能针对继承的属性进行优先级的提升 )

    5. 标签+类与单类

       标签+类 > 单类

    6. 群组优先级

       群组选择器与单一选择器的优先级相同，靠后写的优先级高。

    7. 层次优先级

       1. 权重比较

          ul li .box p input{}   1 + 1 + 10 + 1 + 1

          .hello span #elem{}    10 + 1 + 100

       2. 约分比较

          ul li .box p input{}    li p input{}

          .hello span #elem{}      #elem{}

11. CSS盒子模型

    组成 : content -> padding -> border -> margin

    ​    			物品			填充物		包装盒  		盒之间的间距

    content : 内容区域  width和height组成的

    padding : 内边距(内填充)

    ​	只写一个值： 30px (上下左右)

    ​	写两个值 : 30px 40px ( 上下、左右 )

    ​	写四个值 : 30px 40px 50px 60px（上、右、下、左）

    单一样式只能写一个值：

    ​	padding-left

    ​	padding-right

    ​	padding-top

    ​	padding-bottom

    margin : 外边距(外填充)

    ​	只写一个值： 30px (上下左右)

    ​	写两个值 : 30px 40px ( 上下、左右 )

    ​	写四个值 : 30px 40px 50px 60px（上、右、下、左）

    单一样式只能写一个值：

    ​	margin-left

    ​	margin-right

    ​	margin-top

    ​	margin-bottom

    注：

    1. 背景色填充到margin以内的区域（不包括margin区域）
    2. 文字在content区域添加
    3. padding不能为负数，而margin可以为负数

    box-sizing:

    盒尺寸，可以改变盒子模型的展示形态。

    默认值： content-box :  width、height -> content

    border-box : width、height -> content padding border

    使用的场景：

    1. 不用再去计算一些值
    2. 解决一些100%的问题

    盒子模型的一些问题：

    1. margin叠加问题，出现在上下margin同时存在的时候。会取上下中值较大的作为叠加的值。
    2. margin传递问题，出现在嵌套的结构中，只是针对margin-top的问题。

    * 扩展：
      1. margin左右自适应是可以的 ，但是上下自适应是不行的。( 如果想实现上下自适应的话，需要在第二大部分来进行学习 )
      2. width、height不设置的时候，对盒子模型的影响，会自动去计算容器的大小，节省代码。

12. 标签分类

    * 按类型

      * block : div、p、ul、li、h1 ...
        1. 独占一行
        2. 支持所有样式
        3. 不写宽的时候，跟父元素的宽相同
        4. 所占区域是一个矩形
      * inline : span 、a、em、strong、img ...
        1. 挨在一起的
        2. 有些样式不支持，例如：width、height、margin、padding
        3. 不写宽的时候，宽度由内容决定
        4. 所占的区域不一定是矩形
        5. 内联标签之间会有空隙，原因：换行产生的
      * inline-block : input、select ...
        1. 挨在一起，但是支持宽高
      * 布局一般用块标签，修饰文本一般用内联标签

    * 按内容

      * Flow：流内容
      * Metadata：元数据
      * Sectioning：分区
      * Heading：标题
      * Phrasing：措辞
      * Embedded：嵌入的
      * Interactive：互动的

      （详情：https://www.w3.org/TR/html5/dom.html）

    * 按显示

      * 替换元素 :浏览器根据元素的标签和属性，来决定元素的具体显示内容。
                    img、input ...
      * 非替换元素 : 将内容直接告诉浏览器，将其显示出来。
                    div、h1、p ...

13. 显示框类型

    display: block inline inline-block none ...

    区别：
        display:none   不占空间的隐藏
        visibility: hidden 占空间的隐藏

14. 标签嵌套规范

    1. 本身具有规范的标签

       ul li

       dl dt dd

       table tr td

    2. 块能够嵌套内联

       ```
       <div>
           <span></span>
           <a href="#"></a>
       </div>
       ```

    3. 块嵌套块

       ```html
       <div>
           <div></div>
       </div>
       ```

       特殊：

       错误的写法

       ```html
       <p>
       	<div></div>
       </p>
       ```

    4. 内联是不能嵌套块

       错误的写法：

       ```html
       <span>
           <div></div>
       </span>
       ```

       特殊：

       正确的写法：

       ```html
       <a href="#">
           <div></div>
       </a>
       ```

15. 溢出隐藏

    overflow : 
            visible : 默认
            hidden
            scroll
            auto
          

    x轴、y轴
                overflow-x、overflow-y针对两个轴分别设置

16. 透明度与手势

    1. opacity : 0(透明) ~ 1(不透明)

       注：占空间、所有的子内容也会透明

    2. rgba() : 0 ~ 1

       注：可以让指定的样式透明，而不影响其他样式

    3. cursor : 手势

       default : 默认箭头

       要实现自定义手势：
                   准备图片： .cur 、 .ico 
                   cursor : url(./img/cursor.ico),auto;

17. 最大、最小宽高

    1. min-width、min-height、max-width、max-height

       %单位：换算 -> 已父容器的大小进行换算的

       一个容器怎么适应屏幕的高 : 容器加height:100%;   body:100%;  html:100%;

       html,body{ height:100%;}

        .contrainer{ height:100%;}

18. CSS默认样式

    没有默认样式的： div、span

    有默认样式的：

    ​		body ->  marign : 8px
    ​        h1 ->  margin : 上下 21.440px
    ​               font-weight : bold
    ​        p  ->  margin : 上下 16px
    ​        ul ->  margin : 上下 16px  padding : 左 40px
    ​               默认点：list-style : disc
    ​        a ->   text-decoration: underline;

    css reset : 

    ​	*{ margin:0; padding:0;}

    ​			优点：不用考虑哪些标签有默认的margin和padding
    ​            缺点：稍微的影响性能
    ​            body,p,h1,ul{ margin:0; padding:0;}

    ul{ list-style : none;} 

    a{ text-decoration: none; color:#999;}

    img{ dispaly:block}

    问题的现象：图片跟容器底部有一些空隙。
                    内联元素的对齐方式是按照文字基线对齐的，而不是文字底线对齐的。
                     vertical-align: baseline;  基线对齐方式，默认值
                      img{ vertical-align:bottom;} 解决方式是推荐的

    写具体页面的时候或一个布局效果的时候：

    1. 写结构
    2. CSS重置样式
    3. 写具体样式

    所以说css重置样式是很重要的

    

