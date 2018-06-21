# vue-project-guide
### 目录结构
`项目主体代码规范采用eslint规则`
~~~
vue-web 部署目录
├─build           webpack应用目录
│  ├─build.js           npm run build 执行脚本
│  ├─check-versions.js           检查web环境版本
│  ├─utils.js           静态资源预处理器
│  ├─vue-loader.conf.js           组件预处理器配置
│  ├─webpack.base.conf.js           webpack基础配置
│  ├─webpack.dev.conf.js           npm run dev 执行脚本及开发环境时 webpack打包配置
│  └─webpack.prod.conf.js           生产环境时webpack打包配置
│
├─config           项目配置文件（对外访问目录）
│  ├─dev.env.js           开发环境配置
│  ├─index.js           项目配置文件
│  ├─prod.env.js           生产环境配置
│  └─test.env.js           单元测试配置（此项目没有用）
│
├─server           node中间服务文件（用于生产环境web服务器的中间服务）
│  ├─package.json           安装依赖包
│  └─server.js           node服务脚本
│
├─src           应用目录
│  ├─api           项目api模块
│  │  ├─index.js           api入口
│  │  ├─login.js           登录模块的api（自定义）
│  │  └─request.js           请求服务设置（axios、请求拦截器...）
│  ├─assets           静态资源
│  ├─components           公共组件
│  │  ├─SvgIcon           svg-icon组件（例子）
│  │  └─table           table组件（例子）
│  ├─global           全局方法及变量
│  │  ├─means.js           全局方法
│  │  └─variable.js           全局变量
│  ├─icons           图标
│  │  ├─svg           svg资源
│  │  └─index.js           注册全局svg-icon组件
│  ├─router           路由
│  │  ├─before_each.js           vue-router导航守卫
│  │  └─index.js           vue-router配置
│  ├─store           vuex配置
│  │  ├─modules           按模块设置全局状态及管理
│  │  ├─getters.js           全局状态的计算属性
│  │  └─index.js           vuex入口
│  ├─views           视图目录
│  │  ├─layout           项目布局
│  │  ├─login           登录模块
│  │  └─svg-icons           svg-icon列表
│  ├─App.vue           应用组件
│  └─main.js           应用主入口
│
├─static           静态资源
├─test           单元测试（没有启用）
├─.babelrc           ES6编译设置
├─.editorconfig           统一代码格式的解决方案，[参考：有各个参数的说明](https://github.com/cy0707/Learn_Vue/issues/6)
├─eslintignore.js           eslint不检查目录配置
├─eslintrc.js           eslint配置
├─gitignore           git不上传目录配置
├─.gitlab-ci.yml           gitlab-ci 自动部署脚本
├─.postcssrc.js           [参考](https://github.com/michael-ciniawsky/postcss-load-config)
├─Dockerfile           docker镜像文件
├─index.html           入口文件
~~~
### vue风格指南
* 单文件组件采用大驼峰命名法
* 


