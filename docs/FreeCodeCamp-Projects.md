# FreeCodeCamp-Projects

本文记录我在fcc中文社区刷的题，做的小项目。2020/4/1。



## Responsive Web Design Projects 

响应式网页设计项目。在此之前已经学过基本的知识，一天内把前面的小练习做完，现在是时候把学到的技能付诸实践了！通过接下来的项目，fcc让我有机会实践目前所学的技能，原理和概念，HTML，CSS，可视化设计，辅助功能等。

1. 搭建致敬页
2. 搭建调查表格
3. 搭建产品主页
4. 搭建技术文档页面
5. 搭建个人作品集页面

### 致敬页

[fcc题目（需求）地址](https://learn.freecodecamp.one/responsive-web-design/responsive-web-design-projects/build-a-tribute-page)

[我制作的页面地址](https://codepen.io/ultraman-agul/full/ZEGPWLe)

[代码编辑页面](https://codepen.io/ultraman-agul/pen/ZEGPWLe)

第一次使用到codepen这个在线编辑网站，一开始感觉怪怪的，后来觉得还挺好用。

这个页面制作简单，很基本的页面，但有一个地方需要注意：

```img`元素应相对于其父元素的宽度响应地调整大小，但不超过其原始大小。``

我一开始忽略了这个需求，看错误报告也发下缩小页面后图片呢不能自适应，对于手机端来说更是个大问题，所以为图片添加css样式

```html
#image {
			max-width:100%;
			height:auto; 
			margin:0 auto;
}
```

如此一来图片可以随着拉伸页面进行自适应了，问题也就解决了。( •̀ ω •́ )y

### 调查表单

[fcc题目（需求）地址](https://learn.freecodecamp.one/responsive-web-design/responsive-web-design-projects/build-a-survey-form)

[我制作的页面地址](https://codepen.io/ultraman-agul/full/MWwxGBY)

[代码编辑页面](https://codepen.io/ultraman-agul/pen/MWwxGBY)

给网页添加了背景图，但是发现这样会使文字看不清，想要实现背景图和颜色遮罩，我一开始想要使用伪类元素解决：

```css
body::after{
  position:absolute;
  content:"";
  width:100%;
  height:100%;
  top:0;
  left:0;
  background: rgba(255, 255, 255, 0.2);
}
```

![](C:\Users\Administrator\Desktop\markdown\media\1.png)

出现文字也被遮罩，所以我使用添加新标签<main></main>，添加css为

```css
main {
  background: rgba(255, 255, 255, 0.2);
  width:100%;
  height:100%;
  position:absolute;
}
```

可以实现。

但是当内容高度大于窗口高度，需要滑动滚动条时，出现问题：

![](C:\Users\Administrator\Desktop\markdown\media\2.png)

下方没有了遮盖，检查代码发现main标签添加了绝对定位absolute，虽然高度为100%，那是针对浏览器窗口大小所定的，并非随着body大小而改变，将 

```css
position:absolute;
```

去掉即可 。（尽量让代码简洁，不要出现多余的代码😵）

制作表单，让其居中时发现form始终无法居中，分析原因是form本身只是一个表单，对页面根本没有布局的作用，因此无法居中，解决方法是在form外面嵌套div标签，给div标签添加css样式`text-align:center;`解决。

### 产品登录页

[题目需求页面](https://learn.freecodecamp.one/responsive-web-design/responsive-web-design-projects/build-a-product-landing-page)

[代码编辑页面](https://codepen.io/ultraman-agul/pen/VwLNKPm?editors=1100)

[我制作的网页](https://codepen.io/ultraman-agul/full/VwLNKPm?editors=1100)

运用flexbox可以布局灵活的页面.

```css
#nav-bar {
  width: 50%;
  float: right;
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  justify-content: space-around;
}
footer {
  display: flex;
  flex-flow: row wrap;
  align-items: center;
}
```

媒体查询也是响应式布局的好方法。当视口宽度最大值小于400px时，padding:0;

```css
@media (max-width: 400px) {
  .nav-link {
    padding:0;
  }
}
```

使用iframe给网页嵌入视频，点击全屏无反应，查阅资料说不建议使用iframe，bug多，改用video标签引入后可以使用。

```css
<video src="http://www.w3school.com.cn/i/movie.ogg" controls>
//此处可以添加多个<source></source>  添加多个视频格式不一样，解决浏览器兼容性问题。
</video> 
```

flexbox和媒体查询的使用较为生疏，多使用才能熟练掌握。

### 技术文档

[题目需求页面](https://learn.freecodecamp.one/responsive-web-design/responsive-web-design-projects/build-a-technical-documentation-page)

[代码编辑页](https://codepen.io/ultraman-agul/pen/gOpJOoa?editors=1100)

[我制作的网页地址](https://codepen.io/ultraman-agul/full/gOpJOoa?editors=1100)

设计可以滚动的侧边导航栏：

```css
#navbar {
  position: fixed;
  top: 0;
  left: 0;
  min-width: 290px;
  height: 100%;
  width:300px;
  text-align: center;
}
.uu {
  /*   100%则没有滚动的空间 */
  height: 88%;
  /*   滚动条的设置 */
  overflow-y: auto;
  overflow-x: hidden;
  margin-top: 20px;
  border-right: 5px solid #ccc;
}
```

媒体查询

```css
@media only screen and (max-width:800px)
{
/*   响应手机端 */
  #navbar ul{
    border:1px solid #ccc;
    height:200px;
  }
  #navbar{
    position:absolute;   //浮在页面最上方
    width:100%;           //视口宽度
    max-height:270px;
    border:1px solid blue;
  }
}
```

### 个人网站

[题目需求页面](https://learn.freecodecamp.one/responsive-web-design/responsive-web-design-projects/build-a-personal-portfolio-webpage)

[代码编辑页面](https://codepen.io/ultraman-agul/pen/QWbXqXL?editors=1100)

[我制作的页面](https://codepen.io/ultraman-agul/full/QWbXqXL?editors=1100)

插入图片下方有缝隙

![](C:\Users\Administrator\Desktop\markdown\media\3.png)

添加图片样式，解决

```css
vertical-align:bottom;
```

**flex**和**grid**是当前流行的布局方法。Grid 布局与 [Flex 布局](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)有一定的相似性，都可以指定容器内部多个项目的位置。但是，它们也存在重大区别。

Flex 布局是轴线布局，只能指定"项目"针对轴线的位置，可以看作是**一维布局**。Grid 布局则是将容器划分成"行"和"列"，产生单元格，然后指定"项目所在"的单元格，可以看作是**二维布局**。Grid 布局远比 Flex 布局强大。

我一开始使用flex布局实现下图：

![](C:\Users\Administrator\Desktop\markdown\media\4.PNG)

```css
#flexx{ /*父盒子*/
  width:100%;
  display:flex;
  flex-flow: row wrap;
  justify-content:space-around;
  align-items:center;
  align-content:space-around;
}
#flexx div{ /*子盒子*/
  width:400px;
  height:450px;
  display:flex;
}
```

使用grid布局

```css
#usegrid{
  width:100%;
  display:grid;
  grid-gap:50px;  
  grid-template-columns:repeat(auto-fit,minmax(320px,1fr));
  max-width:1280px;
  padding:0 20px;
  margin: 0 auto; //居中。
}
```

同样可以实现，更为方便。

在为project-title两边添加隐藏尖括号，鼠标悬停时显示时，使用

```css
.code{
	display:none;
}
.code:hover{
	display:inline-block;
}
```

导致文字位置发生移动。因为display:none;不会保留元素位置。

使用visibility可以解决，隐藏时保留位置。

```css
.code{
	visibility:hidden;
}
.code:hover{
	visibility:visible;
}
```

如果是文字的话，可以把内容颜色设为与背景色一致，悬停时改变颜色。

