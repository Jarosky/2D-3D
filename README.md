
# 基于webpack配置脚手架

不依赖任何框架，可以用vue，react，node服务端。配置接口遵循webpack配置，可以在webpack默认配置下预留接口给用户自行配置等功能。



## webpack-config 配置说明

### @webpack 目录中

有两个文件夹 一个是client文件夹，另外一个是server文件夹，

#### client文件夹

  client文件夹是客户端的webpack配置，分别有

  ````
dev-client-reload.js  热启动刷新js文件
webpack.base.config   基础base配置
webpack.dev.config    dev环境配置
webpack.dll.config    dll 打包
webpack.prod.config   生产环境配置
  ````

入口是  src目录 出口是dit





#### server文件夹

server文件夹是客户端的webpack配置，分别有

```
dev-client-reload.js  热启动刷新js文件
webpack.base.config   基础base配置
webpack.dev.config    dev环境配置
webpack.dll.config    dll 打包
webpack.prod.config   生产环境配置
```

 入口是 app目录 出口是dit 

## 自行定义webpack配置

如果用户想自行定义webpack配置的话，可以在user-webpack-config目录下有两个配置文件

```
webpack.dev.config    dev环境配置
webpack.prod.config   生产环境配置
```

有两个目录是放Loader或者Plugin的

运行脚本
```
  "scripts": {
    "//注释1:": "web端dev环境运行",
    "web:dev": "cross-env NODE_ENV=development   babel-node  @webpack/index.js  webpackEnv=dev  target=web  ",
    "//注释2:": "web端生产环境运行",
    "web:build": "cross-env NODE_ENV=production   babel-node  @webpack/index.js  webpackEnv=prod  target=web  ",
    "//注释3:": "node服务端dev环境运行",
    "node:dev": "cross-env NODE_ENV=development   babel-node  @webpack/index.js  webpackEnv=dev  target=node  ",
    "//注释4:": "node服务端d生产环境运行",
    "node:build": "cross-env NODE_ENV=production   babel-node  @webpack/index.js  webpackEnv=prod  target=node  ",
    "//注释7": "编译dll文件",
    "dll": "webpack   --progress --config ./scripts/webpack/config/webpack.dll.config.js",
    "//注释8单元测试命令": "运行单元测试",
    "test": "npm run jest",
    "//注释9": "生成测试覆盖率报告",
    "coverage": "jest --coverage --config jest.config.ts",
    "mocha": "mocha ./app/test/add.test.ts",
    "test:webpack": "jest-webpack",
    "jest": " babel-node ./scripts/test.js",
    "graphql:demo": "nodemon  --exec cross-env  NODE_ENV=development  babel-node ./app/graphql/schema/graphql.demo.test.js"
  },

```
