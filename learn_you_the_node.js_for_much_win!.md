# LEARN YOU THE NODE.JS FOR MUCH WIN!
#学习NODE.js为了你的胜利 
   
##HTTP CLIENT(练习第7章 第3节)


Write a program that performs an HTTP GET request to a URL provided to you as the first command-line argument. Write the String contents of each"data" event from the response to a new line on the console (stdout). 

######编写一个程序来发起一个 HTTP GET 请求，所请求的 URL 为命令行参数的第一个。然后将每一个 "data"事件所得的数据，以字符串形式在终端（标准输出 stdout）的新的一行打印出来。
───────────────────────────────────────────────────────────────────────
## HINTS 
 For this exercise you will need to use the http core module. 
#####完成这个练习，你需要使用 Node.js 核心模块之一
Documentation on the http module can be found by pointing your browser  
  here:
  
  file:///Users/dllo/.nvm/versions/node/v8.9.4/lib/node_modules/learnyounode 
  /node_apidoc/http.html 
#####你可以使用浏览器访问   file:///Users/dllo/.nvm/versions/node/v8.9.4/lib/node_modules/learnyounode/node_apidoc/http.html 
The http.get() method is a shortcut for simple GET requests, use it to  
simplify your solution. The first argument to http.get() can be the URL  
you want to GET; provide a callback as the second argument. 
#####http.get() 方法是用来发起简单的 GET 请求的快捷方式，使用这个方法可以一定程度简化你的程序。http.get()的第一个参数是你想要 GET 的 URL，第二个参数则是回调函数。。

Unlike other callback functions, this one has the signature:
##### 与其他的回调函数不同，这个回调函数有如下这些特征：
```
 function callback (response) { /* ... */ }
```
 
Where the response object is a Node Stream object. You can treat Node  Streams as objects that emit events. The three events that are of most  
interest are: "data", "error" and "end". You listen to an event like so: 
#####response 对象是一个 Node 的 Stream 类型的对象，你可以将 Node Stream当做一个会触发一些事件的对象，其中我们通常所需要关心的事件有三个："data"，"error" 以及 "end"。你可以像这样来监听一个事件：
```
response.on("data", function (data) { /* ... */ }) 
```
 The "data" event is emitted when a chunk of data is available and can be  
  processed. The size of the chunk depends upon the underlying data source.
#####'data'  
####事件会在每个数据块到达并已经可以对其进行一些处理的时候被触发。数据块的大小将取决于数据源。  
 The response object / Stream that you get from http.get() also has a  
  setEncoding() method. If you call this method with "utf8", the "data"  
  events will emit Strings rather than the standard Node Buffer objects  
  which you have to explicitly convert to Strings. 
##### 你从 http.get() 所获得的 response 对象/Stream 还有一个 setEncoding()的方法。如果你调用这个方法，并为其指定参数为 utf8，那么 data  事件中会传递字符串，而不是标准的 Node Buffer 对象，这样，你也不用再手动将 Buffer 对象转换成字符串了。
───────────────────────────────────────────────────────────────────────
#####要再次显示此说明文本，请执行： learnyounode print  
#####要测试执行你的程序，请执行： learnyounode run program.js 
#####要验证你的程序，请执行： learnyounode verify program.js
#####需要帮助？执行： learnyounode help 