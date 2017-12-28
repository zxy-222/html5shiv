- #### html5shiv有什么用？

  - **html5shiv使得传统浏览器支持部分HTML5元素提供相应的基本样式。**
  - **传统浏览器，即主流浏览器的低版本，包括IE6-9、Safri4.x、Firefox3.x等。**

- #### html5shiv怎么用？

  - **在html文档的head标签里引入链接**

    ```
    <!DOCTYPE html>
    <html>
    <head>
      <meta charset="utf-8">
        <title></title>
        <!-- 在这里引入html5shiv -->
        <!--[if lt IE 9]>
        <script src="html5shiv.min.js"></script>
      <![endif]-->
    </head>
    <body>
        <header>
            <h1>如何使用html5shiv</h1>
            <p>引入html5shiv后就可以愉快地让IE6-9支持html5新元素了！</p>
        </header>
    </body>
    </html>
    ```

- #### html5shiv支持哪些html5元素?

  - **html5shiv并不能让传统低版本浏览器正常实现html5元素所有功能，而是对不支持html5元素，如video、audio等，当成相应的块级或行内元素进行显示，并可以为html5元素添加样式。**

    ```
    <!--[if lt IE 9]>
    <script>
      window.html5 = {
      'elements': 'abbr article custom elements',
      'shivCSS': true,
      'shivMethods': true
      };
    </script>
    <script src="html5shiv.min.js"></script>
    <![endif]-->
    其中elements的属性值是html5元素标签，可以是由空格分隔的字符串或数组；shivCSS的属性类型为Boolean，默认为true，给html5元素添加CSS样式；shivMethods的属性类型为Boolean，默认为true，覆盖createElement和createDocumentFragment方法。
    ```

- #### 不用html5shiv解决问题？

  - 有时，页面只需用到section header footer article等少数几个html5语义化元素。可以不通过html5shiv，自己写js实现低版本浏览器支持这些元素。

    ```
    <!--[if lt IE 9]>
      <script>
       ;(function(){
         var elements = ['section','header','footer','article'];
         var i;
         for(i in elements){
           document.createElement(elements[i]);
         }
       })();
      </script>
    <![endif]-->
    ```

  - 再对html5元素添加相应样式

    ```
    <style>
      section, header, footer, article {display: block}
    </style>
    ```

    ​