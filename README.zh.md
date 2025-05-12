JS/Pipe 是一个极简的库，它使得使用纯 JavaScript 协调复杂的并发事件流和其他数据变得非常容易。无需回调或链式函数。
因此，堆栈跟踪清晰明了，调试变得简单。你还可以保留 try/catch！
JS/Pipe 受到 Go 语言中的 Goroutines 和 Channels 的启发。
更多信息和在线示例，请访问 http://jspipe.org。
入门指南
依赖项
生成器
JS/Pipe 依赖于 ES6 中引入的 JavaScript 生成器。为了让代码在当前的 JavaScript 环境中运行，你需要使用一个将 ES6 生成器语法转换为 ES5 语义的转译器。两种流行的方式是 Google Traceur（它不仅支持生成器，还支持许多其他 ES6 特性，如 lambda 语法、解构等）和 Facebook Regenerator（它只专注于生成器支持）。
我们使用 Facebook Regenerator。
构建
克隆此仓库：git clone git@github.com:jspipe/jspipe.git
如有必要，安装 Grunt：npm install -g grunt
安装开发依赖项：npm install