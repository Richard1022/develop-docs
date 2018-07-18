# git 工作流
### 目的
* 统一团队Git commit日志标准，便于后续代码review，版本发布以及日志自动化生成等等。
* 统一团队的Git工作流，包括分支使用、tag规范、issue等
---
### Git commit日志基本规范
```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```
* type代表某次提交的类型，比如是修复一个bug还是增加一个新的* feature。所有的type类型如下：
* feat： 新增feature
* fix: 修复bug
* docs: 仅仅修改了文档，比如README, CHANGELOG, CONTRIBUTE等等
* style: 仅仅修改了空格、格式缩进、都好等等，不改变代码逻辑
* refactor: 代码重构，没有加新功能或者修复bug
* perf: 优化相关，比如提升性能、体验
* test: 测试用例，包括单元测试、集成测试等
* chore: 改变构建流程、或者增加依赖库、工具等
* revert: 回滚到上一个版本
---
### Git分支与版本发布规范
* 基本原则：master为保护分支，不直接在master上进行代码修改和提交。
* 开发日常需求或者项目时，从master分支上checkout一个feature分支进行开发或者bugfix分支进行bug修复，功能测试完毕并且项目发布上线后，`将feature分支合并到主干master，并且打Tag发布，最后删除开发分支`。分支命名规范：
* develop 分支
> develop 为开发分支，始终保持最新完成以及bug修复后的代码  
> 一般开发的新功能时，feature分支都是基于develop分支下创建的
* feature 分支
> develop 为开发分支，始终保持最新完成以及bug修复后的代码  
> 一般开发的新功能时，feature分支都是基于develop分支下创建的
* release 分支
> release 为预上线分支，发布提测阶段，会release分支代码为基准提测
```
  当有一组feature开发完成，首先会合并到develop分支，进入提测时，会创建release分支。
如果测试过程中若存在bug需要修复，则直接由开发者在release分支修复并提交。
当测试完成之后，合并release分支到master和develop分支，此时master为最新代码，用作上线。
```
* develop 分支
> develop 为开发分支，始终保持最新完成以及bug修复后的代码  
> 一般开发的新功能时，feature分支都是基于develop分支下创建的


* Tag包括3位版本，前缀使用v。比如v1.2.31。Tag命名规范：
  * 新功能开发使用第2位版本号，bug修复使用第3位版本号
  * 核心基础库或者Node中间价可以在大版本发布请使用灰度版本号，在版本后面加上后缀，用中划线分隔。alpha或者belta后面加上次数，即第几次alpha：
    * v2.0.0-alpha-1 
    * v2.0.0-belta-1
* 版本正式发布前需要生成changelog文档，然后再发布上线。




---
### 参考文档
* https://juejin.im/post/58db6ec7570c350058f22fb5
* http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html
