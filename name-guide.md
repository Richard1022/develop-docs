# javascript开发命名指南
### 命名方式
* Pascal Case 大驼峰式命名法：首字母大写。`eg：StudentInfo、UserInfo、ProductInfo`
* Camel Case 小驼峰式命名法：首字母小写。`eg：studentInfo、userInfo、productInfo`
---
### 文件资源命名
* 文件名不得含有空格
* 文件建议只用小写字母，不用大写字母 `eg:某些说明文件除外，README,LICENSE除外`
* 文件名包含多个单词时，单词之间建议使用半角连字符`-`分隔
* 引入资源使用相对路径
---
### 变量命名
命名方式： 小驼峰命名法  
命名规范： 类型+描述  
|类型|命名|
:--:|:--:
boolean|is/has+描述
---
### 常量
命名方式： 全部大写  
命名规范： _下划线来分隔单词
---
### 函数
命名方式： 小驼峰命名法 `eg:构造函数首字母大写`  
命名规则：前缀+描述 `eg:前缀为动词`
* can `判断是否可执行某个动作`
* has `判断是否含有某个值`
* is `判断是否为某个值`
* set/get `设置/获取某个值`
---
### 类
命名方式： 首字母大写 `eg:同构造函数`
* 公有方法/属性 `eg:同函数命名；私有方法_下滑线前缀`
---
### 函数注释
函数(方法)注释也是多行注释的一种，但是包含了特殊的注释要求，参照 javadoc(百度百科)
```
/** 
* 函数说明 
* @关键字 
*/
```
注释名|语法|含义|示例
|:--:|:--|:--|:--|
|@param	|@param 参数名 {参数类型} 描述信息	|描述参数的信息|	@param name {String} 传入名称|
|@return|@return {返回类型} 描述信息|描述返回值的信息|@return {Boolean} true:可执行;false:不可执行|
|@author|@author 作者信息 [附属信息：如邮箱、日期]|描述此函数作者的信息|@author 张三 2015/07/21
|@version|@version XX.XX.XX|描述此函数的版本号|@version 1.0.3|
@example|@example|示例代码|@example setTitle('测试')|如下|
---
# css开发命名指南
* 一般情况下ID不应该被用于样式，并且ID的权重很高，所以不使用ID解决样式的问题，而是使用class
* css选择器中避免使用标签名`从结构、表现、行为分离的原则来看，应该尽量避免css中出现HTML标签，并且在css选择器中出现标签名会存在潜在的问题。`
* 使用子选择器
* 0后面不带单位
* 常见class命名关键词：
布局类：header, footer, container, main, content, aside, page, section  
包裹类：wrap, inner  
区块类：region, block, box  
结构类：hd, bd, ft, top, bottom, left, right, middle, col, row, grid, span  
列表类：list, item, field  
主次类：primary, secondary, sub, minor  
大小类：s, m, l, xl, large, small  
状态类：active, current, checked, hover, fail, success, warn, error, on, off  
导航类：nav, prev, next, breadcrumb, forward, back, indicator, paging, first, last  
交互类：tips, alert, modal, pop, panel, tabs, accordion, slide, scroll, overlay,  
星级类：rate, star  
分割类：group, seperate, divider  
等分类：full, half, third, quarter  
表格类：table, tr, td, cell, row  
图片类：img, thumbnail, original, album, gallery  
语言类：cn, en  
论坛类：forum, bbs, topic, post  
方向类：up, down, left, right  
其他语义类：btn, close, ok, cancel, switch; link, title, info, intro, more, icon; form, label, search, contact, phone, date, email, user; view, loading...












