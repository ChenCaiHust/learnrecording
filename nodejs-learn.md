## Nodejs 学习问题记录

### Nodejs是什么？
* 基于Google V8引擎构建的Javascript运行时环境
* 事件库，异步为Nodejs非常重要的特性
* 目标：将javascript语言扩展到server端

### Nodejs 和 NPM的关系？
* NPM我安装的时候是与nodejs一起安装的，听说之前要分别安装
* NPM 是Nodejs的包管理工具，Nodejs和许多其它的语言库有类似的地方，通过模块来组织类库，NPM这个做的非常不错，可以通过这工具来发布自己的包，也可以方便使用别人写的第三方包，还可以进行对应的版本指定，处理起来相当方便，一个简单的命令即可
* NPM的包管理工具现在看起来做的不错，和Python的包管理工具差不多，做的很方便，很好使用

### 从Javascript和python语言看流行语言的重要特点
* 较简洁的核心语言（如c，python）
* 围绕核心语言特性的核心库是否强大与好用
* 丰富的开发者生态提供的多且方便易用的第三方库，这方面Python及javascript做的非常好，不像c++，搞个库还要自己下载，解压，集成编译，麻烦的要死，而python和javascript只需要简单的命令两个搞定这个问题

### Nodejs的两种执行方式
* 把 javascript 代码写到一个文件中，如server.js， 然后在server.js所在目录下面运行命令行： node server.js
* 在命令行中输入node后，再点击回车键，则进行交互式命令行模式，这种模式下适合进行简单的代码测试，用来看看不知道的功能，简单测试一个结果什么的，比较好用，在正式产品的布置中，当然还是用放到文件里面了
* 这两种方式和python提供的两种执行方式简直基本一模一样

### Nodejs的代码编写模型
* 接口一般都是异步的，因为系统的设计方式就是回调的异步方式设计来提高程度的处理效率
* 异步接口一般最后一个函数是回调函数callback， 而回调函数的第一个参数一般用作处理错误返回码
* Nodejs本身设计为高性能的事件处理javascript运行环境，其设计原则为模块化设计原则加上事件处理模型

### Nodejs事件模型
* events模块是定义良好的事件处理模型出发点，通过 var events = require('events')引入
* EventEmitter这个类里面有两个重要的接口如下：
    * on(eventname, eventHandler)，绑定发生的事件与对应的事件处理函数
    * emit(eventname,para1,para2)，用来表示某事件发生了的标识
* 代码模型如下
```
var events = require("events");
eventMitter = new events.EventEmitter();
eventMitter.on('some-event', function(arg1, arg2){
	console.log("event listener", arg1, arg2);
});
eventMitter.emit('eventMitter', arg1, arg2);
```
### Nodejs之buffer模块
* Buffer模块本质上是用来表示二进制数据的
* 为什么要这个模块呢？是因为想提供字符串类型的底层表示，方便一些底层数据操作
* Buffer.from(string, encoding) 及 Buffer.toString(encoding)是比较重要的接口

###
