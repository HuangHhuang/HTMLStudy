HTML再次入门

VSCode编辑器

快捷键：

 shift + end : 从头选中一行
 shift + home : 从尾部选中一行
 shift + alt + ↓ : 快速复制一行
 alt + ↑或↓ : 快速移动一行

多光标 : alt + 鼠标左键
 ctrl + d : 选则相同元素的下一个



五大浏览器：

IE浏览内核 （微软旗下的浏览器）： Trident内核

Opera浏览器内核 （Opera Software ASA旗下）：最初是自己的Presto内核，后来是Webkit，现在是Blink内核；

Safari浏览器内核 （苹果旗下的浏览器）：Webkit内核

Firefox浏览器内核（Mozilla旗下的浏览器）：Gecko内核

Chrome浏览器内核（Google旗下的浏览器）：统称为 Chromium内核或Chrome内核，最开始Chrome采用webkit作为浏览器内核，直到2013年，Google宣布不再使用苹果的webkit内核，开始使用webkit的分支内核Blink

五大浏览器的更多信息科查看此博客https://blog.csdn.net/qq_36602186/article/details/80310200



创建标签的快捷键：单词 + tab键 -> <单词>

HTML常见标签：http://www.html5star.com/manual/html5label-meaning/



快捷添加注释与删除注释：
           1. ctrl + /					注释选中代码
           2. shift + alt + a       创建一个空的注释



HTML语义化

​	所谓HTML语义化指的是，根据网页中内容的结构，选择适合的HTML标签进行编写。

文本修饰标签

强调 -> 双标签 :

```html
<strong></strong>
<em></em>
```

区别：
   1. 写法和展示效果是有区别的，一个加粗、一个斜体
         g的强调性更强，em的强调性稍弱。

         

```html
下标 : <sub></sub>
上标 : <sup></sup>
```

```html
删除文本 : <del></del>
插入文本 : <ins></ins>
```

注：一般情况下，删除文本都是和插入文本配合使用的。     

#### 图片标签

 img -> 单标签 
        src : 引入图片的地址。
        alt : 当图片出现问题的时候，可以显示一段友好的提示文字。
        title : 提示信息
        width、height : 图片的大小

#### 链接标签

```html
<a></a>
	href属性 : 链接的地址
	target属性 : 可以改变链接打开的方式，默认情况下：
	在当前页面打开 _self  
	新窗口打开 _blank

<base>
	单标签 ：作用就是改变链接的默认行为的。
```

跳转锚点

​	实现一：#+id属性

​			id属性是需要跳转到的标签的id属性。

​	实现二：#+name属性

​			name属性需要在跳转标签的上方加上一个<a>标签，name的值是a标签的name值。



#### 特殊字符

1. & + 字符

2. 解决冲突啊 左右尖括号、添加多个空格的实现

3. ```html
   &lt; &gt; &nbsp;
   ```

   

#### 标签列表

1. 无序列表 -> ul li 符合嵌套的规范
2. 有序列表 -> ol li 一般用的比较少，可以用无序列表来实现
3. 定义列表 -> dl dt dd 列表项需要添加标签和对标题进行描述的内容

```html
<dl>
    <dt>HTML</dt>
    <dd>超文本标记语言</dd>
    <dt>CSS</dt>
    <dd>层叠样式表</dd>
    <dt>JavaScript</dt>
    <dd>网页脚本语言</dd>
</dl>
```



#### 表格标签

table tr th td caption 等

注：之前是有嵌套关系的，要符合嵌套规范。

语义化标签：tHead、tBody、tFood

注：在一个table中，tBody是可以出现多次的，但是tHead、tFood只能出现一次

align : left、center、right

valign : top、middle、bottom

##### colspan和rowspan

`colspan`用来指定单元格横向跨越的列数：colspan就是合并列的，colspan=2的话就是合并两列。

`rowspan用来`指定单元格纵向跨越的行数:rowspan就是用来合并行的，比如rowspan=2就是合并两行，



#### 表单标签

 form、input、textarea、select、label ..

	input(单标签)标签有一个type属性，决定是什么控件。
	还有一些常见的属性：
		checked、disabled、name、for ...

代码展示：

```html
<form action="https://www.baidu.com">
        <h2>输入框：</h2>
        <input type="text" placeholder="请输入用户名">
        <h2>密码框：</h2>
        <input type="password" placeholder="请输入密码">
        <h2>复选框：</h2>
        <input type="checkbox" checked>葡萄
        <input type="checkbox" checked>香蕉
        <input type="checkbox" disabled>苹果
        <h2>单选框：</h2>
        <input type="radio" name="gender">男
        <input type="radio" name="gender">女
        <h2>上传文件：</h2>
        <input type="file">
        <h2>提交和重置：</h2>
        <input type="submit">
        <input type="reset">
        <h2>多行文本框：</h2>
        <textarea cols="30" rows="10"></textarea>
        <h2>下拉菜单：</h2>
        <select>
            <option selected disabled>请选择</option>
            <option>上海</option>
            <option>北京</option>
            <option>广州</option>
        </select>
        <!-- 多选 -->
        <select multiple>
            <option>上海</option>
            <option>北京</option>
            <option>广州</option>
        </select>
        <!-- 多选文件 -->
        <input type="file" multiple>
        <!-- 点击文字也能选中 -->
        <input type="radio" name="gender" id="man"><label for="man">男</label>
        <input type="radio" name="gender" id="woman"><label for="woman">女</label>
    </form>
```



#### div和span

​	div : 做一个区域划分的块
​    span : 对文字进行修饰的内联