# 开发者项目开发准备

## 目录结构

- build 构建相关的配置和文件
- client 客户端相关的内容，此项目为网页相关的内容
  - assets
  - components
  - containers
- config 项目的配置
- dist 生成内容
- docs 项目相关文档
- scripts 一些辅助脚本
- server 服务端程序
  - boot 启动 server 时做处理，可能会去掉
  - helper 公用的辅助代码
  - middlewares 中间件
  - routes server 端路由
  - service 独立的 service，提供某种服务，例如登陆登出
- static 静态文件的存放位置
- test 测试
  - e2e 集成测试
  - unit 单元测试
- views 模板文件


## 如何使用

npm 为核心，尽量使用 package.json 文件中的 scripts 字段
其余可能的脚本放到 scripts 目录中，推荐使用 python3 和 shell

~~~JavaScript
{
  "dev": "nodemon --watch server server/main.js",
  "start": "cross-env NODE_ENV=production node server/main.js",
  "build": "node build/build.js",
  "unit": "cross-env BABEL_ENV=test karma start test/unit/karma.conf.js --single-run",
  "unit-ci": "cross-env BABEL_ENV=test karma start test/unit/karma.conf.js",
  "e2e": "node test/e2e/runner.js",
  "test": "npm run unit && npm run e2e",
  "lint": "eslint --ext .js,.vue client server test/unit/specs test/e2e/specs"
}
~~~


## 选型和工具

### 开发

- vue
- scss 换 stylus 或 cssnext
- es6、7 其他语言也 ok


### 代码规范

#### markdown css js

editorconfig & eslint airbnb

~~~ini
charset = utf-8
indent_style = space
indent_size = 2
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true
~~~

bem rscss smacss


### 测试

karma、mocha & powerassert

nightmare


### webpack

#### webpack 是什么

js 的 bundler => 前端代码的 bundler

hmr


#### 与 gulp 和 grunt 的区别

gulp grunt task runner

html -> html
css -> css
js -> js
img -> img
\* -> \*

webpack bundler

all -> js -> all


#### webpack 基础

- entry

- output
  filename
  path

- rules loader test use
  > webpack treats every file (.css, .html, .scss, .jpg, etc.) as a module. However, webpack only understands JavaScript.
  > Loaders in webpack transform these files into modules as they are added to your dependency graph.

- plugins


### git

#### git 是什么

dist branch

权限

git config
  email/user
  safecrlf
  autocrlf

ssh

git workflow && pullrequest

git commit


## Resource

### 排版

https://github.com/sparanoid/chinese-copywriting-guidelines


### for webpack

https://llp0574.github.io/2016/11/29/getting-started-with-webpack2/
https://webpack.js.org/


### for git

#### 推荐教程

https://www.atlassian.com/git/tutorials
https://git-scm.com/book/en/v2


#### commit message

http://jiongks.name/blog/git-commit/
http://karma-runner.github.io/1.0/dev/git-commit-msg.html


#### 推荐工具

Git for windows(official)
GitKraken
SourceTree
Git Extension
各种 IDE 或编辑器的 plugin


### es6

http://es6.ruanyifeng.com/


## sass 的替代

### stylus

http://stylus-lang.com/


### cssnext

http://cssnext.io/