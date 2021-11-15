# <i class="fa fa-internet-explorer"></i> 关于网站

> 其实好久之前就想搭建个网站，苦于啥也不会、无从下手。学了点html、css感觉还是不太会，很多原理上的东西没有专门学过，完全是丈二和尚摸不着头脑。后来我想既然我这个主要是一些文档知识记录，也没有前后端分离的需求，能够展示内容的话就完全没有问题，那么一般的静态网站形式足矣，于是一顿操作后便有了现在这个网站模样。

## 先修条件

* 一点点[html](https://www.runoob.com/html/html-tutorial.html)、[css](https://www.runoob.com/css/css-tutorial.html)的相关知识，能看懂解读一般的网页代码就行了。

* [markdown](https://markdown.com.cn/)的语法知识。

## Docsify

* 一个神奇的**文档网站**生成器。

* 查看[docsify](https://docsify.js.org/#/)官方网站，这个网站本身也是用了docsify的。里面说明很详尽，按照上面操作的话，一个简单的网站几分钟就能搞定。关于一些其他配置的问题，可自行查询网络上其他人分享的技巧，我在配置这个网站的时候，还是能搜到不少的，虽然品质良莠不齐😂。

* 下面记录几条在配置上我觉得有点困难的方面。
    1. katex公式渲染插件(这是一开始搞错位置了(＞﹏＜))。
        ~~~html
        <head>
            ......
            <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/katex@latest/dist/katex.min.css" />
        </head>

        <body>
            ......
            <script src="//cdn.jsdelivr.net/npm/docsify-katex@latest/dist/docsify-katex.js"></script>
        </body>
        ~~~

    2. C代码部分高亮。
        ~~~html
        <body>
            ......
            <script src="js/lang/prism-c.js"></script> //这里我把json源文件下载到本地了，下同。
            <script src="js/lang/prism-cpp.js"></script>
        </body>
        ~~~
        渲染效果如下↓ 我刚完成的时候即便导入了prism-cpp.js也渲染不了C标记，现在又行了，感觉有点奇怪。其他代码高亮配置同样原理，找CDN添加[语法文件](https://cdn.jsdelivr.net/npm/prismjs@1/components/)
        ~~~cpp
        #include <stdio.h>
        ~~~

        ~~~c
        #include <stdio.h>
        ~~~

    3. 添加css样式表。
        可以看出本网站和docsify原格式有那么些许样式的改变。其实更改样式也比较简单，我这里举个例子（本网站css样表中的一段）。如果更改样式比较多，也建议和我一样新建一个css文件，把需要更改的样式统一汇总即可。

        ~~~css
        .markdown-section pre>code {
            color: #c0c3c1 !important;
            background-color: #343a40 !important;
            font-size: 16px !important;
            white-space: pre !important;
            line-height: 1.5 !important;
            -moz-tab-size: 4 !important;
            -o-tab-size: 4 !important;
            tab-size: 4 !important;
        }
        /*设置代码区的样式*/
        ~~~

* 其他配置。总体来说不是很难，遇到好看的样式，查看其他网站源代码，基本上都能学习借鉴，当然也可以自己创新设计。

## GitHub pages

没什么可说的，网上搜索一堆，这是[官方文档](https://docs.github.com/en/pages)。