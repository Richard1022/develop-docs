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
* 组件数据return 新对象
* v-for 设置键值,避免和v-if用在一起
* 私有属性名$_
> 插件、混入等扩展中始终为自定义的私有属性使用 $_ 前缀。并附带一个命名空间以回避和其它作者的冲突 (比如 $_yourPluginName_)。
* 单文件组件的文件名采用大驼峰命名法
* 基础组件名
> 应用特定样式和约定的基础组件 (也就是展示类的、无逻辑的或无状态的组件) 应该全部以一个特定的前缀开头，比如 Base、App 或 V。
* 单例组件
> 只应该拥有单个活跃实例的组件应该以 The 前缀命名，以示其唯一性。
* 紧密耦合的组件名
> 和父组件紧密耦合的子组件应该以父组件名作为前缀命名。
* 组件名中的单词顺序
> 组件名应该以高级别的 (通常是一般化描述的) 单词开头，以描述性的修饰词结尾。
* 自闭合组件
> 在单文件组件、字符串模板和 JSX 中没有内容的组件应该是自闭合的——但在 DOM 模板里永远不要这样做。
* 模板中的组件名大小写
> 对于绝大多数项目来说，在单文件组件和字符串模板中组件名应该总是 PascalCase 的——但是在 DOM 模板中总是 kebab-case 的。
* JS/JSX 中的组件名大小写
> JS/JSX 中的组件名应该始终是 PascalCase 的，尽管在较为简单的应用中只使用 Vue.component 进行全局组件注册时，可以使用 kebab-case 字符串。
* 完整单词的组件名
> 组件名应该倾向于完整单词而不是缩写。
* Prop 名大小写
> 在声明 prop 的时候，其命名应该始终使用 camelCase，而在模板和 JSX 中应该始终使用 kebab-case。
* 模板中简单的表达式
> 组件模板应该只包含简单的表达式，复杂的表达式则应该重构为计算属性或方法。
* 带引号的特性值
> 非空 HTML 特性值应该始终带引号 (单引号或双引号，选你 JS 里不用的那个)。

### 组件实例顺序
```
全局感知 (要求组件以外的知识)

name
parent
1. 组件类型 (更改组件的类型)

functional
2. 模板修改器 (改变模板的编译方式)

delimiters
comments
3. 模板依赖 (模板内使用的资源)

components
directives
filters
4. 组合 (向选项里合并属性)

extends
mixins
5. 接口 (组件的接口)

inheritAttrs
model
props/propsData
6. 本地状态 (本地的响应式属性)

data
computed
7. 事件 (通过响应式事件触发的回调)

watch
8. 生命周期钩子 (按照它们被调用的顺序)
beforeCreate
created
beforeMount
mounted
beforeUpdate
updated
activated
deactivated
beforeDestroy
destroyed
非响应式的属性 (不依赖响应系统的实例属性)

9. methods
渲染 (组件输出的声明式描述)

template/render
renderError
```



