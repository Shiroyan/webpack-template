# webpac-spa

### 推荐目录结构
      build
      config
      src
      static      // 存放静态资源
      index.html

### 一些说明
1.  这个配置来源于`vue-cli`， 对其进行一些更改，令其能够适用于非vue的普通项目
2.  默认在生产的时候关闭`sourceMap`
3.  生产时开启了`gzip`
4.  已自带`dev-server`，以及代理转发功能
5.  已集成babel，放心使用`es6`语法
6.  采用`eslint airbnb`标准
7.  使用`handlebars`模板语法

### 使用方法
    `npm install` 安装完依赖
    `npm run dev` 开发
    `npm run build` 打包
    `npm run build --report` 打包并生产分析表格

### 代理转发的配置
    在`config/index.js`中更改
    proxyTable: {
      '/api': {
        target: '',       // 接口域名
        changeOrigin: true,
      }
    }
  
它会把代码中以`api`开头的接口地址转发到`target`域名下，举个例子
接口地址为`api/getList`，其域名为`http://www.abc.com` 当你

    $.ajax({
      url: 'api/getList',
      ..........
    })

发送请求的时候，实际上是请求`http://www.abc.com/api/getList`
    


    