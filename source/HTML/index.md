---
title: HTML
date: 2023-02-11 22:23:18
---

- HTML Hyper Text Markup Language
- 引入
- 与 markdown 同为标记语言

  - 只不过标记的方式不一样
  - 嵌套规则
  - 与【数学公式】几乎一模一样
  - 树状（递归）结构
  - 其实我们会发现，递归结构在数学与计算机里出现的非常之多

    - 树木
    - 数学公式
    - 文件树
    - 编程语言的语法规则
    - 书籍的目录
    - 公司的组织架构
    - 房子
    - 都是树形结构
      - 标签
    - <div>lskdfj<span>woejfl</span>kjsdf</div>
    - <div>aaa<span>bbb</div>ccc</span>

    * <起始标签></结束标签>
    * <自闭合标签>
    * <自闭合标签 /> <img/> <hr/> <base /> <meta /> <link /> <input />
      - 空标签，void element/tag
      - self closing tag
      - <div></div>    <div/>
    * 有些特定标签，即使里面是空的，也不能写成自闭合形式

    - script/iframe/canvas
    - <canvas></canvas>
    `<script src="xxx.js" foo="bar" foo=bar>
    <div>您的浏览浏览器不支持js，请在设置中开启相应的功能</div>
    </script>`
      * 歧义

    * 在 html5 中，完全可以不用给自闭合标签打结束符 <br> <br />
    * 事实上，即使是有些非自闭合标签（如 p，li），在一些情况下也是可以省略结束标签的，**而且，是完全符合 html 标准的**
      - 这种场景一般是可以【推断出】此标签肯定已经结束了
      - 例如
        ````html
        <p>这是一个段落</p>
        <p>这是另一个段落</p>
        <span>aaa</span>
        ```
        ````

  - w3 的文档中对每一个标签在什么情况下可以省略结束标签都做了详细说明 - 例： https://www.w3.org/TR/html-markup/p.html

    - 一般不推荐省略结束标签，原因很简单，省略那么多，人会看不明白，也背不下来那么多规则 \* https://developer.mozilla.org/en-US/docs/Web/HTML/Content_categories
    - 缩进 indent

      - 一般来说，现在前端社区里面都是缩进**两个空格**
        - 对于 markdown，完全也可以只缩进两个空格，我之所以推荐大家缩进 4 个空格，主要是 md 有太多的查看器，效果各不兼容
      - 一个标签如果被一个标签包含在内，则它相对于这个标签缩进一个层级
      - 如果一个标签里面只有纯文字，则可以直接把文字包含在标签内而不缩进

        ```html
        <p></p>
        <div>
          <ul>
            <li>
              <a>
                <img src="a.jpg" />
              </a>
            </li>
            <li>
              <a href="a.pdf"> 点击下载 </a>
            </li>
            <li>he<strong>ll</strong>o</li>
            <li></li>
          </ul>
          <p>aaabb sl</p>
          <p>你在哪里呢 asdfkljsdlf asdf asdf asdf</p>
          <p>我<span>在</span>这里</p>
        </div>
        ```

    - 一般来说，非**块级标签**（关于什么是块级标签，以后会提到）在内容不多的情况下可以选择不缩进，如

           ```html
           <div>
               <p>
                 点击打开
                 <a href="http://jd.com">京东</a>
               </p>
           </div>
           ```

       <!-- * 语义化
         * 语义化是前端开发里面的一个专用术语，其优点在于标签语义化有助于构架良好的html结构，有利于搜索引擎的建立索引、抓取；另外，亦有利于页面在不同的设备上显示尽可能相同；此外，亦有利于构建清晰的机构，有利于团队的开发、维护。————维基百科
         * 说人话：合适的内容用合适的标签 -->

         <div foo="ba'r" foz=baz contenteditable="true"  >jL</div>

         <INPUT TYPE=checkbox disabled required="required" checked='checked' >
         <INPUT TYPE='checkbox' disabled required="required" checked='checked' >
         <video id="ojfwife" class="foo bar baz" controls=controls loop="loop" autoplay>

    - 属性
      _ 每一个标签可以接受一个或多个属性
      _ 属性可以有值，也可以没有
      _ 属性名不区分大小写，属性值区分大小写的
      _ 属性的值一般使用双引号包起来
      _ 也可以使用单引号
      _ 但当属性的值里没有空格，引号等特殊字符时，属性值是**完全可以**不用引号包起来的
      _ 如下列出一些，通用/全局属性(Global Attributes)，即可以用在所有元素上面且有实际意义 + id 属性，在不学 js 的情况下，也可以有地方要用到
      _ 标签在整个页面唯一的值
      _ 一般来说起成一个单一的单词，不以数字开头，没有空格 + name 属性，标签的名字，现在主要用在表单类标签上面 + title 属性，鼠标在上面时显示的 tooltip 文本
      _ alt 属性，主要用在 img 标签上
      _ 指定在图片加载失败的时候的替换文本
      _ ![描述文本](url.jpg)
      _ <img alt="描述文本" title="描述文本" src="url.jpg">
      _
      _ alternative 可选项，替补，或者
      _ alternate
      _ alter 修改
      _ alert 警钟 + class="foo bar" 类别，类名
      _ 空格分隔的单词列表（word,foo-bar）
      _ comma/space separated list + style 属性，用于给标签指定内联样式 + tabindex + contenteditable(5) + data-\*
      _ <div isbn="567890">书籍详情</div>
      _ 文档：https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes \* Google：html Global Attributes

      - data-\* 属性
      - 如何在 html 内表示这些用来表示 html 自身的字符呢

        - 如<>="
        - &char_name;
        - &#decimal;
        - &#xHEX;
        - 所以下面的写法其实是一样的

          ```html　
            abc <p>
                <span> abc     def   </span>  bbb



              a <i> foo bar

                </i>
            </p>
            <pre>

            </pre>
          ```

          - 上面的写当于下面的写法，【严格注意】空格
            ```html
            <p><span>abc def </span><i>foo bar</i></p>
            ```

_ 如何不用 CSS 让空格不被合并呢？
_ html 实体：&nbsp;，但注意这个不是真的空格
_ 实际的 ascii 编码是 160
_ Non Breaking Space

- 以下介绍各个标签

  - html

    - 对于 xhtml 页面来说，根元素可以是其它标签

      - 根标签 root element
        - 一个页面只能有一个
        - 没有的话，浏览器也会自动添加
          <!DOCTYPE HTML>
          <html></html>
          {[() ()]}
      - head

        - https://github.com/joshbuchea/HEAD
        - 头部标签，放一些与页面相关的“元信息”，比如：

          - 页面的编码方式
            - `<meta charset="utf-8">`
              - chartset：字符集
              - meta：元
            * 编码方式又是一个很大的话题
            * 一般的乱码都是因为编码方式引起的
          - 页面的标题，即 title 标签
          - 页面的图标，即浏览器标题栏左边显示的那个小图标

            - 页面图标可以用一个标签来设置

              - `<link rel(ation)="icon" href="http://www.baidu.com/img/favicon.png">`
              - 对于http://example.com/lksjdfasdfjasfd/asdfa/sdf/asd/fasdf/a.html

              * http://example.com/favicon.ico

            - 也可以不用一个标签设置，浏览器会自动读取网站根目录下的 favicon.ico 这个文件
              - 例如：http://www.baidu.com/favicon.ico

          - 比如页面的样式表
            - style/<link rel="stylesheet" href="a.css">
          - 甚至页面可以在这里选择使用哪个引擎渲染
            - 国产很多双核浏览器支持这种模式
              - 浏览器普及
            - <meta name="UA-X-Compatable" content="EDGE" />
              * cutting edge
              * bleeding edge
          - 在移动端，还可以定义页面以多宽的尺寸渲染等
            - viewport,视口
            - <meta name="viewport" content="width=500" />

        - head 里的内容不会被显示在页面上
        - 不存在的话，也会自动添加

      - body

        - 想要在页面中被显示出来的内容都放在这个标签里面
        - 如果页面没有 html 或者 body 标签，浏览器会自动添加，并将页面内容包含在 body 里面

          - 但浏览器同时也会将那些必须放在 head 里的标签放进 head 里面，比如 title 标签

            ```html
            <title>页面标题</title>
            <h1>一级标题</h1>
            <p>一个段落</p>
            ```

          - 上面的代码会被浏览器解析为下面的结构

            ```html
            <!-- <!doctype html> 这一行不会自动添加的 -->
            <html>
              <head>
                <title>页面标题</title>
              </head>
              <body>
                <h1></h1>
                <p></p>
              </body>
            </html>
            ```

          - 同时，如果在 body 或者 html 标签的**结束标签之后**又出现了其它的标签，则之前的结束标签就会被认为无效，浏览器会自动添加结束标签

            ```html
            <html>
              <head></head>
              <body>
                <div></div>
              </body>
              这行会被认为无效
              <p></p>
              <script></script>
            </html>
            <div></div>
            ```

          - 上面的代码相当于

            ```html
            <html>
              <head></head>
              <body>
                <div></div>
                <p></p>
                <script></script>
                <div></div>
              </body>
            </html>
            ```

      - title
        - 页面标题
        - 仅支持纯文本，不支持嵌套其它标签
        - 如果不出现在 head 内，将自动移到 head 内
        - 出现多个的话，仅第一个生效
      - h1-h6 标签

        - header(标题) 1 到 6
        - 一级到六级标题
        - 默认情况下，标题上下会有一定的空白
        - 比较传统的观点认为一个页面不能出现超过一个 h1 标签，原因是为了 SEO
          - SEO 是什么？
            - Search Engine Optimism
            - 搜索 引擎 优化
              - 讲白了就是如何布置页面能让页面在搜索结果中尽量靠前
              - 手段有很多种，请各们各行了解，SEO 本身也是 IT 行业里一个专业的职位
                - 如关键字
                - 页面被引用的次数（反向链接数量）
                  - 交换链接
                - 使用 https
                - 使页面的 html 更符合语义
        - HTML5 中新增了 hgroup（即 header group） 标签，大致用法如下：H5

        ```html
        <hgroup>
          <h1>三体</h1>
          <h2>一部人类文明的诗史</h2>
        </hgroup>
        ```

              * 即当不同级别的标题显示在一起的时候可以用这个标签把hN标签归类
              * 一般来说，这个标签可以替换以前使用div的场景

      - p 标签
        - paragraph
        - 语意是一个段落，当想要表达一段话时都可以使用这个标签
        - 默认情况下也会有上下边距
      - a 标签

        - anchor, 锚
        - 语义是一个链接，链接地址写在 href（Hyperlink REFerence）属性里

          - 可以链接到的类型非常多，而且一般来说是可扩展的

            - 绝对网址，fullpath
              - `<a href="https://jd.com/">京东</a>`
            - 页内特定位置跳转地址
              - `<a href="#pos1"></a>`
              - 例：https://html.spec.whatwg.org/multipage/grouping-content.html#the-dl-element
            - 其它页特定位置跳转地址
              - `<a href="http://jd.com/#footer"></a>`
            - 这个在书目的章节跳转在使用的比较多
            - 相对路径

              - <a href="https://baidu.com/">baidu</a>
              - <a href="a.html">baidu</a>

              - `<a href=".././../a/b/../index.html"></a>`
              - `<a href="./index.html"></a>`
              - `<a href="../index.html"></a>`
                - http://a.com/a/b/c.html
                  - http://a.com/a/b/index.html
                  - http://a.com/a/index.html
              - `<a href="/index.html"></a>`
                - http://a.com/a/b/lkj/adsfa/sdf/c.html
                - http://a.com/index.html

            - 电子邮件
              - `<a href="mailto:aaa@bbb.com"></a>`
              - `<a href="mailto:aaa@bbb.com?title=1&subject=2&content=3"></a>`
                - 需要在电脑安装邮件客户端
            - 电话号码　 tel:18611075877
              - 主要用在手机页面上
            - QQ/taobao 临时会话
              - tencent://temp-chat?QQ=285696737
              - thunder://ghjk;adfklasdhfkweuhfasdlfk
            - 等等等等
              - thunder://LKDJOIE7436239/
            - 空的 href 属性 href="" href="."
              - 链接到当前页面
                - 所以仅以#开头的值是中转到当前页面的特定位置
              - <img src="">
              - 类似的，如果一个 img 标签的 src 属性为空，也将对应当前页面地址
                - https://www.nczonline.net/blog/2009/11/30/empty-image-src-can-destroy-your-site/

        - target 属性

          - 可以指定在哪个窗口打开链接
            - 几个特殊值,关键字
              - \_blank，链接在空白的窗口显示，也就相当于新打开一个窗口了
              - \_self，其实这个是默认值，就是在当前窗体打开
              - \_parent，链接在父窗体显示
              - \_top，链接在顶层窗体显示
            - 自定义值
              - shopingcart，要求不能以\_开头，出处：https://www.w3.org/TR/html-markup/datatypes.html#common.data.browsing-context-name-def
              - 这点等讲到 iframe 等标签时再说
                - \_parent
                - \_top 这两个属性也是需要讲到 iframe 时再提起

        - 在 html5 中，还有一个 download 属性
          `
          - 表示点击这个链接将下载链接对应的文件，而不是跳转到目标页面，下载的文件名以 download 属性的值来命名
            - `<a href="xxx/jianai.pdf" download="简爱.pdf">点我下截《简爱》完整版</a>`
            - 只能触发下载自己网站上的资源，只能在真正的网址上使用，即 url 以 http 开头
            - 问题，如果同时有 target=“\_blank”，又有 download 属性，它如何行为呢？
              - 请自行测试
            - 为什么要有这个属性呢？传统浏览器中，要触发下载，需要服务端的支持，给出特定的 http 头才会触发浏览器下载而不是打开对应的内容
              - 这个属性的出现可以让点击下载完全由前端来完成

      - img 标签
        - image
        - 表示一张图片
        - 用 src(source)属性表示图片的地址
          - 同样也可以是绝对地址，相对地址
            - `<img src="http://www.baidu.com/logo.png" alt="" title="tooltip">`
            - `<img src="../abc.jpg" alt="">`
            - `<img src="/abc.jpg" alt="">`
            - <img srcset="a.jpg 1x, b.jpg 2x, c.jpg 3x">
            - hd/a.jpg
            - fhd/a.jpg
            -
            - 1366\*768
            - 19 吋，1440\*900
            - mac pro 1440*900 2880 * 1800 2k
            - 1280\*720/800
            - 23， 1920\*1080 -> 0.3mm 1
            - 4k 1920*1080 3840*2160
            - 5k 1920*1200 * 4
            - 2 笔记本屏幕
            - 3 手机
            - src 指定的图片可以是浏览器支持的任意图片格式
              - jpg/jpeg,png,bmp,gif,webp,svg,ico
              - 注意 psd 格式应该是不支持的，因为它是 photoshop 专有的格式，支持它需要大量的代码而且 psd 格式的文件一般很大，一般都在几十 M 上下
        - 同时，用 alt 属性表示图片在加载失败时的替换文本
          - 类似于 markdown 中图片的替换文档`![加载失败的替换文档](image source)`，事实上两者基本上是等同的
          - alt 的全程是 alternative
            - 自己查询这个单词的意思，就明白为啥用这个词了
            - 键盘上的 Alt 键是这个单词的前缀，即 alter
        - 可以使用 width 和 height 属性定义图片的宽和高
          - 只写一个的话另一个会根据图片原始比例计算出来
          - 图片一般来说有自己的宽高（natural width/height）
          - 但是图片加载往往需要时间，而图片在加载完成之前浏览器是不知道其宽高的，所以就会产生页面抖动的问题
          - 所以一般会在标签上把宽高写出来，这样图片加载过程中页面就不会抖动了
        - usemap="#themap"
          - <map>
               <area title="xxxx" href="xxx" shape="rect" coords="0,0,100,100">
               <area title="xxxx" href="xxx" shape="circle" coords="0,0,100,100">
               <area title="xxxx" href="xxx" shape="poly" coords="0,0,100,100">
            </map>
            - 可以让图片不同区域对应不同的链接
            - 后面说到map标签后再说
      - span 标签
        - <span class="price">10.00</span>
        - <p> aaa <strong> bbb </strong> ccc </p>
        - 是一个没有明确语义(通用语义)的标签
        - 一般来说想要给特定的内容加样式时可以用一个 span 标签将内容包起来
          - 后面学到 css 就知道了
      - div

      - br
        - break
        - 换行
        - 自闭合标签
        - <br>
      - hr
        - horizontal
        - 水平分隔线
        - 自闭合标签
        - 强行写做`<hr>some text</hr>`的话里面的内容会被移出标签
          - 可以理解为没有</hr>标签
      - base 基准

        - `<base href="页面中所有相对路径的基准地址" target="页面中所有链接的打开位置">`
          - href 属性表示页面中所有**相对路径**的基础路径
            - 一定要以/即目录结尾
              - `<base href="https://www.baidu.com/abc/">`
              - `<base href="/">`相当于`<base href="https://www.baidu.com/">`
          - target 属性表示页面中**所有链接**的打开位置
            - 当然，可以在页内的 a 标签中用它自己的 target 属性覆盖用 base 标签设置的全局打开位置
        - 有些框架等可能会利用这个特性

      - font/blink/marquee

        - <blink> lsk <font>jf</font> dowe </blink>
        - <marquee> foo </marquee>
          - deprecated 不推荐使用
          - obsolete 已废弃
          - 字体
            - 用 size 属性表示大小
            - face 属性表示字体 fontface
            - color 属性表示颜色
            * <font size="25px" face="幼圆" color="red"></font>
          - 已废弃
          - 早些年不用 css 时可以使用这个标签指定字体等
          - 所有已废弃的标签将不再提及

      - em
        - emphasis
        - 语义为**强调**
      - strong
        - 语义也为强调
        - 但强度跟 em 不同，strong 的强调更重一些
      - b bold
        - 只是样式上加粗
      - u underline
      - i italic

        - 多数网站会这个标签来表示图标

      - u underline
      - i
        - italic，斜体的，一般编辑器（如 word）的斜体按钮就是用的一个斜着的 I 图标表示
        - 在以前，这个标签就是表示斜体文字的
        - 但 html5 中对其语义进行了明确
          - 用来表示由于某些原因需要与普通文本区分的文本
        - 默认情况下为斜体
        - 因为跟 icon 这个单词的首字母一样，很多人/框架/库也用这个标签来表示图标
          - http://fontawesome.io/
            - `<i class="fa fa-star"></i>`




- `<!-- dfghjkl -->`
     <!-- 注释 -->

  - 没有基础的同学可能对注释这个概念有点陌生

    - **注释是对程序本身的解释，几乎不会对程序的行为造成任何影响**

      - 说几乎，是因为有些注释还是会对程序有一些影响
        - 几乎任意语言里都有注释
          - C/C++,JS,PHP，java 等语言// , /\* \*/ comment block c style
      - bash 脚本（即命令行脚本），python - 以#做为注释

        - css - 以/\*\*/内的内容为注释 - xcolor: red;

      - html entity
        - 转义(escape)：html entity HTML 实体
      - &name;

        - &#number; 十进制数，&#25105; 我
        - &#xHHHH; 十六进制数,&#x6211;

    - Hexdecimal
    - Unicode
    - 常见具名 html 实体：
      - &nbsp; non-breaking space 160 号空格
      - &amp; &符 ampersand
    - &copy; 版权符
    - &lt; 小于号 little than
    - &gt; 大于号 greater than
    - &quot; 双引号 quote
    - &apos; 单引号
    - 文档：

      - Google： html entity
      - https://dev.w3.org/html5/html-author/charref
      - http://www.w3school.com.cn/html/html_entities.asp
      - http://www.w3school.com.cn/tags/html_ref_entities.html
      - [ square bracket ]
      - { curly braces } mustcache
      - ( parentheses )
      - ; semicolon
      - : colon
      - , comma

        - . period
        - / slash
        - \ backslash
        - ? question mark
        - - plus sign
        - - times star asterisk
        - | vertical | bar ||||||
        - ! exclaimation
        - ^ caret
        - # hash
        - `~~~
        - $ dollar
        - @ at
        - 对空白字符的忽略 我 我

          - 默认情况下浏览器忽略文字与文字之间多于一个的空格，换行符会被全部忽略
            - 当然 css 可以改变这种行为，后我们会看到

        - 可访问性 accessibility a11y internationalizition i18n
        - 在各个设备上访问/对各种人群可访问/视障/听障
        - 读屏软件
        - windows
          高对度主题
        - a r i a / role
        - accessibly rich Internet Application
        - 网页应用程序
        - role 属性提示浏览器当前元素是一个何种视觉元素
        - role=""
        - aria-xxx="yyy"提示浏览器当前视觉元素的状态或其它信息

      - pre
      - pre formatted
      - 表示有预定义格式的文本
      - 里面的内容的回车跟空格都会被保留
      - 本来有个 width 属性，表示每行最多的字符

      * 本来支持度也不好，然后在 html5 中被弃用了，因为可以用 css 来更精确的控制

      - 常与 code 标签 `配合` 使用，用来在`网页`里显示高亮过的代码
      - <pre><code class="">code goes here</code></pre>

        ```js
        var a = 8;
        ```

           <p>  foo  <code> bar </code>   </p>

      - 列表类标签

        - ol，ul
          - Ordered List, Unordered List
          - 其直接子结点必须只能是 li 标签 list item
            - li 内可以是任意其它标签
          - 默认会在每多一层级的列表中缩进
          - 并带有列表项标号，有序和无序的
          * 多个同类项的重复，就应该使用 ol/ul 标签
          * LISP List Procressing SICP
          * 黑客与画家
        - dl

          - Description List / define list
          - dt
            - Description Term
          - dd
            - Description Description
          - 一个列表项是**一个 dt**和**一个或多个 dd**一起算一组
          - 此标签与 ol/ul 有些区别，在于
            - 一个 dt 可以对应多个 dd

          ```html
          <ul>
            <li>
              <span>老师</span>
              <span>谢然</span>
            </li>
          </ul>
          <dl>
            <dt>老师</dt>
            <dd>谢然</dd>

            <dt>学生</dt>
            <dd>张三</dd>
            <dd>李四</dd>
            <dd>王五</dd>
          </dl>
          ```

      - 表单标签

        - form 标签
          - input
            - https://www.google.com.hk/search?q=invalid+inentity+escape+in+regular+expression
            - https://stackoverflow.com/questions/36953775/firefox-error-unable-to-check-input-because-the-pattern-is-not-a-valid-regexp
            - https://www.fxsitecompat.com/en-CA/docs/2016/input-pattern-now-sets-u-flag-for-regular-expressions/
            - https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input
          * 属性
            - action
              - 表单提交的地址
            - target
              - 行为类似 a 标签的 target
            - method
              - 表单提交方式
                - get
                  - 将表单字段拼成 querystring
                    - 什么是 querystring？
                      - http://abc.com/?a=1&b=2&c=3
                - post
                  - 这个等学到 http 再说
            - enctype，编码方式
              - 在讲到 http 的时候再谈
        - input

          - type 属性的各项值
            - text
              - 文本
            - password
              - 密码
            - checkbox
              - 复选框
              - 以 name 相同分组
              - checked 属性表示默认选中
            - radio
              - 单选框
              - 剩余同上
            - file
              - accept
                - 可以接受的文件类型
                - `<input type="file" name="" id="" accept="image/*,text/*">`
                * MIME Type 媒体类型 Multipurpose Internet Mail Extensiion
                - `<input type="file" name="" id="" accept=".jpg,.png,.gif,.jpeg,.webp,.exe" value="c:/user/xieran/desktop/a.pdf">`
                * http://wwww.a.com/favicon.ico
              - 安全问题
              - multiple
                - 是否支持多选文件
              * .txt text/plain
              * .js application/javascript
              * .css text/css
              * .html text/html
              * .png image/png
              * .jpg image/jpeg
              * .gif image/gif
            - hidden
              - 隐藏的输入域
              - value 设置其值
              - name 设置名字
            - 为以下四个值时，都表现为按钮的样式，按钮上的文字需要用 value 属性来设置
            - image
              - 从功能上讲是一个表单提交按钮
              - 从形态上看是一个图片
              - 此时需要使用 src 属性指定图片的地址
              - 现在基本上不这么用，之所以有这个用法，是以前不用 js 时想做出漂亮的按钮时，需要这么用
              - 在 html5 中，可以在这种标签上给定 width 跟 height，类似 img 标签相应的属性，src，alt
            - button
            - submit
              - 单击时会触发表单的提交
            - reset
              - 单击时会重置表单为初始状态
            - **以下为 html5 新增属性值**
            - number
              - 输入数字
              * e,.,-
              * -3.14e-8
              *
            - email
              - multiple
              - 使用半角逗号分隔每个地址
            - date
            - datetime-local
            - time
            - week
            - month
            - url
              - protocal://user:password@domain:port/a/b/c/d.html?a=b&c=d#sldjfoiwjeofij
              - 百度.中国
            - tel
            - range
              - min，4
              - max，10
              - step，2
            - color
              - value 将返回十六进制颜色#abcdef
            - 不能识别的值，当做 text 来处理

          * input 的其它属性

            - value
              - 为按钮形态时设置上面的文字
              - 为输入框时设置里面的默认内容
                - datetime-local
                  - https://zh.wikipedia.org/wiki/ISO_8601
            - name

              - 很重要，表单提交时，这个域/字段/框/FormControl 的名字
              - 同时，在 radio 和 checkbox 阵列里，name 相同的元素被分在一组里

            - disabled
              - 无值的属性
              - 禁用这个输入域
            - required
              - 设置这个输入域为必填项
              - 不填的话无法用**正常手段**触发表单提交
            - maxlength
              - 为文本输入框时设置输入的最大长度
            - minlength
              - 同上，但为设置最小长度
              - 不过兼容性不太好，不少浏览器没有实现
                - 有点矛盾，不填的时候是空的，当然会非法
            - placeholder
              - 占位符
              - 提示性文字，一旦输入内容就消失
            - autofocus
              - 自动获得焦点，即页面加载完后光标自动在这个元素内
            - tabindex
              - 按 tab 键在不同输入域之间跳转时的顺序
              - 会往顺序更大的元素跳
              - 为-1 的话会跳过那个元素

        - button
          - type 属性
            - 不写 type 属性的话，默认为 submit
              - 即：无 type 的 button 的 type 属性默认为 submit
            - `<button type="reset/button/submit">Submit</button>`
            - button
              - 常规按钮，功能上与 input[type="button"]一样
            - submit
              - 提交按钮，功能上与 input[type="submit"]一样
            - reset
              - 重置按钮，功能上与 input[type="reset"]一样
          - 与`<input type="button" name="b" value="lksjdf">`的区别
            - input 的 button 只能在按钮上显示纯文字
            - 而 button 标签可以在按钮上显示其它内容比如图片（即嵌套其它标签），文字也可以设置不同颜色等
        - label 标签

          - 一般与 checkbox 及 radio 一起用，以扩大这两个按钮的可点击区域，提升用户体验。当然，也可以跟其它元素一起用，不过一般没必要（比较典型的是与 input:file 一起用）

          * for 属性

            - 为想要被扩大点击区域的元素的 id，不带井号

            * 细节：在 ie8 及以下不能用于 displaynone 的表单元素，可能是因为 not focusable
            * 表单元素嵌套在 label 的时候可以不用 for 属性

              ```html
              <form action="">
                有for的用法
                <label for="oneid">One</label>

                <input onclick type="text" id="oneid" />

                不用for的用法
                <label> <input type="checkbox" /> 男 </label>
              </form>
              ```

          * 如下怎么算呢？

            ```html
            <input id="a" />
            <label for="a">
              lllll
              <input type="text" />
            </label>
            ```

          * 典型的坑，两次点击，等学了 js 后再谈

        - select name="sel"
          - 下拉选择框
          - 属性
            - multiple
              - 无值属性，表示多选，多选时就不是下拉的样式了
          - 另外此标签在不同的系统里面样式差别很大，而且它的样式一般来说是取自系统自带的，所以很难被 css 控制
            - 所以一些对 ui 要求比较高的网站都选择用其它元素模拟下拉框
              - 例：小米路由器
          - size 属性控制默认显示的数量，也即它的尺寸

        * option
          - value
            - 选择了该项目后它所属的 select 元素的值
          - selected
            - 默认被选中
          - disabled
            - 表示该项被禁用
          - hidden
            - 表示该项被隐藏
          * 以上三个属性均无值
        * optgroup // hgroup colgroup
          - 给 option 分组
          - 用 label 属性表示这个分组的名字
          - 无法被选中，只选择 option
          - 有一个 disabled 属性，如果设置了这个属性，整组标签都会被禁用
          ```html
          <select>
            <option value="1">1</option>
            <optgroup label="这是一个分组" disabled hidden>
              <option value="01">01</option>
              <option value="02">02</option>
              <option value="03">03</option>
              <option value="04">04</option>
              <option value="05">05</option>
            </optgroup>
          </select>
          ```
          - 兼容性不确定，因为我没用过 mac。。。。

        - textarea
          - 多行文本输入框
          - 两个特殊属性
            - rows="3" 行
            - cols="20" 列 column
            * 不过现在也不常用，一般都用 css 来控制了
        - fieldset 字段组 用来把 一组 输入域 放在一起的。
          - field 就是字段的意思，就是说一个表单输入域（输入框）
          - 这个标签用来给输入域分组，所以叫 set
            - set 本来就是组的意思
          - 如果只是分组，完全可以用 div 等标签
            - 那这个标签有什么用呢？
            - fieldset 有个 disabled 属性，如果它有了这个属性，其内的所有输入域都将被禁用，类似 optgroup
              - 在某些场景下是非常好用的
        - legend
          - 只能作为 field set 的子元素，用来标识这组输入域的名字，基本上没有其它用处
            - 而且在有了 css 之后，这个标签基本也没有用武之地了
