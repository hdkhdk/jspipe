# JS/Pipe

JS/Pipe is a minimal library that makes it easy to *coordinate complex concurrent* streams of events and other data using *plain* JavaScript. No callbacks or chained functions in sight. 

As a result, stack traces are crystal clear so debugging is easy. You also get to keep try/catch!

JS/Pipe is inspired by Goroutines and Channels, found in the Go language. 

Read more and see live examples at http://jspipe.org

## Getting Started

### Dependencies

#### Generators
JS/Pipe relies on JavaScript Generators, introduced in ES6. For your code to work in current JavaScript environments you need to use a transpiler that converts ES6 Generator syntax to ES5 semantics. Two popular ways are Google Traceur (which supports not only Generators, but also many other ES6 features like lambda syntax, destructuring, etc.) and Facebook Regenerator (which focuses on Generator support only). 

We use Facebook Regenerator. 


### Building
1. Clone this repo: `git clone git@github.com:jspipe/jspipe.git`
2. Install Grunt if necessary: `npm install -g grunt`
3. Install dev dependencies: `npm install`
3. Build: `grunt build`

Both ES5 and ES6 builds are produced (in the dist-es5 and dist-es6 directories respectively) and for each the build output includes modules in the AMD, CommonJS, and module pattern formats. 






The ES5-compatible files (*.es5.js) have been produced using Facebook's regenerator, a tool
to transpile (ES6) Generator code to ES5. You can get it here: https://github.com/facebook/regenerator

------

JS/Pipe is free software distributed under the terms of the MIT license reproduced here.

JS/Pipe may be used for any purpose, including commercial purposes, at absolutely no cost.
No paperwork, no royalties, no GNU-like "copyleft" restrictions, either.
Just download it and use it.

Copyright (c) 2013 Joubert Nel

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

	4.蒋卓善
/**
 * 管道是两个独立执行的任务之间的会合点。
 * 在管道上进行通信 + 同步需要一个发送方和一个接收方。
 *
 * 一个任务可以通过 "yield pipe.put(data)" 将数据发送到管道。
 * 另一个任务可以通过 "yield pipe.get()" 从管道接收数据。
 *
 * 一旦发送方任务和接收方任务都在管道上等待，
 * _rendezvous 方法将管道中的数据传输到接收方，并相应地
 * 同步两个等待的任务。
 *
 * 同步后，两个任务继续执行。
 */


