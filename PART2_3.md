# PART2_3

### 1.text-shadow

文字的阴影
    x y blur color

以上分别是x轴偏移量，y轴偏移量，模糊度，阴影颜色

 注：阴影的默认颜色是跟文字样色相同
 注：通过逗号的方式进行分割，可以设置多阴影

### 2.box-shadow

盒子阴影

​	x y blur spread color inset 多阴影

x和y是偏移量，blur是模糊度，spread是阴影范围，color是颜色，inset是设置内阴影，多阴影用逗号隔开。

​	 注：盒子阴影的默认样色是黑色。
​    注：默认就是外阴影，如果设置outset不起作用，可选的值只有inset表示内阴影。

### 3.mask 遮罩

url 		 ：路径

repeat	：平铺

x			：偏移量

y			：偏移量

/

w			：宽

h			：高

多遮罩用逗号隔开



注：mask目前还没有标准化，所以需要添加浏览器前缀。例：-webkit-mask

注：默认是x、y都平铺。

### 4.box-reflect

above \ below \ left \ right	：	上 \ 下 \ 左 \ 右

距离	：

遮罩|渐变	：	按照遮罩或渐变的方式直接写在后面

​	渐变：只是针对透明度的渐变，不能支持颜色的渐变。

### 5.blur模糊

​	filter:blur()

### 6.calc计算

​	四则运算

### 7.分栏布局

​	  column-count : 分栏的个数
​      column-width : 分栏的宽度 
​      column-gap : 分栏的间距   
​      column-rule : 分栏的边线
​      column-span : 合并分栏

注：column-width和column-count不要一起去设置。

### 8.伪元素

伪元素本质上是创建了一个有内容的虚拟容器。这个容器不包含任何DOM元素，但是可以包含内容。另外，开发者还可以为伪元素定制样式。
        :: selection
        :: first-line   /    first-letter
        :: before     /     after 
        …

### 9.CSS  Hack分类

1. CSS属性前缀法：	.elem{ _background:red; }

   | 前缀标识 |    兼容浏览器     |
   | :------: | :---------------: |
   |    _     |        IE6        |
   |   +,*    |      IE6,IE7      |
   |    \9    |  IE6,IE7,IE8,IE9  |
   |    \0    | IE8,IE9,IE10,IE11 |

   

2. 选择器前缀法

   | 前缀标识 |     兼容浏览器      |
   | :------: | :-----------------: |
   |  *html   |         IE6         |
   |  *+html  |         IE7         |
   |  :root   | IE9以上及现代浏览器 |

   

3. IE条件注释法

   IE10以上已经不支持注释法

### 10.IE低版本常见BUG

1. 透明度

2. 双边距
3. 最小高度
4. 图片边框

### 11.渐进增强与优雅降级

​		渐进增强：针对低版本浏览器进行构建页面，保证最基本的功能，然后在针对高级浏览器进行效果，交互等改进和追加功能达到更好的用户体验。

​		优雅降级：一开始就构建完整的功能，然后在针对低版本浏览器进行兼容。

### 12.布局扩展

1. 等高布局

   利用margin-bottom负值与padding-bottom配合实现。

2. 三列布局，左右固定，中间自适应

   1. BFC方式

   2. 定位

   3. 浮动（双飞翼布局，圣杯布局）

      margin负值实现

   4. flex弹性