#前端开发面试题基础篇答案

&emsp;&emsp;来自网络和自己的总结

## <a name='preface'>前言</a> ##


**前端开发知识点：**

    HTML&CSS：
        对Web标准的理解、浏览器内核差异、兼容性、hack、CSS基本功：布局、盒子模型、选择器优先级、
        HTML5、CSS3、Flexbox

    JavaScript：
        数据类型、运算、对象、Function、继承、闭包、作用域、原型链、事件、RegExp、JSON、Ajax、
        DOM、BOM、内存泄漏、跨域、异步装载、模板引擎、前端MVC、路由、模块化、Canvas、ECMAScript 6、Nodejs、编程规范

    其他：
        移动端、响应式、自动化构建、HTTP、离线存储、WEB安全、优化、重构、团队协作、可维护、易用性、SEO、UED、架构、职业生涯、快速学习能力、BOM、DOM

作为一名前端工程师，**无论工作年头长短都应该掌握的知识点**：


        1、DOM结构 —— 两个节点之间可能存在哪些关系以及如何在节点之间任意移动。

        2、DOM操作 ——如何添加、移除、移动、复制、创建和查找节点等。

        3、事件 —— 如何使用事件，以及IE和标准DOM事件模型之间存在的差别。

        4、XMLHttpRequest —— 这是什么、怎样完整地执行一次GET请求、怎样检测错误。

        5、严格模式与混杂模式 —— 如何触发这两种模式，区分它们有何意义。

        6、盒模型 —— 外边距、内边距和边框之间的关系，及IE8以下版本的浏览器中的盒模型

        7、块级元素与行内元素 —— 怎么用CSS控制它们、以及如何合理的使用它们

        8、浮动元素 ——怎么使用它们、它们有什么问题以及怎么解决这些问题。

        9、HTML与XHTML ——二者有什么区别，你觉得应该使用哪一个并说出理由。

        10、JSON —— 作用、用途、设计结构。

**备注：**

    根据自己需要选择性了解，面试题是对理论知识的总结，另外也要让自己学会应该如何表达。


## <a name='html'>一、HTML</a>

- Doctype作用？标准模式与兼容模式各有什么区别?

        （1）、<!DOCTYPE>声明位于位于HTML文档中的第一行，处于 <html> 标签之前。告知浏览器的解析器用什么文档标准解析这个文档。DOCTYPE不存在或格式不正确会导致文档以兼容模式呈现。

        （2）、标准模式的排版 和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示,模拟老式浏览器的行为以防止站点无法工作。

- HTML5 为什么只需要写 <!doctype html>？

         HTML5 不基于 SGML，因此不需要对DTD（Document Type Definition）进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照它们应该的方式来运行）；

         而HTML4.01基于SGML,所以需要对DTD进行引用和声明，才能告知浏览器文档所使用的文档类型。

- 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？

        首先：CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认的display值，如div的display默认值为“block”，则为“块级”元素；span默认display属性值为“inline”，是“行内”元素。

        （1）行内元素有：a b span img input select strong（强调的语气）
        （2）块级元素有：div ul ol li(不带描述的列表) dl dt dd(带描述的列表) h1 h2 h3 h4 p

        （3）常见的空元素：
            <br> <hr> <img> <input> <link> <meta>
            鲜为人知的是：
            <area> <base> <col> <command> <embed> <keygen> <param> <source> <track> <wbr>

- ol、ul和dl标签的区别？
        
        当使用有序无标题描述的列表时使用ol，无序无标题的列表时使用ul，创建带标题描述的列表使用dl。
        
- img元素的title和alt属性有什么区别？有什么用？
        
        alt元素是img元素图片内容加载失败时显示的文字，title则是鼠标放到图片上时显示的提示。有利于SEO和阅读软件读取网页文字内容。


- this、constructor、prototype、__proto__的区别？

- js执行的两个阶段预处理阶段和执行阶段各做了什么？

- ajax中 xhrFields: { withCredentials: true } 有什么作用？

- 浏览器的主要组件哪些？
        
        浏览器组件由七部分组成。用户界面，js引擎，渲染引擎，网络，UI后端，js解释器，数据存储。内核指js引擎和渲染引擎。

- 介绍一下你对浏览器内核的理解？

        主要分成两部分：渲染引擎(layout engineer或Rendering Engine)和JS引擎。
        渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。所有网页浏览器、电子邮件客户端以及其它需要编辑、显示网络内容的应用程序都需要内核。

        JS引擎则：解析和执行javascript来实现网页的动态效果。
        最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。

- 常见的浏览器内核有哪些？

        Trident内核：IE,MaxThon,TT,The World,360,搜狗浏览器等。[又称MSHTML]
        Gecko内核：Netscape6及以上版本，FF,MozillaSuite/SeaMonkey等
        Presto内核：Opera7及以上。      [Opera内核原为：Presto，现为：Blink;]
        Webkit内核：Safari,Chrome等。   [ Chrome的：Blink（WebKit的分支）]

      详细文章：[浏览器内核的解析和对比](http://www.cnblogs.com/fullhouse/archive/2011/12/19/2293455.html)



- html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和
HTML5？

        * HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。
              绘画 canvas;
              用于媒介回放的 video 和 audio 元素;
              localStorage和sessionstorage;
              语意化更好的内容元素，比如 article、footer、header、nav、section;
              表单控件，calendar、date、time、email、url、search;
              新的技术webworker, websockt, Geolocation;

          移除的元素：
              纯表现的元素：basefont，big，center，font, s，strike，tt，u;
              对可用性产生负面影响的元素：frame，frameset，noframes；

        * 支持HTML5新标签：
             IE8/IE7/IE6支持通过document.createElement方法产生的标签，
             可以利用这一特性让这些浏览器支持HTML5新标签，
             浏览器支持新标签后，还需要添加标签默认的样式。

             当然最好的方式是直接使用成熟的框架、比如html5shim;
             <!--[if lt IE 9]>
                <script> src="http://html5shim.googlecode.com/svn/trunk/html5.js"</script>
             <![endif]-->

        * 如何区分HTML5： DOCTYPE声明\新增的结构元素\功能元素


- 简述一下你对HTML语义化的理解？

        用正确的标签做正确的事情。
        html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;
        及时在没有样式CCS情况下也以一种文档格式显示，并且是容易阅读的;
        搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;
        使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

- HTML5的离线储存怎么使用，工作原理能不能解释一下？

        在用户没有与因特网连接时，可以正常访问站点或应用，在用户与因特网连接时，更新用户机器上的缓存文件。
        原理：HTML5的离线存储是基于一个新建的.appcache文件的缓存机制(不是存储技术)，通过这个文件上的解析清单离线存储资源，这些资源就会像cookie一样被存储了下来。之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示。


        如何使用：
        1、页面头部像下面一样加入一个manifest的属性；
        2、在cache.manifest文件的编写离线存储的资源；
            CACHE MANIFEST
            #v0.11
            CACHE:
            js/app.js
            css/style.css
            NETWORK:
            resourse/logo.png
            FALLBACK:
            / /offline.html
        3、在离线状态时，操作window.applicationCache进行需求实现。

    详细的使用请参考：[有趣的HTML5：离线存储](http://segmentfault.com/a/1190000000732617)



- 浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？

        在线的情况下，浏览器发现html头部有manifest属性，它会请求manifest文件，如果是第一次访问app，那么浏览器就会根据manifest文件的内容下载相应的资源并且进行离线存储。如果已经访问过app并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面，然后浏览器会对比新的manifest文件与旧的manifest文件，如果文件没有发生改变，就不做任何操作，如果文件改变了，那么就会重新下载文件中的资源并进行离线存储。并在下一次生效。
        离线的情况下，浏览器就直接使用离线存储的资源。
        详细的使用请参考：[有趣的HTML5：离线存储](http://segmentfault.com/a/1190000000732617)

- 请描述一下 cookies，sessionStorage 和 localStorage 的区别？

        cookie是网站为了标示用户身份而储存在用户本地终端（Client Side）上的数据（通常经过加密）。
        cookie数据始终在同源的http请求中携带（即使不需要），记会在浏览器和服务器间来回传递。
        sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存。

        存储大小：
            cookie数据大小不能超过4k。
            sessionStorage和localStorage 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。

        有期时间：
            localStorage    存储持久数据，浏览器关闭后数据不丢失除非主动删除数据；
            sessionStorage  数据在当前浏览器窗口关闭后自动删除。
            cookie  设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭

- iframe有那些缺点？

        1.iframe会阻塞主页面的Onload事件；
        2.搜索引擎的检索程序无法解读这种页面，不利于SEO;
        3.frame和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。

        使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript
        动态给iframe添加src属性值，这样可以绕开以上两个问题。

- Label的作用是什么？是怎么用的？

        label标签来定义表单控制间的关系,当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。

        <label for="Name">Number:</label>
        <input type=“text“name="Name" id="Name"/>
        <label>Date:<input type="text" name="B"/></label>

- HTML5的form如何关闭自动完成功能？

        给不想要提示的 form 或下某个input 设置为 autocomplete=off。

- 如何实现浏览器内多个标签页之间的通信? (阿里)

        调用localstorge、cookies等本地存储方式

- webSocket如何兼容低浏览器？(阿里)

        Adobe Flash Socket 、
        ActiveX HTMLFile (IE) 、
        基于 multipart 编码发送 XHR 、
        基于长轮询的 XHR

- 页面可见性（Page Visibility）API 可以有哪些用途？

        在页面被切换到其他后台进程的时候，自动暂停音乐或视频的播放；

- 如何在页面上实现一个圆形的可点击区域？

        1、map+area或者svg
        2、border-radius
        3、纯js实现 需要求一个点在不在圆上简单算法、获取鼠标坐标等等

- 实现不使用 border 画出1px高的线，在不同浏览器的标准模式与怪异模式下都能保持一致的效果。

        <div style="height:1px;overflow:hidden;background:#ccc"></div>


- 网页验证码是干嘛的，是为了解决什么安全问题。

        区分用户是计算机还是人的公共全自动程序。可以防止：恶意破解密码、刷票、论坛灌水；
        有效防止黑客对某一个特定注册用户用特定程序暴力破解方式进行不断的登陆尝试；

- 浏览器缓存机制一共9种，列一下。

        http cache、cookie、localstorage、sessionStorage、webSQL、indexDB、application cache、cache storage、flash；


## <a name='css'>CSS</a>

- css flex布局的兼容性写法。

    flex性能很差，尽量避免使用，就像js中的with一样的东西。一般仍然用其它的布局方案。一定要写的话。
    
    .box{
      width: 75%;
      height: 50px;
      background: #eee;
      border:#ccc 1px solid;
      margin: 20px auto;
      padding: 5px;
      display: -webkit-box;
        display: -moz-box;
        display: -o-box;
        display: -ms-flexbox;
        display: flex;
    }
    .item{
      border:#ccc 1px solid;
      margin: 0 5px;
      height: 48px;
      -moz-box-flex: 1;
        -webkit-box-flex: 1;
            -o-box-flex: 1;
            -ms-flex: 1;
                flex: 1;
    }
  

- css引入方式有哪几种？使用link和@import有什么区别？

        引入方法：link、import、style标签、style属性、js操作
        
        区别：
        （1）link属于XHTML标签，除了加载CSS外，还能用于定义RSS, 定义rel连接属性等作用；而@import是CSS提供的，只能用于加载CSS;
        （2）页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;
        （3）import是CSS2.1 提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题;


- 介绍一下CSS的盒子模型？

        （1）有两种， IE 盒子模型、标准 W3C 盒子模型：IE盒模型的width包含border + padding + content，w3c 盒子模型width只包含content部分，height同理。
        （2）盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border)。

- box-sizing 取值和盒模型

        box-sizing 为padding-box是使用的标准盒模型，为border-box时使用的IE盒模型。

- 介绍所知道的CSS hack技巧(如：_， *， +， \9， !important 之类)

        .all IE{ property:value\9; }
        .gte IE 8{ property:value\0; }
        .lte IE 7{ *property:value; }
        .IE 9{ property:value\9\0; }
        .IE 7{ +property:value; }
        .IE 6{ _property:value; }
        .not IE{ property//:value; }
        
        !important只有Ie7.0和firefox可以识别，但是Ie6.0不能成功应用.
        

- CSS选择符有哪些？哪些属性可以继承？

        *   1.id选择器（ # myid）
            2.类选择器（.myclassname）
            3.标签选择器（div, h1, p）
            4.相邻选择器（h1 + p）
            5.子选择器（ul > li）
            6.后代选择器（li a）
            7.通配符选择器（ * ）
            8.属性选择器（a[rel = "external"]）
            9.伪类选择器（a: hover, li: nth - child）

        *   可继承的样式： font-size font-family color, ul, li, dl;

        *   不可继承的样式：border padding margin width height ;


- CSS优先级算法如何计算？
        *   优先级就近原则，同权重情况下样式定义最近者为准;
        *   载入样式以最后载入的定位为准;

        优先级为:
           !important >  id > class > tag
            important 比 内联优先级高

- CSS3新增伪类有那些？

        CSS3新增伪类举例：
            p:first-of-type 选择属于其父元素的首个 <p> 元素的每个 <p> 元素。
            p:last-of-type  选择属于其父元素的最后 <p> 元素的每个 <p> 元素。
            p:only-of-type  选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。
            p:only-child    选择属于其父元素的唯一子元素的每个 <p> 元素。
            p:nth-child(2)  选择属于其父元素的第二个子元素的每个 <p> 元素。
            :enabled        :disabled 控制表单控件的禁用状态。
            :checked        单选框或复选框被选中。

- 如何居中div？如何居中一个浮动元素？如何让绝对定位的div居中？

    *  给div设置一个宽度，然后添加margin:0 auto属性

            div{
                width:200px;
                margin:0 auto;
             }


    *  居中一个浮动元素

              确定容器的宽高 宽500 高 300 的层
              设置层的外边距

             .div {
                  width:500px ; height:300px;//高度可以不设
                  margin: -150px 0 0 -250px;
                  position:relative;         //相对定位
                  background-color:pink;     //方便看效果
                  left:50%;
                  top:50%;
             }

    *  让绝对定位的div居中

              position: absolute;
              width: 1200px;
              background: none;
              margin: 0 auto;
              top: 0;
              left: 0;
              bottom: 0;
              right: 0;


- display有哪些值？说明他们的作用。

          block 像块类型元素一样显示。
          inline 行内元素类型一样
          none 缺省值。象行内元素类型一样显示。
          inline-block 象行内元素一样显示，但其内容象块类型元素一样显示。
          list-item 象块类型元素一样显示，并添加样式列表标记。


- position的值relative和absolute定位原点是？

          absolute
            生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。

          fixed （老IE不支持）
            生成绝对定位的元素，相对于浏览器窗口进行定位。

          relative
            生成相对定位的元素，相对于其正常位置进行定位。

          static
            默认值。没有定位，元素出现在正常的流中
           （忽略 top, bottom, left, right z-index 声明）。

          inherit
            规定从父元素继承 position 属性的值。

- CSS3有哪些新特性？

          CSS3实现圆角（border-radius:8px），
          阴影（box-shadow:10px），
          文字特效（text-shadow、），
          线性渐变（gradient），
          旋转（transform）
          transform:rotate(9deg) scale(0.85,0.90) translate(0px,-30px) skew(-9deg,0deg);//旋转,缩放,定位,倾斜
          增加了更多的CSS选择器
          多背景 rgba

- 请解释一下CSS3的Flexbox（弹性盒布局模型）,以及适用场景？

        元素可以改变大小以适应可用空间，当可用空间变大，Flex元素将伸展大小以填充可用空间，当Flex元素超出可用空间时将自动缩小。总之，Flex元素是可以让你的布局根据浏览器的大小变化进行自动伸缩。
        
- 用纯CSS创建一个三角形的原理是什么？

        把上、左、右三条边隐藏掉（颜色设为 transparent）
        #demo {
          width: 0;
          height: 0;
          border-width: 20px;
          border-style: solid;
          border-color: transparent transparent red transparent;
        }

- 一个满屏 品 字布局 如何设计?

        简单的方式：
            上面的div宽100%，
            下面的两个div分别宽50%，
            然后用float或者inline使其不换行即可

- em、px、rem的计算方法？

        em是浏览器默认的字体大小，一般浏览器为1em = 16px，px是像素大小，rem是相对于根元素的em倍数。

- 常见前端兼容性问题？

        * png24位的图片在iE6浏览器上透明背景会变成灰色，解决方案是做成PNG8.

        * 浏览器默认的margin和padding不同。解决方案是加一个全局的*{margin:0;padding:0;}来统一。

        * IE6双边距bug:块属性标签float后，又有横行的margin情况下，在ie6显示margin比设置的大。

          浮动ie产生的双倍距离 #box{ float:left; width:10px; margin:0 0 0 100px;}

          这种情况之下IE会产生20px的距离，解决方案是在float的标签样式控制中加入 ——_display:inline;将其转化为行内属性。(_这个符号只有ie6会识别)

          渐进识别的方式，从总体中逐渐排除局部。

          首先，巧妙的使用“\9”这一标记，将IE游览器从所有情况中分离出来。
          接着，再次使用“+”将IE8和IE7、IE6分离开来，这样IE8已经独立识别。

          css
              .bb{
                  background-color:#f1ee18;/*所有识别*/
                  .background-color:#00deff\9; /*IE6、7、8识别*/
                  +background-color:#a200ff;/*IE6、7识别*/
                  _background-color:#1e0bd1;/*IE6识别*/
              }

        *  IE下,可以使用获取常规属性的方法来获取自定义属性,
           也可以使用getAttribute()获取自定义属性;
           Firefox下,只能使用getAttribute()获取自定义属性。
           解决方法:统一通过getAttribute()获取自定义属性。

        *  IE下,even对象有x,y属性,但是没有pageX,pageY属性;
           Firefox下,event对象有pageX,pageY属性,但是没有x,y属性。

        *  解决方法：（条件注释）缺点是在IE浏览器下可能会增加额外的HTTP请求数。

        *  Chrome 中文界面下默认会将小于 12px 的文本强制按照 12px 显示,
           可通过加入 CSS 属性 -webkit-text-size-adjust: none; 解决。

        超链接访问过后hover样式就不出现了 被点击访问过的超链接样式不在具有hover和active了解决方法是改变CSS属性的排列顺序:
        L-V-H-A :  a:link {} a:visited {} a:hover {} a:active {}


- li与li之间有看不见的空白间隔是什么原因引起的？有什么解决办法？

        li与li之间有默认的回车空格会导致用空白间隙。设置float或list-style-type：none

- 经常遇到的浏览器的兼容性有哪些？原因，解决方法是什么，常用hack的技巧 ？

        IE6 png8问题；margin双间距问题；浏览器默认样式问题；移动端宽度布局适配问题；

- 为什么要初始化CSS样式。有哪几种思路？

        - 因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对CSS初始化往往会出现浏览器之间的页面显示差异。

        - 当然，初始化样式会对SEO有一定的影响，但鱼和熊掌不可兼得，但力求影响最小的情况下初始化。

        最简单的初始化方法： * {padding: 0; margin: 0;} （强烈不建议）

        淘宝的样式初始化代码：
        body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, form, fieldset, legend, button, input, textarea, th, td { margin:0; padding:0; }
        body, button, input, select, textarea { font:12px/1.5tahoma, arial, \5b8b\4f53; }
        h1, h2, h3, h4, h5, h6{ font-size:100%; }
        address, cite, dfn, em, var { font-style:normal; }
        code, kbd, pre, samp { font-family:couriernew, courier, monospace; }
        small{ font-size:12px; }
        ul, ol { list-style:none; }
        a { text-decoration:none; }
        a:hover { text-decoration:underline; }
        sup { vertical-align:text-top; }
        sub{ vertical-align:text-bottom; }
        legend { color:#000; }
        fieldset, img { border:0; }
        button, input, select, textarea { font-size:100%; }
        table { border-collapse:collapse; border-spacing:0; }

        主要有reset，normalize，neat三种思路：reset是清除所有浏览器的默认样式并在所有浏览器保持一致；normalize是使用一种浏览器的默认样式并在所有浏览器保持一致；neat是前两种的结合，但仍在所有浏览器中保持一致

- absolute的containing block(容器块)计算方式跟正常流有什么不同？

        无论属于哪种，都要先找到其祖先元素中最近的 position 值不为 static 的元素，然后再判断：
        1、若此元素为 inline 元素，则 containing block 为能够包含这个元素生成的第一个和最后一个 inline box 的 padding box (除 margin, border 外的区域) 的最小矩形；
        2、否则,则由这个祖先元素的 padding box 构成。
        如果都找不到，则为 initial containing block。

        补充：
        1. static(默认的)/relative：简单说就是它的父元素的内容框（即去掉padding的部分）
        2. absolute: 向上找最近的定位为absolute/relative的元素
        3. fixed: 它的containing block一律为根元素(html/body)，根元素也是initial containing block

- CSS里的visibility属性有个collapse属性值是干嘛用的？在不同浏览器下以后什么区别？

- float、BFC、伪对象、和额外对象

- position跟display、margin collapse、overflow、float这些特性相互叠加后会怎么样？

- 对BFC规范(块级格式化上下文：block formatting context)的理解？

        In a block formatting context, each box's left outer edge touches the left edge of the containing block (for right-to-left formatting, right edges touch). This is true even in the presence of floats (although a box's line boxes may shrink due to the floats), unless the box establishes a new block formatting context (in which case the box itself may become narrower due to the floats).  http://www.w3.org/TR/CSS21/visuren.html#block-formatting

        在bfc中，每个元素的左外边与子元素的最左外边缘重合（其它边类似），即父元素为最小包含所有子元素的容器，float元素也包含，除非里面有新的bfc元素。
        
         不同类型的 Box,会参与不同的 Formatting Context（决定如何渲染文档的容器）,因此Box内的元素会以不同的方式渲染,也就是说BFC内部的元素和外部的元素不会互相影响。
         
- css定义的权重

        以下是权重的规则：标签的权重为1，class的权重为10，id的权重为100，以下例子是演示各种定义的权重值：

        /*权重为1*/
        div{
        }
        /*权重为10*/
        .class1{
        }
        /*权重为100*/
        #id1{
        }
        /*权重为100+1=101*/
        #id1 div{
        }
        /*权重为10+1=11*/
        .class1 div{
        }
        /*权重为10+10+1=21*/
        .class1 .class2 div{
        }
        如果权重相同，则最后定义的样式会起作用，但是应该避免这种情况出现


- 请解释一下为什么会出现浮动和什么时候需要清除浮动？清除浮动的方式

        设置了float属性的元素脱离了文档流，原来的地方被其他元素填充或塌陷，导致父元素的大小不再由float的元素决定，发生大小变化或塌陷而导致布局混乱。清浮动常见几种思路如下：
        1. overflow设置为非visible，触发bfc
        2. 后面加上空的div，样式加上 clear:both
        3. 设置父元素after为clear:both
        4. 手动设置父元素高度，使之在视觉上包含float的元素
        5. 设置after元素的clear: both; display: table

        总结最优方案：
        .floatfix{
            *zoom:1;
        }
        
        .floatfix:after{
            content:"";
            display:table;
            clear:both;
        }

- 移动端的布局用过媒体查询吗？

        一般用到根据屏宽和屏幕分辨率来进行适应处理。
    
- 使用 CSS 预处理器吗？喜欢那个？

        SASS (SASS、LESS没有本质区别，只因为团队前端都是用的SASS)

- CSS优化、提高性能的方法有哪些？

- 浏览器是怎样解析CSS选择器的？

        从右往左解析。效率更好。如果是从左至右，那要遍历每一个子节点进行选择，从右往左得每一步都可以过滤掉很多的元素。
        如果正向解析，例如 div div p em ，我们首先就要检查当前元素到 html 的整条路径，找到最上层的 div，再往下找，如果遇到不匹配就必须回到最上层那个 div，往下再去匹配选择器中的第一个 div，回溯若干次才能确定匹配与否，效率很低。逆向匹配则不同，如果当前的 DOM 元素是 div，而不是 selector 最后的 em，那只要一步就能排除。只有在匹配时，才会不断向上找父节点进行验证。

- 在网页中的应该使用奇数还是偶数的字体？为什么呢？

        Windows 自带的点阵宋体（中易宋体）从 Vista 开始只提供 12、14、16 px 这三个大小的点阵，而 13、15、17 px 时用的是小一号的点阵（即每个字占的空间大了 1 px，但点阵没变），于是略显稀疏。
        
- margin和padding分别适合什么场景使用？

        magin用于设置一个元素与另一个元素的距离，padding用于设置一个元素内容与边缘空白的距离 
    
- 抽离样式模块怎么写，说出思路，有无实践经验？[阿里航旅的面试题]

        公共样式，公共组件样式，特定组件样式。
    
- 元素竖向的百分比设定是相对于容器的高度吗？

        相对于父元素的高度。
    
- 全屏滚动的原理是什么？用到了CSS的那些属性？

        图片轮播原理，只不过图片宽高100%、超出隐藏、调整比例适应屏幕大小

- 什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的IE？

        网页适应不同尺寸或平台的设备而不会导致排版功能上混乱，并保持较好的使用体验。根据不同尺寸或平台展示不同的网页结构、样式、行为。

- 视差滚动效果，如何给每页做不同的动画？（回到顶部，向下滑动要再次出现，和只出现一次分别怎么做？）

- ::before 和 :after中双冒号和单冒号 有什么区别？解释一下这2个伪元素的作用。

        :: 为css3的伪元素，:为伪类，:active、:link、:hover为伪类，是将样式应用到一些特殊状态的元素上；:first-letter、:before、:after为伪元素，是将特殊的内容插入到文本中。在元素的前后插入一个假的元素。

- 如何修改chrome记住密码后自动填充表单的黄色背景 ？

        input : -webkit-autofill {
            background-color : #FAFFBD ;
            background-image : none ;
            color : #000 ;
        }

- 你对line-height是如何理解的？

        line-height指容器内放置内容的行高，该属性会影响行框的布局。在应用到一个块级元素时，它定义了该元素中基线之间的最小距离而不是最大距离。

- 设置元素浮动后，该元素的display值是多少？

        自动变成display:block

- 怎么让Chrome支持小于12px 的文字？

        transfrome: scale(0.5)
        
- 让页面里的字体变清晰，变细用CSS怎么做？

        -webkit-font-smoothing: antialiased;

- position:fixed;在android下无效怎么处理？

        加上viewport，让窗口适应屏幕

- 如果需要手动写动画，你认为最小时间间隔是多久，为什么？（阿里）

        多数显示器默认频率是60Hz，即1秒刷新60次，所以理论上最小间隔为1/60＊1000ms ＝ 16.7ms

- display:inline-block 什么时候会显示间隙？(携程)

        移除空格、使用margin负值、使用font-size:0、letter-spacing、word-spacing

- overflow: scroll时不能平滑滚动的问题怎么处理？

        使用iscroll等插件

- 有一个高度自适应的div，里面有两个div，一个高度100px，希望另一个填满剩下的高度。

        border-box，position: absolute，flex

- png、jpg、gif 这些图片格式解释一下，分别什么时候用。有没有了解过webp？


## <a name='js'>JavaScript</a>

-  介绍js的基本数据类型。

         Undefined、Null、Boolean、Number、String。数据类型包含Object，Object不是基本数据类型

-  介绍js有哪些内置对象？

        Object 是 JavaScript 中所有对象的父对象

        数据封装类对象：Object、Array、Boolean、Number 和 String
        其他对象：Function、Arguments、Math、Date、RegExp、Error
        
-  数组操作的方法常用哪几种？slice和splice的区别？split和join的区别

        push、pop、shift、unshift、slice、splice、join。
        slice是截取子串，splice是替代子串，split是分割字符串为数组，join是将数组内容连接为字符串。

        数据封装类对象：Object、Array、Boolean、Number 和 String
        其他对象：Function、Arguments、Math、Date、RegExp、Error
        
-  说几条写JavaScript的基本规范？

        1.不要在同一行声明多个变量。
        2.请使用 ===/!==来比较true/false或者数值
        3.使用对象字面量替代new Array这种形式
        4.不要使用全局函数。
        5.Switch语句必须带有default分支
        6.函数不应该有时候有返回值，有时候没有返回值。
        7.For循环必须使用大括号
        8.If语句必须使用大括号
        9.for-in循环中的变量 应该使用var关键字明确限定作用域，从而避免作用域污染。

-  JavaScript原型，原型链 ? 有什么特点？

        每个对象都会在其内部初始化一个属性，就是prototype(原型)，当我们访问一个对象的属性时，
        如果这个对象内部不存在这个属性，那么他就会去prototype里找这个属性，这个prototype又会有自己的prototype，
        于是就这样一直找下去，也就是我们平时所说的原型链的概念。
        关系：instance.constructor.prototype = instance.__proto__

        特点：继承更改
        JavaScript对象是通过引用来传递的，我们创建的每个新对象实体中并没有一份属于自己的原型副本。当我们修改原型时，与之相关的对象也会继承这一改变。

         当我们需要一个属性的时，Javascript引擎会先看当前对象中是否有这个属性， 如果没有的话，
         就会查找他的Prototype对象是否有这个属性，如此递推下去，一直检索到Object内建对象。
            function Func(){}
            Func.prototype.name = "Sean";
            Func.prototype.getInfo = function() {
              return this.name;
            }
            var person = new Func();//现在可以参考var person = Object.create(oldObject);
            console.log(person.getInfo());//它拥有了Func的属性和方法
            //"Sean"
            console.log(Func.prototype);
            // Func { name="Sean", getInfo=function()}


            

-  JavaScript有几种类型的值？，你能画一下他们的内存图吗？

        栈：原始数据类型（Undefined，Null，Boolean，Number、String） 
        堆：引用数据类型（对象、数组和函数）

        两种类型的区别是：存储位置不同；
        原始数据类型直接存储在栈(stack)中的简单数据段，占据空间小、大小固定，属于被频繁使用数据，所以放入栈中存储；
        引用数据类型存储在堆(heap)中的对象,占据空间大、大小不固定,如果存储在栈中，将会影响程序运行的性能；引用数据类型在栈中存储了指针，该指针指向堆中该实体的起始地址。当解释器寻找引用值时，会首先检索其
        在栈中的地址，取得地址后从堆中获得实体
        
    ![Stated Clearly Image](http://www.w3school.com.cn/i/ct_js_value.gif)

-  Javascript如何实现继承？

        1、构造继承
        2、原型继承
        3、实例继承
        4、拷贝继承

        原型prototype机制或apply和call方法去实现较简单，建议使用构造函数与原型混合方式。
            
         function Parent(){
                this.name = 'wang';
            }
        
            function Child(){
                this.age = 28;
            }
            Child.prototype = new Parent();//继承了Parent，通过原型
        
            var demo = new Child();
            alert(demo.age);
            alert(demo.name);//得到被继承的属性
          }

-  javascript创建对象的几种方式？

        javascript创建对象简单的说,无非就是使用内置对象或各种自定义对象，当然还可以用JSON；但写法有很多种，也能混合使用。


        1、对象字面量的方式   

            person={firstname:"Mark",lastname:"Yun",age:25,eyecolor:"black"};

        2、用function来模拟无参的构造函数

            function Person(){}
            var person=new Person();//定义一个function，如果使用new"实例化",该function可以看作是一个Class
            person.name="Mark";
            person.age="25";
            person.work=function(){
            alert(person.name+" hello...");
            }
            person.work();

        3、用function来模拟参构造函数来实现（用this关键字定义构造的上下文属性）

            function Pet(name,age,hobby){
               this.name=name;//this作用域：当前对象
               this.age=age;
               this.hobby=hobby;
               this.eat=function(){
                  alert("我叫"+this.name+",我喜欢"+this.hobby+",是个程序员");
               }
            }
            var maidou =new Pet("麦兜",25,"coding");//实例化、创建对象
            maidou.eat();//调用eat方法


        4、用工厂方式来创建（内置对象）
    
             var wcDog =new Object();
             wcDog.name="旺财";
             wcDog.age=3;
             wcDog.work=function(){
               alert("我是"+wcDog.name+",汪汪汪......");
             }
             wcDog.work();


        5、用原型方式来创建

            function Dog(){
            
             }
             Dog.prototype.name="旺财";
             Dog.prototype.eat=function(){
             alert(this.name+"是个吃货");
             }
             var wangcai =new Dog();
             wangcai.eat();


        5、用混合方式来创建

            function Car(name,price){
              this.name=name;
              this.price=price; 
            }
             Car.prototype.sell=function(){
               alert("我是"+this.name+"，我现在卖"+this.price+"万元");
              }
            var camry =new Car("凯美瑞",27);
            camry.sell(); 

-  Javascript作用链域?

        全局函数无法查看局部函数的内部细节，但局部函数可以查看其上层的函数细节，直至全局细节。
        当需要从局部函数查找某一属性或方法时，如果当前作用域没有找到，就会上溯到上层作用域查找，
        直至全局函数，这种组织形式就是作用域链。

-  谈谈js中This对象的理解。匿名函数的this和构造函数的this的区别？
    
        js中的this值创建当前对象的环境对象。浏览器中，匿名函数的this始终执行window。

-  eval是做什么的？

        它的功能是把对应的字符串解析成JS代码并运行；
        应该避免使用eval，不安全，非常耗性能（2次，一次解析成js语句，一次执行）。

-  什么是window对象? 什么是document对象?

        window是浏览器全局对象，执行浏览器宿主环境全局；document指文档对象。

-  null，undefined 的区别？

        null        表示一个对象被定义了，值为“空值”；
        undefined   表示不存在这个值。


        typeof undefined
            //"undefined"
            undefined :是一个表示"无"的原始值或者说表示"缺少值"，就是此处应该有一个值，但是还没有定义。当尝试读取时会返回 undefined； 
            例如变量被声明了，但没有赋值时，就等于undefined

        typeof null
            //"object"
            null : 是一个对象(空对象, 没有任何属性和方法)；
            例如作为函数的参数，表示该函数的参数不是对象；
    
        注意：
            在验证null时，一定要使用　=== ，因为 == 无法分别 null 和　undefined

        
        再来一个例子：
            null
            Q：有张三这个人么？
            A：有！
            Q：张三有房子么？
            A：没有！
    
            undefined
            Q：有张三这个人么？
            A：没有！

- js保留两位小数的方法
  
    // toFixed 有精度问题，js里面的toFixed保留小数的时候，是四舍五入的，但是项目需求是不要四舍五入，即：小数点后第三位如果有值则进一
      0.235.toFixed(2) 输出0.23
      0.236.toFixed(2) 输出0.24
    
      var bb = num+"";
      var dian = bb.indexOf('.');
      var result = "";
      if(dian == -1){
        result =  num.toFixed(2);
      }else{
        var cc = bb.substring(dian+1,bb.length);
        if(cc.length >=3){
          result =  (Number(num.toFixed(2))+0.01);  //注意这里就好了
        }else{
          result =  num.toFixed(2);
        }
      }
      alert(result);
  
- 实现一个银行卡号四位放一个空格的功能

    this.value.replace(/\s/g,'').replace(/(\d{4})(?=\d)/g,"$1 ") 或
    this.value.replace(/(\d{4})/g,"$1 ").replace(/\s$/,'')

    (?=)会作为匹配校验，但不会出现在匹配结果字符串里面
    (?:)会作为匹配校验，并出现在匹配结果字符里面，它跟(?=)不同的地方在于，不作为子匹配返回

- 页面无刷新上传的两种实现原理

    formData与iframe，用了uploadify.js的需要了解下。XMLHttpRequest Level 2 添加了一个新的接口——FormData。利用 FormData 对象，我们可以通过 JavaScript 用一些键值对来模拟一系列表单控件，我们还可以使用 XMLHttpRequest 的 send() 方法来异步的提交表单。与普通的 Ajax 相比，使用 FormData 的最大优点就是我们可以异步上传二进制文件。

-  写一个通用的事件侦听器函数。

            // event(事件)工具集，来源：github.com/markyun
            markyun.Event = {
                // 页面加载完成后
                readyEvent : function(fn) {
                    if (fn==null) {
                        fn=document;
                    }
                    var oldonload = window.onload;
                    if (typeof window.onload != 'function') {
                        window.onload = fn;
                    } else {
                        window.onload = function() {
                            oldonload();
                            fn();
                        };
                    }
                },
                // 视能力分别使用dom0||dom2||IE方式 来绑定事件
                // 参数： 操作的元素,事件名称 ,事件处理程序
                addEvent : function(element, type, handler) {
                    if (element.addEventListener) {
                        //事件类型、需要执行的函数、是否捕捉
                        element.addEventListener(type, handler, false);
                    } else if (element.attachEvent) {
                        element.attachEvent('on' + type, function() {
                            handler.call(element);
                        });
                    } else {
                        element['on' + type] = handler;
                    }
                },
                // 移除事件
                removeEvent : function(element, type, handler) {
                    if (element.removeEventListener) {
                        element.removeEventListener(type, handler, false);
                    } else if (element.datachEvent) {
                        element.detachEvent('on' + type, handler);
                    } else {
                        element['on' + type] = null;
                    }
                },
                // 阻止事件 (主要是事件冒泡，因为IE不支持事件捕获)
                stopPropagation : function(ev) {
                    if (ev.stopPropagation) {
                        ev.stopPropagation();
                    } else {
                        ev.cancelBubble = true;
                    }
                },
                // 取消事件的默认行为
                preventDefault : function(event) {
                    if (event.preventDefault) {
                        event.preventDefault();
                    } else {
                        event.returnValue = false;
                    }
                },
                // 获取事件目标
                getTarget : function(event) {
                    return event.target || event.srcElement;
                },
                // 获取event对象的引用，取到事件的所有信息，确保随时能使用event；
                getEvent : function(e) {
                    var ev = e || window.event;
                    if (!ev) {
                        var c = this.getEvent.caller;
                        while (c) {
                            ev = c.arguments[0];
                            if (ev && Event == ev.constructor) {
                                break;
                            }
                            c = c.caller;
                        }
                    }
                    return ev;
                }
            };

-  ["1", "2", "3"].map(parseInt) 答案是多少？

         [1, NaN, NaN] 因为 parseInt 需要两个参数 (val, radix)，其中 radix 表示解析时用的基数。
         map 传了 3 个 (element, index, array)，对应的 radix 不合法导致解析失败。parseInt(string, radix)中，如果该参数小于 2 或者大于 36，则 ‘parseInt()‘ 将返回 ‘NaN‘，第二个解析失败，后面的均解析失败

-  事件模型？IE与火狐的事件机制有什么区别？ 如何阻止冒泡？

         1. 我们在网页中的某个操作（有的操作对应多个事件）。例如：当我们点击一个按钮就会产生一个事件。是可以被 JavaScript 侦测到的行为。
         2. 事件处理机制：IE是事件冒泡、Firefox同时支持两种事件模型，也就是：捕获型事件和冒泡型事件；
         3. ev.stopPropagation();（旧ie的方法 ev.cancelBubble = true;）


-  什么是闭包（closure），为什么要用它？

        闭包是指有权访问另一个函数作用域中变量的函数，创建闭包的最常见的方式就是在一个函数内创建另一个函数，通过另一个函数访问这个函数的局部变量,利用闭包可以突破作用链域，将函数内部的变量和方法传递到外部。

        闭包的特性：

        1.函数内再嵌套函数
        2.内部函数可以引用外层的参数和变量
        3.参数和变量不会被垃圾回收机制回收

        //li节点的onclick事件都能正确的弹出当前被点击的li索引
         <ul id="testUL">
            <li> index = 0</li>
            <li> index = 1</li>
            <li> index = 2</li>
            <li> index = 3</li>
        </ul>
        <script type="text/javascript">
            var nodes = document.getElementsByTagName("li");
            for(i = 0;i<nodes.length;i+= 1){
                nodes[i].onclick = function(){
                    console.log(i+1);//不用闭包的话，值每次都是4
                }(i);
            }
        </script>



        执行say667()后,say667()闭包内部变量会存在,而闭包内部函数的内部变量不会存在
        使得Javascript的垃圾回收机制GC不会收回say667()所占用的资源
        因为say667()的内部函数的执行需要依赖say667()中的变量
        这是对闭包作用的非常直白的描述

          function say667() {
            // Local variable that ends up within closure
            var num = 666;
            var sayAlert = function() {
                alert(num);
            }
            num++;
            return sayAlert;
        }

         var sayAlert = say667();
         sayAlert()//执行结果应该弹出的667


-  javascript 代码中的"use strict";是什么意思 ? 使用它区别是什么？

        use strict是一种ECMAscript 5 添加的（严格）运行模式,这种模式使得 Javascript 在更严格的条件下运行,

        使JS编码更加规范化的模式,消除Javascript语法的一些不合理、不严谨之处，减少一些怪异行为。
        默认支持的糟糕特性都会被禁用，比如不能用with，也不能在意外的情况下给全局变量赋值;
        全局变量的显示声明,函数必须声明在顶层，不允许在非函数代码块内声明函数,arguments.callee也不允许使用；
        消除代码运行的一些不安全之处，保证代码运行的安全,限制函数中的arguments修改，严格模式下的eval函数的行为和非严格模式的也不相同;

        提高编译器效率，增加运行速度；
        为未来新版本的Javascript标准化做铺垫。


-  如何判断一个对象是否属于某个类？

          使用instanceof （待完善）
           if(a instanceof Person){
               alert('yes');
           }

-  new操作符具体干了什么呢?

             1、创建一个空对象，并且 this 变量引用该对象，同时还继承了该函数的原型。
             2、属性和方法被加入到 this 引用的对象中。
             3、新创建的对象由 this 所引用，并且最后隐式的返回 this 。

        var obj  = {};
        obj.__proto__ = Base.prototype;
        Base.call(obj);


-  用原生JavaScript的实现过什么功能吗？


-  Javascript中，有一个函数，执行时对象查找时，永远不会去查找原型，这个函数是？

        hasOwnProperty

        javaScript中hasOwnProperty函数方法是返回一个布尔值，指出一个对象是否具有指定名称的属性。此方法无法检查该对象的原型链中是否具有该属性；该属性必须是对象本身的一个成员。
        使用方法：
        object.hasOwnProperty(proName)
        其中参数object是必选项。一个对象的实例。
        proName是必选项。一个属性名称的字符串值。

        如果 object 具有指定名称的属性，那么JavaScript中hasOwnProperty函数方法返回 true，反之则返回 false。

-  JSON 的了解？

        JSON(JavaScript Object Notation) 是一种轻量级的数据交换格式。
        它是基于JavaScript的一个子集。数据格式简单, 易于读写, 占用带宽小
        如：{"age":"12", "name":"back"}

-  `[].forEach.call($$("*"),function(a){a.style.outline="1px solid #"+(~~(Math.random()*(1<<24))).toString(16)})` 能解释一下这段代码的意思吗？

        设置页面所有元素的outline添加一个随机颜色的边框。

- javascript的内存泄露？
        
        全局变量引起泄露
        function leaks(){  
            leak = 'xxxxxx';//leak 成为一个全局变量，不会被回收
        }
    
        闭包引起泄露
        var leaks = (function(){  
            var leak = 'xxxxxx';// 被闭包所引用，不会被回收
            return function(){
                console.log(leak);
            }
        })()

        dom清空或删除时，事件未清除导致的内存泄漏
        <div id="container"> </div>
            
            $('#container').bind('click', function(){
                console.log('click');
            }).remove();
            
        dom对象应用了js对象，js对象应用到dom对象造成循环引用
        
            // zepto 和原生 js下，#container dom 元素，还在内存里jquery 的 empty和 remove会帮助开发者避免这个问题
            
          1. 单纯的JS Engine Object的Circular References、Closures是不会引起内存泄漏；
          2. 单纯的DOM Element的Circular References只会引起当前页面的内存泄漏；
          3. JS Engine Object 和 DOM Element的Circular References、Closures会引起跨页面的内存泄漏；
          4. 将DOM Element直接追加到DOM Tree中，可减少temporary scope的创建和丢弃；
          5. CollectGarbage()不是万金油。

- js执行时的预处理与预执行？

        js预处理阶段，将扫描变与函数声明，执行阶段进行赋值和函数调用。

- js怎样获取操作cookie？

        document.cookie

- js对象prototype，__proto__，constructor和this的区别与联系？

        所有构造器/函数的__proto__都指向Function.prototype，它是一个空函数（Empty function）；所有对象的__proto__都指向其构造器的prototype。this指向申明构造函数的当前执行上下文对象，constructor值构造器函数。

- ajax中 xhrFields: { withCredentials: true } 有什么作用？

        告诉xhr对象在发送ajax时带上cookie信息
    
- javascript void(0)、return false和e.preventDefault()区别

        void(0)表示什么也不做阻止便签默认行为，但ie6下会使gif动画失效，return false指跳出执行，默认行为依然会触发，e.preventDefault指阻止标签的默认事件。
        
- property和attribute、encodeURI和encodeURIComponent、prop()和attr()的区别

        property是dom对象的属性，而attribute是html便签的属性，例如style是property一直存在的，但是不一定是attribute。prop()和attr()是jquery获取两种不同属性的方法。encodeURI编码的符号集合更广，会对特殊符号转移，encodeURIComponent则不会。
        
- jquery中this和$(this)的区别？

        js对象与jquery对象。

- 正则式贪婪匹配和懒惰匹配各是什么？如何实现？
- 什么是正则式？写出一个合法url地址的匹配规则
- js在ie与firefox下的兼容性有哪些？
- 元素div.setAttribute("title","XX")和div.title="XX"两种写法的区别?

        div.setAttribute可以设置非原生属性，div.title方式只能设置原生属性。

-  Ajax 是什么? 如何创建一个Ajax？

        ajax的全称：Asynchronous Javascript And XML。异步传输+js+xml。
        所谓异步，在这里简单地解释就是：向服务器发送请求的时候，我们不必等待结果，而是可以同时做其他的事情，等到有了结果它自己会根据设定进行后续操作，与此同时，页面是不会发生整页刷新的，提高了用户体验。

        (1)创建XMLHttpRequest对象,也就是创建一个异步调用对象
        (2)创建一个新的HTTP请求,并指定该HTTP请求的方法、URL及验证信息
        (3)设置响应HTTP请求状态变化的函数
        (4)发送HTTP请求
        (5)获取异步调用返回的数据
        (6)使用JavaScript和DOM实现局部刷新

-  同步和异步的区别?

    同步：浏览器访问服务器请求，用户看得到页面刷新，重新发请求,等请求完，页面刷新，新内容出现，用户看到新内容,j进行下一步操作。

    异步：浏览器访问服务器请求，用户正常操作，浏览器后端进行请求。等请求完，页面不刷新，新内容也会出现，用户看到新内容。

-  如何解决跨域问题?

        jsonp、 iframe、window.name、window.postMessage、服务器上设置Access-Control-Allow-Origin

- xss、csrf、sql注入的各自防护措施是什么？

- 什么是xss?什么是csrf?两者的区别和联系是什么？

- http协议get和post有什么区别？请求的参数有什么区别？

- PC端优化和H5优化有什么区别？

- 为什么静态文件要分域并行下载？

        1. 增加并行数，浏览器单个域文件下载线程数有限制，IE6为2，一般为4个，分域可以突破限制。
        2. 进行cookie隔离。避免cookie信息带入请求中，减少请求大小，提高了webserver的http请求的解析速度

- 列举Yslow23条优化规则?每条规则的优化依据？

## <a name='html'>工程化</a>

-  模块化开发怎么做？

     [ 立即执行函数](http://benalman.com/news/2010/11/immediately-invoked-function-expression/),不暴露私有成员

            var module1 = (function(){
            　　　　var _count = 0;
            　　　　var m1 = function(){
            　　　　　　//...
            　　　　};
            　　　　var m2 = function(){
            　　　　　　//...
            　　　　};
            　　　　return {
            　　　　　　m1 : m1,
            　　　　　　m2 : m2
            　　　　};
            　　})();

    （待完善）

-  AMD（Modules/Asynchronous-Definition）、CMD（Common Module Definition）规范区别？

    > AMD 规范在这里：https://github.com/amdjs/amdjs-api/wiki/AMD

    > CMD 规范在这里：https://github.com/seajs/seajs/issues/242

        Asynchronous Module Definition，异步模块定义，所有的模块将被异步加载，模块加载不影响后面语句运行。所有依赖某些模块的语句均放置在回调函数中。

         区别：

            1. 对于依赖的模块，AMD 是提前执行，CMD 是延迟执行。不过 RequireJS 从 2.0 开始，也改成可以延迟执行（根据写法不同，处理方式不同）。CMD 推崇 as lazy as possible.
            2. CMD 推崇依赖就近，AMD 推崇依赖前置。看代码：

        // CMD
        define(function(require, exports, module) {
            var a = require('./a')
            a.doSomething()
            // 此处略去 100 行
            var b = require('./b') // 依赖可以就近书写
            b.doSomething()
            // ...
        })

        // AMD 默认推荐
        define(['./a', './b'], function(a, b) { // 依赖必须一开始就写好
            a.doSomething()
            // 此处略去 100 行
            b.doSomething()
            // ...
        })


-  requireJS的核心原理是什么？（如何动态加载的？如何避免多次加载的？如何
缓存的？）
    
        动态加载引入模块化js模块，暂存在数组中，等到需要的模块加载都完成后执行。
    

-  谈一谈你对ECMAScript6的了解？

        高效新特性、兼容性、开发体系，面向未来。

- grunt、gulp构建任务用过没？有什么区别

- 前端页面有哪三层构成，分别是什么?作用是什么?

- http下载一个文件的过程是怎样的？判断文件缓存过期有哪两种控制方法？

- http协议头部cache-control字段和expires字段的意思？

- 浏览器端数据存储的方式有哪几种？（cookie、localstorage、indexDB）

- 什么是跨域？跨域的方式有哪些？

- 浏览器调试与dev tool使用和请求、资源查看?

-  ECMAScript6 怎么写class么，为什么会出现class这种东西?

        javascript没有真正意义上的class，使用class有点，完善封装性。 

-  异步加载JS（延时加载）的方式有哪些？

          1. defer，只支持IE
          2. async
          3. 动态创建script插入到dom中
          4. 按需加载

- documen.write和 innerHTML的区别

        document.write只能重绘整个页面
        innerHTML可以重绘页面的一部分

- DOM操作——怎样添加、移除、移动、复制、创建和查找节点?

        （1）创建新节点
          createDocumentFragment()    //创建一个DOM片段
          createElement()   //创建一个具体的元素
          createTextNode()   //创建一个文本节点
        （2）添加、移除、替换、插入
          appendChild()
          removeChild()
          replaceChild()
          insertBefore() //在已有的子节点前插入一个新的子节点
        （3）查找
          getElementsByTagName()    //通过标签名称
          getElementsByName()    //通过元素的Name属性的值(IE容错能力较强，会得到一个数组，其中包括id等于name值的)
          getElementById()    //通过元素Id，唯一性

-  .call() 和 .apply() 的区别？

          call的传入参数有多个，apply的传入参数第二个为数组

-  数组和对象有哪些原生方法，列举一下？

-  JS 怎么实现一个类。怎么实例化这个类

-  JavaScript中的作用域与变量声明提升？

-  如何编写高性能的Javascript？

-  JQuery的源码看过吗？能不能简单概况一下它的实现原理？

-  jQuery.fn的init方法返回的this指的是什么对象？为什么要返回this？

-  jquery中如何将数组转化为json字符串，然后再转化回来？

-  jQuery 的属性拷贝(extend)的实现原理是什么，如何实现深拷贝？ 

-  jquery.extend 与 jquery.fn.extend的区别？

-  jQuery 的队列是如何实现的？队列可以用在哪些地方？

-  谈一下Jquery中的bind(),live(),delegate(),on()的区别？

-  JQuery一个对象可以同时绑定多个事件，这是如何实现的？

-  是否知道自定义事件。jQuery里的fire函数是什么意思，什么时候用？

-  jQuery 是通过哪个方法和 Sizzle 选择器结合的？（jQuery.fn.find()进入Sizzle）

-  针对 jQuery性能的优化方法？

-  Jquery与jQuery UI 有啥区别？


        *jQuery是一个js库，主要提供的功能是选择器，属性修改和事件绑定等等。

        *jQuery UI则是在jQuery的基础上，利用jQuery的扩展性，设计的插件。
         提供了一些常用的界面元素，诸如对话框、拖动行为、改变大小行为等等


-  JQuery的源码看过吗？能不能简单说一下它的实现原理？

-  jquery 中如何将数组转化为json字符串，然后再转化回来？

jQuery中没有提供这个功能，所以你需要先编写两个jQuery的扩展：

        $.fn.stringifyArray = function(array) {
            return JSON.stringify(array)
        }
        $.fn.parseArray = function(array) {
            return JSON.parse(array)
        }
        然后调用：
        $("").stringifyArray(array)

-  针对 jQuery 的优化方法？

        *基于Class的选择性的性能相对于Id选择器开销很大，因为需遍历所有DOM元素。

        *频繁操作的DOM，先缓存起来再操作。用Jquery的链式调用更好。
         比如：var str=$("a").attr("href");

        *for (var i = size; i < arr.length; i++) {}
         for 循环每一次循环都查找了数组 (arr) 的.length 属性，在开始循环的时候设置一个变量来存储这个数字，可以让循环跑得更快：
         for (var i = size, length = arr.length; i < length; i++) {}


-  Zepto的点透问题如何解决？

-  jQueryUI如何自定义组件?

-  需求：实现一个页面操作不会整页刷新的网站，并且能在浏览器前进、后退时正确响应。给出你的技术实现方案？

- 如何判断当前脚本运行在浏览器还是node环境中？（阿里）

        通过判断Global对象是否为window，如果不为window，当前脚本没有运行在浏览器中

-  移动端最小触控区域是多大？

-  jQuery 的 slideUp动画 ，如果目标元素是被外部事件驱动, 当鼠标快速地连续触发外部元素事件, 动画会滞后的反复执行，该如何处理呢?

-  把 Script 标签 放在页面的最底部的body封闭之前 和封闭之后有什么区别？浏览器会如何解析它们？

-  移动端的点击事件的有延迟，时间是多久，为什么会有？ 怎么解决这个延时？（click 有 300ms 延迟,为了实现safari的双击事件的设计，浏览器要知道你是不是要双击操作。）

-  知道各种JS框架(Angular, Backbone, Ember, React, Meteor, Knockout...)么? 能讲出他们各自的优点和缺点么?

-  Underscore 对哪些 JS 原生对象进行了扩展以及提供了哪些好用的函数方法？

-  解释JavaScript中的作用域与变量声明提升？

-  那些操作会造成内存泄漏？

        内存泄漏指任何对象在您不再拥有或需要它之后仍然存在。
        垃圾回收器定期扫描对象，并计算引用了每个对象的其他对象的数量。如果一个对象的引用数量为 0（没有其他对象引用过该对象），或对该对象的惟一引用是循环的，那么该对象的内存即可回收。

        setTimeout 的第一个参数使用字符串而非函数的话，会引发内存泄漏。
        闭包、控制台日志、循环（在两个对象彼此引用且彼此保留时，就会产生一个循环）

-  JQuery一个对象可以同时绑定多个事件，这是如何实现的？

-  Node.js的适用场景？

-  (如果会用node)知道route, middleware, cluster, nodemon, pm2, server-side rendering么?

-  解释一下 Backbone 的 MVC 实现方式？
    
- 什么是“前端路由”?什么时候适合使用“前端路由”? “前端路由”有哪些优点和缺点?

    同一个页面，根据不同的参数或hash后缀加载不同的内容。适合SPA。
    使用前端页面无刷新，体验好，但不利于SEO，单个页面内容庞杂，可能难以维护。

- 用js实现千位分隔符?(来源：[前端农民工](http://div.io/topic/744)，提示：正则+replace)

    function commafy(num) {
       num = num + '';
       var reg = /(-?d+)(d{3})/;
      
      if(reg.test(num)){
       num = num.replace(reg, '$1,$2');
      }
      return num;
    }

  
- 检测浏览器版本版本有哪些方式？

    功能特性检测、userAgent检测

- promise的理解。
  
    promise用于处理异步编程中函数嵌套的场景。当有多个函数相互依赖的异步场景，而且处理时间比较长，会形成多层函数的不断嵌套，增加代码复杂度，解决方法是函数执行返回一个promise对象，对象有其它函数的方法，这样就更易懂。可以理解为异步嵌套的另一种形式的封装。

- ES6 let和const区别

    let声明的变量拥有块级作用域；
    let声明的全局变量不是全局对象的属性；
    形如for (let x...)的循环在每次迭代时都为x创建新的绑定；
    let声明的变量直到控制流到达该变量被定义的代码行时才会被装载，所以在到达之前使用该变量会触发错误；
    用let重定义变量会抛出一个语法错误（SyntaxError）；

    const声明的变量与let声明的变量类似，它们的不同之处在于，const声明的变量只可以在声明时赋值，不可随意修改，否则会导致SyntaxError（语法错误）

- 原生js实现事件模型及事件代理/委托

- 实现Function.bind函数

- 将url的查询参数解析成字典对象

- 函数节流的实现原理

- 设计模式中的观察者模式、责任链模式、工厂模式的实现原理

## <a name='other'>编程题</a>

- 动态创建一个ul列表，然后将li反序
- 实现类的继承？
- 自适应三列布局，左右定宽，中间自适应？
- 实现一个右键菜单，点击左键或其它地方消失？
- js原生实现事件绑定方法？要求兼容ie和chrome?
- 实现一个方块从浏览器左边移动到右边，再回到左边的循环动画？
- 实现一个Animal类，type属性为animal，实现一个Dog继承Animal，catogery属性为dog，用Dog类生成一个Mydog实例，name属性为Bolt？（尽量用多种方法实现）
- js实现选择排序算法?（或者其它的排序算法）
- 统计一个页面的打开次数，要求每次每次刷新，打开次数加1？
- 实现两个大数相加的函数？例如1862836423423423486348+8236483927349234
- 实现一个输入框的实时输入搜索功能？即自动补全功能
- js原生一个div元素的拖拽效果？
- 原生实现ajax请求函数？
- 新建一个ul元素，往里面插入1000个li元素。完成后再将这1000个li子元素倒序显示？(使用原生js实现)
- 计算目录/a/b/c/d/e.js和/a/b/f/g.js的相对目录？
- 数组元素统计方法，统一数组中各个元素出现的次数，使用O(1)复杂度算法？

## <a name='other'>其他问题</a>

- 自我介绍(介绍姓名，学院，主要项目经历，爱好即可，一到两分钟即可)

- 你还有什么其他问题？

- 做过哪些项目？描述下你做的最满意的项目？你在其中做了哪些事情？

- 你遇到过比较难的技术问题是？你是如何解决的？

- 是否接触过移动端h5开发？觉得和PC上的开发有什么区别？

- 平时用什么编辑器？觉得它哪里好？用过哪些插件？

- 原来公司工作流程是怎么样的，如何与其他人协作的？如何夸部门合作的？

- 设计模式 知道什么是singleton, factory, strategy, decrator么?

- 常使用的库有哪些？常用的前端开发工具？开发过什么应用或组件？

- 页面重构怎么操作？

        网站重构：在不改变外部行为的前提下，简化结构、添加可读性，而在网站前端保持一致的行为。
        也就是说是在不改变UI的情况下，对网站进行优化，在扩展的同时保持一致的UI。

        对于传统的网站来说重构通常是：

        表格(table)布局改为DIV+CSS
        使网站前端兼容于现代浏览器(针对于不合规范的CSS、如对IE6有效的)
        对于移动平台的优化
        针对于SEO进行优化
        深层次的网站重构应该考虑的方面

        减少代码间的耦合
        让代码保持弹性
        严格按规范编写代码
        设计可扩展的API
        代替旧有的框架、语言(如VB)
        增强用户体验
        通常来说对于速度的优化也包含在重构中

        压缩JS、CSS、image等前端资源(通常是由服务器来解决)
        程序的性能优化(如数据读写)
        采用CDN来加速资源加载
        对于JS DOM的优化
        HTTP服务器的文件缓存

- 列举IE与其他浏览器不一样的特性？

        1、事件不同之处：

            触发事件的元素被认为是目标（target）。而在 IE 中，目标包含在 event 对象的 srcElement 属性；
            
            获取字符代码、如果按键代表一个字符（shift、ctrl、alt除外），IE 的 keyCode 会返回字符代码（Unicode），DOM 中按键的代码和字符是分离的，要获取字符代码，需要使用 charCode 属性；

            阻止某个事件的默认行为，IE 中阻止某个事件的默认行为，必须将 returnValue 属性设置为 false，Mozilla 中，需要调用 preventDefault() 方法；

            停止事件冒泡，IE 中阻止事件进一步冒泡，需要设置 cancelBubble 为 true，Mozzilla 中，需要调用 stopPropagation()；
        

- 99%的网站都需要被重构是那本书上写的？

        网站重构：应用web标准进行设计（第2版）

- 什么叫优雅降级和渐进增强？

        优雅降级：Web站点在所有新式浏览器中都能正常工作，如果用户使用的是老式浏览器，则代码会针对旧版本的IE进行降级处理了,使之在旧式浏览器上以某种形式降级体验却不至于完全不能用。
        如：border-shadow

        渐进增强：从被所有浏览器支持的基本功能开始，逐步地添加那些只有新版本浏览器才支持的功能,向页面增加不影响基础浏览器的额外样式和功能的。当浏览器支持时，它们会自动地呈现出来并发挥作用。
        如：默认使用flash上传，但如果浏览器支持 HTML5 的文件上传功能，则使用HTML5实现更好的体验；

- 是否了解公钥加密和私钥加密。

        一般情况下是指私钥用于对数据进行签名，公钥用于对签名进行验证;
        HTTP网站在浏览器端用公钥加密敏感数据，然后在服务器端再用私钥解密。


- WEB应用从服务器主动推送Data到客户端有那些方式？

        html5提供的Websocket
        不可见的iframe
        WebSocket通过Flash
        XHR长时间连接
        XHR Multipart Streaming
        <script>标签的长时间连接(可跨域)

- 对Node的优点和缺点提出了自己的看法？

        *（优点）因为Node是基于事件驱动和无阻塞的，所以非常适合处理并发请求，
          因此构建在Node上的代理服务器相比其他技术实现（如Ruby）的服务器表现要好得多。
          此外，与Node代理服务器交互的客户端代码是由javascript语言编写的，
          因此客户端和服务器端都用同一种语言编写，这是非常美妙的事情。

        *（缺点）Node是一个相对新的开源项目，所以不太稳定，它总是一直在变，
          而且缺少足够多的第三方库支持。看起来，就像是Ruby/Rails当年的样子。


- 你有用过哪些前端性能优化的方法？

          （1） 减少http请求次数：CSS Sprites, JS、CSS源码压缩、图片大小控制合适；网页Gzip，CDN托管，data缓存 ，图片服务器。

          （2） 前端模板 JS+数据，减少由于HTML标签导致的带宽浪费，前端用变量保存AJAX请求结果，每次操作本地变量，不用请求，减少请求次数

          （3） 用innerHTML代替DOM操作，减少DOM操作次数，优化javascript性能。

          （4） 当需要设置的样式很多时设置className而不是直接操作style。

          （5） 少用全局变量、缓存DOM节点查找的结果。减少IO读取操作。

          （6） 避免使用CSS Expression（css表达式)又称Dynamic properties(动态属性)。

          （7） 图片预加载，将样式表放在顶部，将脚本放在底部  加上时间戳。

          （8） 避免在页面的主体布局中使用table，table要等其中的内容完全下载之后才会显示出来，显示比div+css布局慢。
          对普通的网站有一个统一的思路，就是尽量向前端优化、减少数据库操作、减少磁盘IO。向前端优化指的是，在不影响功能和体验的情况下，能在浏览器执行的不要在服务端执行，能在缓存服务器上直接返回的不要到应用服务器，程序能直接取得的结果不要到外部取得，本机内能取得的数据不要到远程取，内存能取到的不要到磁盘取，缓存中有的不要去数据库查询。减少数据库操作指减少更新次数、缓存结果减少查询次数、将数据库执行的操作尽可能的让你的程序完成（例如join查询），减少磁盘IO指尽量不使用文件系统作为缓存、减少读写文件次数等。程序优化永远要优化慢的部分，换语言是无法“优化”的。

- http状态码有那些？分别代表是什么意思？

            简单版
            [
                100  Continue   继续，一般在发送post请求时，已发送了http header之后服务端将返回此信息，表示确认，之后发送具体参数信息
                200  OK         正常返回信息
                201  Created    请求成功并且服务器创建了新的资源
                202  Accepted   服务器已接受请求，但尚未处理
                301  Moved Permanently  请求的网页已永久移动到新位置。
                302  Found          临时性重定向。
                303  See Other      临时性重定向，且总是使用 GET 请求新的 URI。
                304  Not Modified 自从上次请求后，请求的网页未修改过。

                400 Bad Request  服务器无法理解请求的格式，客户端不应当尝试再次使用相同的内容发起请求。
                401 Unauthorized 请求未授权。
                403 Forbidden   禁止访问。
                404 Not Found   找不到如何与 URI 相匹配的资源。

                500 Internal Server Error  最常见的服务器端错误。
                503 Service Unavailable 服务器端暂时无法处理请求（可能是过载或维护）。
            ]

          完整版
          1**(信息类)：表示接收到请求并且继续处理
            100——客户必须继续发出请求
            101——客户要求服务器根据请求转换HTTP协议版本

          2**(响应成功)：表示动作被成功接收、理解和接受
            200——表明该请求被成功地完成，所请求的资源发送回客户端
            201——提示知道新文件的URL
            202——接受和处理、但处理未完成
            203——返回信息不确定或不完整
            204——请求收到，但返回信息为空
            205——服务器完成了请求，用户代理必须复位当前已经浏览过的文件
            206——服务器已经完成了部分用户的GET请求

          3**(重定向类)：为了完成指定的动作，必须接受进一步处理
            300——请求的资源可在多处得到
            301——本网页被永久性转移到另一个URL
            302——请求的网页被转移到一个新的地址，但客户访问仍继续通过原始URL地址，重定向，新的URL会在response中的Location中返回，浏览器将会使用新的URL发出新的Request。
            303——建议客户访问其他URL或访问方式
            304——自从上次请求后，请求的网页未修改过，服务器返回此响应时，不会返回网页内容，代表上次的文档已经被缓存了，还可以继续使用
            305——请求的资源必须从服务器指定的地址得到
            306——前一版本HTTP中使用的代码，现行版本中不再使用
            307——申明请求的资源临时性删除

          4**(客户端错误类)：请求包含错误语法或不能正确执行
            400——客户端请求有语法错误，不能被服务器所理解
            401——请求未经授权，这个状态代码必须和WWW-Authenticate报头域一起使用
            HTTP 401.1 - 未授权：登录失败
            　　HTTP 401.2 - 未授权：服务器配置问题导致登录失败
            　　HTTP 401.3 - ACL 禁止访问资源
            　　HTTP 401.4 - 未授权：授权被筛选器拒绝
            HTTP 401.5 - 未授权：ISAPI 或 CGI 授权失败
            402——保留有效ChargeTo头响应
            403——禁止访问，服务器收到请求，但是拒绝提供服务
            HTTP 403.1 禁止访问：禁止可执行访问
            　　HTTP 403.2 - 禁止访问：禁止读访问
            　　HTTP 403.3 - 禁止访问：禁止写访问
            　　HTTP 403.4 - 禁止访问：要求 SSL
            　　HTTP 403.5 - 禁止访问：要求 SSL 128
            　　HTTP 403.6 - 禁止访问：IP 地址被拒绝
            　　HTTP 403.7 - 禁止访问：要求客户证书
            　　HTTP 403.8 - 禁止访问：禁止站点访问
            　　HTTP 403.9 - 禁止访问：连接的用户过多
            　　HTTP 403.10 - 禁止访问：配置无效
            　　HTTP 403.11 - 禁止访问：密码更改
            　　HTTP 403.12 - 禁止访问：映射器拒绝访问
            　　HTTP 403.13 - 禁止访问：客户证书已被吊销
            　　HTTP 403.15 - 禁止访问：客户访问许可过多
            　　HTTP 403.16 - 禁止访问：客户证书不可信或者无效
            HTTP 403.17 - 禁止访问：客户证书已经到期或者尚未生效
            404——一个404错误表明可连接服务器，但服务器无法取得所请求的网页，请求资源不存在。eg：输入了错误的URL
            405——用户在Request-Line字段定义的方法不允许
            406——根据用户发送的Accept拖，请求资源不可访问
            407——类似401，用户必须首先在代理服务器上得到授权
            408——客户端没有在用户指定的饿时间内完成请求
            409——对当前资源状态，请求不能完成
            410——服务器上不再有此资源且无进一步的参考地址
            411——服务器拒绝用户定义的Content-Length属性请求
            412——一个或多个请求头字段在当前请求中错误
            413——请求的资源大于服务器允许的大小
            414——请求的资源URL长于服务器允许的长度
            415——请求资源不支持请求项目格式
            416——请求中包含Range请求头字段，在当前请求资源范围内没有range指示值，请求也不包含If-Range请求头字段
            417——服务器不满足请求Expect头字段指定的期望值，如果是代理服务器，可能是下一级服务器不能满足请求长。

          5**(服务端错误类)：服务器不能正确执行一个正确的请求
            HTTP 500 - 服务器遇到错误，无法完成请求
            　　HTTP 500.100 - 内部服务器错误 - ASP 错误
            　　HTTP 500-11 服务器关闭
            　　HTTP 500-12 应用程序重新启动
            　　HTTP 500-13 - 服务器太忙
            　　HTTP 500-14 - 应用程序无效
            　　HTTP 500-15 - 不允许请求 global.asa
            　　Error 501 - 未实现
          HTTP 502 - 网关错误
          HTTP 503：由于超载或停机维护，服务器目前无法使用，一段时间后可能恢复正常

- 一个页面从输入 URL 到页面加载显示完成，这个过程中都发生了什么？（流程说的越详细越好）

          注：这题胜在区分度高，知识点覆盖广，再不懂的人，也能答出几句，
          而高手可以根据自己擅长的领域自由发挥，从URL规范、HTTP协议、DNS、CDN、数据库查询、
          到浏览器流式解析、CSS规则构建、layout、paint、onload/domready、JS执行、JS API绑定等等；

          详细版：
            1、浏览器会开启一个线程来处理这个请求，对 URL 分析判断如果是 http 协议就按照 Web 方式来处理;
            2、调用浏览器内核中的对应方法，比如 WebView 中的 loadUrl 方法;
            3、通过DNS解析获取网址的IP地址，设置 UA 等信息发出第二个GET请求;
            4、进行HTTP协议会话，客户端发送报头(请求报头);
            5、进入到web服务器上的 Web Server，如 Apache、Tomcat、Node.JS 等服务器;
            6、进入部署好的后端应用，如 PHP、Java、JavaScript、Python 等，找到对应的请求处理;
            7、处理结束回馈报头，此处如果浏览器访问过，缓存上有对应资源，会与服务器最后修改时间对比，一致则返回304;
            8、浏览器开始下载html文档(响应报头，状态码200)，同时使用缓存;
            9、文档树建立，根据标记请求所需指定MIME类型的文件（比如css、js）,同时设置了cookie;
            10、页面开始渲染DOM，JS根据DOM API操作DOM,执行事件绑定等，页面显示完成。

          简洁版：
            浏览器根据请求的URL交给DNS域名解析，找到真实IP，向服务器发起请求；
            服务器交给后台处理完成后返回数据，浏览器接收文件（HTML、JS、CSS、图象等）；
            浏览器对加载到的资源（HTML、JS、CSS等）进行语法解析，建立相应的内部数据结构（如HTML的DOM）；
            载入解析到的资源文件，渲染页面，完成。

- 部分地区用户反应网站很卡，请问有哪些可能性的原因，以及解决方法？

- 从打开app到刷新出内容，整个过程中都发生了什么，如果感觉慢，怎么定位问题，怎么解决?

- 除了前端以外还了解什么其它技术么？你最最厉害的技能是什么？

- 你用的得心应手用的熟练地编辑器&开发环境是什么样子？

        Sublime Text 3 + 相关插件编写前端代码
        Google chrome 、Mozilla Firefox浏览器 +firebug 兼容测试和预览页面UI、动画效果和交互功能
        Node.js+Gulp
        git 用于版本控制和Code Review

- 对前端工程师这个职位是怎么样理解的？它的前景会怎么样？

        前端是最贴近用户的程序员，比后端、数据库、产品经理、运营、安全都近。
        1、实现界面交互
        2、提升用户体验
        3、有了Node.js，前端可以实现服务端的一些事情

        前端是最贴近用户的程序员，前端的能力就是能让产品从 90分进化到 100 分，甚至更好，

        参与项目，快速高质量完成实现效果图，精确到1px；

        与团队成员，UI设计，产品经理的沟通；

        做好的页面结构，页面重构和用户体验；

        处理hack，兼容、写出优美的代码格式；

        针对服务器的优化、拥抱最新前端技术。

- 你怎么看待Web App 、hybrid App、Native App？

- 你移动端前端开发的理解？（和 Web 前端开发的主要区别是什么？）

- 你对加班的看法？

- 平时如何管理你的项目？

        先期团队必须确定好全局样式（globe.css），编码模式(utf-8) 等；

        编写习惯必须一致（例如都是采用继承式的写法，单样式都写成一行）；

        标注样式编写人，各模块都及时标注（标注关键样式调用的地方）；

        页面进行标注（例如 页面 模块 开始和结束）；

        CSS跟HTML 分文件夹并行存放，命名都得统一（例如style.css）；

        JS 分文件夹存放 命名以该JS功能为准的英文翻译。

        图片采用整合的 images.png png8 格式文件使用 尽量整合在一起使用方便将来的管理

- 如何设计突发大规模并发架构？

- 当团队人手不足，把功能代码写完已经需要加班的情况下，你会做前端代码的测试吗？

- 说说最近最流行的一些东西吧？常去哪些网站？

        ES6\WebAssembly\Node\MVVM\Web Components\React\React Native\Webpack 组件化

- 知道什么是SEO并且怎么优化么? 知道各种meta data的含义么?

- 移动端（Android IOS）怎么做好用户体验?

        清晰的视觉纵线、
        信息的分组、极致的减法、
        利用选择代替输入、
        标签及文字的排布方式、
        依靠明文确认密码、
        合理的键盘利用、

- 简单描述一下你做过的移动APP项目研发流程？

- 你在现在的团队处于什么样的角色，起到了什么明显的作用？

- 你认为怎样才是全端工程师（Full Stack developer）？

- 你有自己的技术博客吗，用了哪些技术？

- 对前端安全有什么看法？

- 是否了解Web注入攻击，说下原理，最常见的两种攻击（XSS 和 CSRF）了解到什么程度？

- 项目中遇到国哪些印象深刻的技术难题，具体是什么问题，怎么解决？。

- 你的优点是什么？缺点是什么？

- 如何管理前端团队?

- 最近在学什么？能谈谈你未来3，5年给自己的规划吗？