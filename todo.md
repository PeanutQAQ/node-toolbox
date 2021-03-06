# node Dev & Deploy 个人笔记

#### node 包

 包名 | 用途
:-----------:| :-------------------------------------:
zeit/ncc     | 一个打包 node 项目内 node-modules 的工具。
minimist     | 一个轻量级解析 process.argv 的工具。
chalk        | 一个可以给 node 输出着色的工具。
progress     | 一个 node 输出框的步骤条。
inquirer     | 一个在命令行页面对话的复杂交互。
cowsay       | 牛说
forever      | 类似 pm2 一个启动 node 进程的工具
nodemon      | 开发 node 热更新工具 https://nodemon.io/

#### 不错的文章

[task&mircotasks详解](https://jakearchibald.com/2015/tasks-microtasks-queues-and-schedules/)
[createServer详解](https://codeburst.io/all-about-http-in-node-js-and-3-best-ways-for-http-requests-in-web-development-6e5b6876c3a4)


 
区分 process.nextTick setImmadite()
the Battery API the Fetch API Service Workers 在浏览器 runtime 均提供 promise 接口
使用 util.promisify 将旧的 error-first 的 Node API 转换为 promise
详细阅读 mdn Promise 的定义和使用，明确 async await 用法 & 正确捕获 ERROR
node 核心模块
       1. Event emitter 事件模块
       2. http 模块 - createServer 会返回一个 Server 对象 - 原生node || request 库 || axios 可以在 node 端发起请求 
       3. http createServer 传递的 callback 只会在获取完 headers 时触发，如果要获取 request body 需要用 流 处理
fs 模块
       1. node fs 基础 api 
       2. fs-extra 库 
       3. fs promise 接口
path 模块
       path.basename() path.dirname() path.extname() path.isAbsolute() path.join() etc
os 模块 一些系统的参数
buffer 模块
stream 模块是核心 stream-handbook 



### todo
1. 写一个 http 模块的详细介绍，从 event emmitter 开始 到 request stream
2. 写一个静态服务器参考：https://codeburst.io/all-about-http-in-node-js-and-3-best-ways-for-http-requests-in-web-development-6e5b6876c3a4
3. 写一个图床
4. 写一个 weather 应用


npm | npm update 更新包 
      npm root -g 查询全局包的路径 
      可以在 package.json 里配置 eslint 或者 babel 这个跟每个 dev 工具有关，查看对应的配置说明。
      npm list packageName --depth=0 - 查看第一层包
    npm view packageName version - 查看已安装的包版本
    npm view packageName versions - 查看可安装的包的版本信息
    npm uninstall packageName 从 node_modules 移除
    npm uninstall -S packageName 移除并在 dependency 删除 -S || --save
    npm uninstall -D packageName 移除并在 devdependency 删除 -D || --save-dev
    npm install --production 不安装 dev


    npx 可以做很多事：本质上安装然后擦除
      1. 不安装的执行很多 commond line 包
      2. npx node@8 -v 不安装 nvm 等 node 的不同版本
      3. 通过 url 运行代码npx https://gist.github.com/zkat/4bc19503fe9e9309e2bfaa2c58074d32
