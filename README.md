# front-end
## 一、小黑鱼
### 1、ES6是什么，有了解吗？
    ES6（ECMAScript 6）是 JavaScript 语言的下一代标准，2015年6月正式发布。Mozilla 公司将在这个标准的基础上，推出 JavaScript 2.0。
    目标：使得 JavaScript 语言可以用来编写大型的复杂的应用程序，成为企业级开发语言。
    ECMAScript 是 JavaScript 语言的国际标准，JavaScript 是 ECMAScript 的实现。
####  1.1、Symbol
        这是新增的一种原始数据类型，ES5 中原始类型有 5 种，在 ES6 中新引入了一种后，
        现在就是有 6 种原始数据类型了：Number、String、Boolean、null、undefined、Symbol


### 2、排序算法有哪些，最快的是什么，时间复杂度
    直接插入排序，希尔排序，简单选择排序，堆排序，冒泡排序，快速排序，归并排序，基数排序
    最快：快速排序    时间复杂度：nlog2n

### 3、前端三大框架
    vue,angular,react
#### 3.1、vue
#### 3.2、angular
#### 3.3、react
    
### 4、内存泄漏和内存溢出
#### 4.1、内存泄漏（memory leak）
        内存泄漏：由于疏忽或错误造成程序未能释放已经不再使用的内存。
        内存「在物理上并没有消失」，是应用程序分配某段内存后，由于设计错误，导致在「释放该段内存之前就失去了对该段内存的控制」，从而造成了内存的浪费。
        内存泄漏通常情况下只能由获得程序源代码的程序员才能分析出来。
#### 4.2、内存溢出（out of memory）
        内存溢出：系统在为某段执行指令（程序）分配内存的时候，发现内存不足，抛出错误。        
        
### 5、盒子模型
    可以认为每个html标签都是一个方块，然后这个方块又包着几个小方块，如同盒子一层层的包裹着。
    分别是：margin、border、padding、content。它们的关系是margin>border>padding>content。
    分为「IE盒模型」和「W3C标准盒模型」
#### 5.1、IE盒模型
        属性width,height，包含border和padding，指的是content+padding+border。
#### 5.2 W3C标准盒模型
        属性width,height，只包含内容content，不包含border和padding（在content里？）。

### 6、什么是闭包
  有权访问另一个函数作用域中变量的函数
  创建闭包的最常见的方式就是在一个函数内创建另一个函数，通过另一个函数访问这个函数的局部变量,利用闭包可以突破作用链域，将函数内部的变量和方法传递到外部。
#### 6.1、背景
   Javascript语言的特殊之处：</br>
     1、函数内部可以直接读取全局变量。
```js
     var n=999;
     function f1(){
　　　　 alert(n);
　　  }
　　  f1(); // 999    
```
   2、在函数外部自然无法读取函数内的局部变量
```js
     function f1(){
　　　　 var n=999;
　　  }
　　  alert(n); // error
```
   3、函数内部声明变量的时候，一定要使用var命令。如果不用的话，你实际上声明了一个全局变量
```js
     function f1(){
　　　　 n=999;
　　  }
　　  f1();
　　  alert(n); // 999
```
   需要得到函数内的局部变量->在函数的内部，再定义一个函数->将内部函数作为返回值
   =>在原函数外部读取到其内部变量
```js
     function f1(){
　　　　 var n=999;
　　　　 function f2(){
　　　　　 　alert(n); 
　　　   }
　　　　 return f2;
　　  }
　　  var result=f1();
　　  result(); // 999
     //f2函数，就是闭包
```    
   总结：闭包就是能够读取其他函数内部变量的函数。
        由于在Javascript语言中，只有函数内部的子函数才能读取局部变量，因此可以把闭包简单理解成"定义在一个函数内部的函数"。
        在本质上，闭包就是将函数内部和函数外部连接起来的一座桥梁。
#### 6.2、闭包的用途
    1、读取函数内部的变量；2、让这些变量的值始终保持在内存中。
    
[上述闭包有关信息来源](http://www.ruanyifeng.com/blog/2009/08/learning_javascript_closures.html)
        
### 7、什么是指针
    是编程语言中的一类数据类型及其对象或变量，用来表示或存储一个存储器地址，这个地址的值直接指向（points to）存在该地址的对象的值。

### 8、按值调用（call by value）和按引用调用（call by reference）
    
### 9、块元素和行内元素
#### 9.1、块级元素：block element（div,address,p,form,h123...）
    每个块级元素默认占一行高度，一行内添加一个块级元素后无法一般无法添加其他元素（float浮动后除外）；
    两个块级元素连续编辑时，会在页面自动换行显示。块级元素一般可嵌套块级元素或行内元素；
    块级元素一般作为容器出现，用来组织结构，但并不全是如此。    
   特点：`1、总是在新行上开始；2、高度，行高以及外边距和内边距都可控制；3、宽度缺省是它的容器的100%，除非设定一个宽度。4、可以容纳内联元素和其他块元素`
#### 9.2、行内元素：inline element（a,b,br,img,label,input,span...）
    也叫内联元素、内嵌元素等；行内元素一般都是基于语义级(semantic)的基本元素，只能容纳文本或其他内联元素。
   特点:`1、和其他元素都在一行上；2、高，行高及外边距和内边距不可改变；3、宽度就是它的文字或图片的宽度，不可改变；4、只能容纳文本或者其他内联元素`
#### 9.3、两者区别
    区别一：
    块级：块级元素会独占一行，默认情况下宽度自动填满其父元素宽度
    行内：行内元素不会独占一行，相邻的行内元素会排在同一行。其宽度随内容的变化而变化。
    区别二：
    块级：块级元素可以设置宽高
    行内：行内元素不可以设置宽高
    区别三：
    块级：块级元素可以设置margin，padding
    行内：行内元素水平方向的margin-left; margin-right; padding-left; padding-right;可以生效。
         但是竖直方向的margin-bottom; margin-top; padding-top; padding-bottom;却不能生效。
    区别四：
    块级：display:block;
    行内：display:inline;
    可以通过修改display属性来切换块级元素和行内元素
    
### 10、为什么要清除浮动，怎么清除浮动
    清除浮动是为了清除使用浮动元素产生的影响。浮动的元素，高度会塌陷，而高度的塌陷使我们页面后面的布局不能正常显示。
   方法一：添加新的元素 、应用 clear：both；
##### HTML
```html
    <div class="outer">
        <div class="div1">1</div>
        <div class="div2">2</div>
        <div class="div3">3</div>
        <div class="clear"></div>
    </div>
```
##### CSS
```css
    .clear{clear:both; height: 0; line-height: 0; font-size: 0}
```
   方法二：父级div定义 overflow: auto（注意：是父级div也就是这里的 div.outer）
##### HTML
```html
    <div class="outer over-flow"> //这里添加了一个class
        <div class="div1">1</div>
        <div class="div2">2</div>
        <div class="div3">3</div>
        <!--<div class="clear"></div>-->
    </div>
```
##### CSS
```css
    .over-flow{
        overflow: auto; zoom: 1; //zoom: 1; 是在处理兼容性问题
    }
```
   方法三：:after 方法（注意：作用于浮动元素的父亲）</br>
   `利用:after和:before来在元素内部插入两个元素块，从而达到清除浮动的效果。`
    
### 11、http请求过程
    域名解析 --> 发起TCP的3次握手 --> 建立TCP连接后发起http请求 --> 服务器响应http请求，浏览器得到html代码 
    --> 浏览器解析html代码，并请求html代码中的资源（如js、css、图片等） --> 浏览器对页面进行渲染呈现给用户

### 12、jquery的链式请求
   链式调用是通过return this的形式来实现的。通过对象上的方法最后加上return this，把对象再返回回来，对象就可以继续调用方法，实现链式操作。
```js
    Obj().init().setFlag();  
```
   如果需要链式的处理，只需要在方法内部返回当前的这个实例对象this就可以了，因为返回当前实例的this，就又可以访问自己的原型了。
```js
    Obj.prototype = {  
    init: function() {  
        ...  
        return this;  
    },  
    setFlag: function() {  
        ...  
        return this;  
    }  
}  
```
    链式调用的好处：节省代码量，代码看起来更优雅。
    链式调用的问题：所有对象的方法返回的都是对象本身，也就是说没有返回值，所以这种方法不一定在任何环境下都适合。

### 13、HTML5
    HTML是网页设计语言，是用字符描述网页是什么样子的语言(基本元素为标签)。
    后来又发展了CSS(样式语言)、JavaScript(脚本语言)，而HTML就演变为单纯的描述页面元素的语言。
    三者一同完成了一个网页需要的绝大部分功能 .

### 14、行高？
### 15、js是什么，是用来干什么的
    HTML负责结构， CSS负责展示， javascript（加上AJAX, JSON）负责逻辑。
    js是脚本语言。浏览器是逐行的读取代码，而传统编程会在执行前进行编译

### 16、ajax原理，请求方式（AsynchronousJavaScript and XML）
    1.使用CSS和XHTML来表示。
    2.使用DOM模型来交互和动态显示。
    3.使用XMLHttpRequest来和服务器进行异步通信。
    4.使用javascript来绑定和调用。
  Ajax的原理简单来说通过XmlHttpRequest对象来向服务器发异步请求，从服务器获得数据，然后用javascript来操作DOM而更新页面。这其中最关键的一步就是`从服务器获得请求数据`。要清楚这个过程和原理，我们必须对 XMLHttpRequest有所了解。
##### XMLHttpRequest
    ajax的核心机制，是一种支持异步请求的技术。
    简单的说，也就是javascript可以及时向服务器提出请求和处理响应，而不阻塞用户。达到无刷新的效果。
##### GET和POST
    GET常用于向服务器查询某些信息。必要时，可以将查询字符串参数追加到URL的末尾，以便将查询条件发送给服务器。
    POST通常用于向服务器发送应该被保存的数据。
    POST请求将内容放在HTTP请求的主体（body）中进行发送，可以进行加密。而GET请求则只能以URL参数明文发送数据，因此安全性不如POST。
    get传送的数据量较小，不能大于2KB（URL长度限制）。post传送的数据量较大，一般被默认为不受限制。但理论上，因服务器的不同而异。
    
### 17、bootstrap是什么，栅格系统
#### 栅格系统
    栅格系统是Bootstrap响应式布局的框架，栅格系统通过一系列的行（row）与列（column）的组合来创建页面布局：
    1、行（.row）必须包含在容器（container或container-fluid）里；
    2、在行内创建一组水平排开的列（.col）；
    3、每一行被分为12格，通过类似.col-sm-4的类来控制每一列占位多少格（这里是4格）；
    4、每一行的列所占格数超过12，便会引起换行；
    5、可以对不同大小的屏幕定义不同的布局。
    
### 18、栈和队列都是什么
#### 栈（LIFO）
    只能允许在链表或数组的一端（称为堆栈顶端指针，top）进行加入数据（push）和输出数据（pop）的运算。
    应用：递归调用、括号匹配、数制转换...
#### 队列（FIFO）
    只允许在后端（rear）进行插入操作，在前端（front）进行删除操作。
    队列的操作方式和堆栈类似，唯一的区别在于队列只允许新数据在后端进行添加。
    应用：广度优先搜索、二叉树的层次遍历...

## 二、育儿网（仅笔试题）
### 1、css3有哪些实用的选择器
   选择器：每一条css样式定义由两部分组成，形式如下： [code] 选择器{样式} [/code] 在{}之前的部分就是“选择器”。 “选择器”指明了{}中的“样式”的作用对象，也就是“样式”作用于网页中的哪些元素</br>
   `1.id选择器（ # myid）`</br>
   `2.类选择器（.myclassname）`</br>
   `3.标签选择器（div, h1, p）`</br>
   `4.相邻选择器（h1 + p）`</br>
   `5.子选择器（ul > li）`</br>
   `6.后代选择器（li a）`</br>
   `7.通配符选择器（ * ）`</br>
   `8.属性选择器（a[rel = "external"]）`</br>
   `9.伪类选择器（a:hover, li:nth-child）`</br>

### 2、css sprites是什么，用来干什么的，在移动端和web端有什么区别
    
### 3、typeof返回值类型
    number, boolean, string, undefined, object, function, symbol(ES6提供的新特性).

### 4、DOM事件响应过程
    事件捕获阶段
    处于目标阶段
    事件冒泡阶段
    
### 5、水平居中的实现方法，如何让一个绝对定位的div实现水平垂直居中
  1、水平居中：给div设置一个宽度，然后添加margin:0 auto属性
```js
div{
 	width:200px;
 	margin:0 auto;
  }
```
  2、让绝对定位的div居中
```js
div {
 	position: absolute;
 	width: 300px;
 	height: 300px;
 	margin: auto;
 	top: 0;
 	left: 0;
 	bottom: 0;
 	right: 0;
 	background-color: pink;	/* 方便看效果 */
 }
```
  3、水平垂直居中一
```js
//确定容器的宽高 宽500 高 300 的层
//设置层的外边距
 div {
 	position: relative;		/* 相对定位或绝对定位均可 */
 	width:500px;
 	height:300px;
 	top: 50%;
 	left: 50%;
 	margin: -150px 0 0 -250px;     	/* 外边距为自身宽高的一半 */
 	background-color: pink;	 	/* 方便看效果 */

  }
```
  4、水平垂直居中二
```js
//未知容器的宽高，利用 `transform` 属性
 div {
 	position: absolute;		/* 相对定位或绝对定位均可 */
 	width:500px;
 	height:300px;
 	top: 50%;
 	left: 50%;
 	transform: translate(-50%, -50%);
 	background-color: pink;	 	/* 方便看效果 */
 }
```
  5、水平垂直居中三
```js
//利用 flex 布局
//实际使用时应考虑兼容性
 .container {
 	display: flex;
 	align-items: center; 		/* 垂直居中 */
 	justify-content: center;	/* 水平居中 */

 }
 .container div {
 	width: 100px;
 	height: 100px;
 	background-color: pink;		/* 方便看效果 */
 }  
```
   
### 6、为什么会出现浮动，如何消除浮动
### 7、display:inlineblock为什么会有间隙，如何消除间隙
### 8、移动端点击网页为什么会有延迟，延迟多久，如何消除延迟
### 9、有一个行高自定义的div，里面有两个div，一个行高100px，如何让另一个充满div
### 10、<meta>标签内容，作用
