# JavaScript全栈

## 一、前端开发的历史和趋势

### 什么是前端
* 前端：针对浏览器的开发，代码在浏览器运行
* 后端：针对服务器的开发，代码在服务器运行

### 前后端不分的时代
互联网发展的早期，前后端开发是一体的，前端代码是后端代码的一部分。
1. 后端收到浏览器的请求
2. 生成静态页面
3. 发送到浏览器

### 后端MVC的开发模式
那时的网站开发，采用的是后端MVC模式。
* Model（模型层）：提供/保存数据
* Controller（控制层）：数据处理，实现业务逻辑
* View（视图层）：展示数据，提供用户界面

前端只是后端MVC的V。

以PHP框架Laravel为例
**前端工程师的角色**
那时的前端工程师，实际上是模板工程师，负责编写页面模板。
后端代码读取模板，替换变量，渲染出页面。

**典型的PHP模板**
```
<html>
    <head>
        <title>Car {{$car->id}}</title>
    </head>
    <body>
        <h1>Car {{$car->id}}</h1>
        <ul>
            <li>Make: {{$car->make}}</li>
            <li>Model: {{$car->model}}</li>
            <li>Produced on: {{$car->produced_on}}</li>
        </ul>
    </body>
</html>
```

### Ajax
Ajax技术诞生，改变了一切。
* 2004年：Gmail
* 2005年：Google地图
前端不再是后端的模板，可以独立得到各种数据。

### Web 2.0
Ajax技术促成了Web2.0的诞生。
* Web1.0：静态页面，纯内容展示。
* Web2.0：动态网页，富交互，前端数据处理。
从那时起，前端变得复杂了，对前端工程师的要求越来越高。

### 前端MVC框架
前端通过Ajax得到数据，因此也有了处理数据的需求。
前端代码变得也需要保存数据、处理数据、生成视图，这导致了前端MVC框架的诞生。
* 2010年，Backbone.js
    Backbone将前端代码分成两个基本部分。
    - Model：管理数据
    - View：数据的展现

    **前端Controller**
    Backbone只有M和V，没有C。因为，前端Controller与后端不同。
    - 不需要，也不应该处理业务逻辑
    - 只需要处理UI逻辑，响应用户的一举一动
    所以，前端Controller相对比较简单。Backbone没有C，只有事件来处理UI逻辑。
    ```
    var Appview = Backbone.View.extend({
        events:{
            "keypress #new-todo":"createOnEnter",
            "click #clear-completed":"clearCompleted",
            "click #toggle-all":"toggleAllCompleted"
        }
    });
    ```

    **Router**
    前端还有一种天然的方法，可以切换视图，那就是URL。
    通过URL切换视图，这就是Router（路由）的作用。以Backbone为例。
    ```
    App.Router=Backbone.Router.extend({
        routers:{
            "":"index",
            "show":"show"
        },
        index:function(){
            $(document.body).append("调用了Index路由");
        },
        show:function(){
            $(document.body).append("调用了Show路由");
        }
    })
    ```
    示例：Backbone_demo *注意浏览器URL的变化*

    ### MVVM模式
    另一些框架提出MVVM模式，用View Model替代Controller。
    - Model
    - View
    - View-Model:简化的Controller，唯一作用就是为View提供处理好的数据，不含其他逻辑。
    本质：*view绑定view-model，视图与数据模型强耦合。数据的变化实时反应在view上，不需要手动处理。*

    ### SPA
    前端可以做到：
    - 读写数据
    - 切换视图
    - 用户交互
    这意味着，网页其实是一个应用程序。
    > SPA = Single-Page application
    2010年后，前端工程师从开发页面，变成了开发“前端应用”（跑在浏览器里面的应用程序）。

    >传统的架构
    >单页应用的架构
    >多了一个前端MVC层

    ### Angular
    Google公司推出的Angular是最流行的MVVM前端框架。
    它的风格属于HTML语言的增强，核心概念是双向绑定。

    **Angular的双向绑定示例** 查看angular demo

    ### Vue
    Vue.js是现在很热门的一种前端MVVM框架。
    它的基本思想与Angular类似，但是用法更简单，而且引入了响应式编程的概念。

    **Vue的双向绑定示例**  查看Vue demo

    ### 前后端分离
    * Ajax ->前端应用兴起
    * 智能手机 -> 多终端支持
    这两个原因，导致前端开发方式发生根本的变化。
    前端不再是后端MVC中的V，而是单独的一层。

    ### REST接口
    前后端分离以后，他们之间通过接口通信。
    后端暴露出接口，前端消费后端提供的数据。
    后端接口一般是REST形式，前后端的通信协议一般是HTTP。

    ### Node
    2009年，Node项目诞生，它是服务器上的JavaScript运行环境。
    Node= JavaScript+操作系统API

    #### Node的意义
    * JavaScript成为服务器端脚本语言，与Python和Ruby一样。
    * JavaScript成为唯一的浏览器和服务器都支持的语言。
    * 前端工程师可以编写后端程序了。

    #### 前端开发模式的根本改变
    * Node环境下开发
    * 大量使用服务器端工具
    * 引入持续集成等软件工程的标准流程
    * 开发完成后，编译成浏览器可以运行的脚本，放上CDN

    ### 全栈工程师
    前端工程师正在转变为全栈工程师
    * 一个人负责开发前端和后端
    * 从数据库到UI的所有开发

    ### 全栈技能
    怎样才能称为全栈工程师？
    * 传统前端技能：HTML、JavaScript、CSS
    * 一门后端语言
    * 移动端开发：IOS/Android/HTML5
    * 其他技能：数据库、HTTP等等。
    ### 软件行业的发展动力
    历史演变：前后端不分 -> 前后端分离 -> 全栈工程师
    动力：更加产业化、大规模地生产软件
    * 效率更高
    * 成本更低
    通用性好、能够快速产出的技术含量最终会赢，单个程序员的生产力要求越来越高。

    ### H5就是一个最好的例子
    为什么H5技术会赢得移动端？
    * 开发速度快：Native需要重新编译才能看到结果，H5是即时输出
    * 开发成本低：Native需要两个开发团队，H5只要一个
    * 快速开发：安卓Native新版本需要24小时，IOS需要3-4天，H5可以随时更新。

    ### 未来软件的特点
    * 联网
    * 高并发
    * 分布式
    * 跨终端
    现在基于Web的前端技术，将演变为未来所有软件的通用的GUI解决方案。

    ### 未来只有两种软件工程师
    * 端工程师
        - 手机端
        - PC端
        - TV端
        - VR端
        - ...
    * 云工程师


## React技术栈
React是目前最热门的前端框架
* Facebook公司2013年推出
* 现在最好的社区支持和生态圈
* 大量的第三方工具

### React的优点
* 组件模式：代码复用和团队分工
* 虚拟DOM：性能优势
* 移动端支持：跨终端

### React的缺点
* 学习曲线较陡峭
* 全新的一套概念，与其他所有框架截然不同
* 只有采用它的整个技术栈，才能发挥最大威力
总结：React非常先进和强大，但是学习和实现成本都不低。

### JSX语法
React使用JSX语法，JavaScript代码中可以写HTML代码。
```
let myTitle = <h1>Hello,World</h1>
```   

### JSX语法解释
1. JSX语法的最外层，只能有一个节点
2. JSX语法中可以插入JavaScript代码，使用大括号。
```
let myTitle = <p>{'Hello'+'World'}</p>
```

### Babel 转码器
JavaScript引擎（包括浏览器和Node）都不认识JSX，需要首先使用Babel转码，然后才能运行。
React需要加载两个库：React和React-DOM，前者是React的核心库，后者是React的DOM适配库。
Babel用来在浏览器转换JSX语法，如果服务器已经转好了，浏览器就不需要加载这个库。





