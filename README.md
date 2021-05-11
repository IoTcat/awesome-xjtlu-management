# awesome-xjtlu-management

企划

## 页面设计

整个网站分为5个页面：登录/注册页面，用户profile页面，文章管理页面，文章编辑页面，展示页面。


### 登录/注册页面
 - 仅支持用户使用xjtlu邮箱进行验证码登录（注册同理）
 - 登录后将用户从定向至用户profile页面

### 用户profile页面
 - 自动根据邮箱生成用户英文姓名
 - 自动根据邮箱生成用户入学年份
 - 显示用户的注册邮箱
 - 显示用户ID（注册邮箱@前内容）
 - 显示用户的权限(admin或user)
 - 用户可编辑的中文姓名
 - 用户可添加一个其他邮箱，供接收通知
 - 用户可添加微信号
 - 用户profile隐私偏好：公开；仅向xjtlu学生展示；不展示


### 文章管理页面
 - user展示所有此用户的文章
 - admin展示全站所有文章
 - 显示文章标题
 - 显示文章分类
 - 显示文章作者
 - 显示文章创建时间
 - 显示文章最后修改时间
 - 安装文章最后修改时间倒序
 - 显示文章状态：未发布，已发布，修改中。
 - 显示文章点赞/点踩次数
 - 显示文章浏览次数
 - 用户可点击指定文章进入编辑页面

### 文章编辑页面
 - 用户能够方便地编辑文章
 - 文章自动保存草稿（未发布或修改中）
 - 一键插入模板
 - 允许用户在文章中添加仅xjtlu学生可见内容
 - 能够选择文章分类
 - 能够编辑文章标题
 - 支持配置文章状态（发布，撤回发布，删除，保存草稿）
 - 支持插入图片


### 展示页面
 - 将各分类文章合理地展示
 - 加载速度应非常快
 - SEO
 - 支持仅xjtlu用户显示内容的页内弹窗
 - 支持文章点赞/点踩并显示点赞/点踩次数
 - 记录各文章浏览次数
 - 显示文章标题
 - 根据用户隐私配置显示作者信息
 - 显示发布时间
 - 显示最后编辑时间
 - 支持评论，且评论应对作者（和admin）作标识
 - 设立留言区，获取改进意见


## 组件设计

网站配备若干组件，实现相应功能。

### 导航栏组件

文章管理页面，文章编辑页面，用户profile页面应当共享同一个导航栏。导航栏上应该有以下选项：展示页面，文章管理，新建文章，设置，登出。

导航栏应当全平台适配。

### 邮件通知组件
用于发送登录验证码，以及评论通知。


### 页内弹窗组件
用于在展示页面内显示xjtlu用户可见内容。



### 统计组件
用于统计访客信息。




## 实现方案（法一）

利用多种先进工具，自主搭建。

展示页面使用现有的[awesome-xjtlu](https://github.com/awesome-xjtlu/wiki)基于Github page的静态站作为展示页面，使用git push自动化脚本实现页面内容更新。
其它后台页面使用Vue+Express快速搭建，其中编辑页面中的编辑器基于[editor.me](https://github.com/pandao/editor.md)搭建。邮件系统基于我的[email API](https://www.eee.dog/tech/mail-api.html)。统计使用google analysis。页内弹窗使用[izimodal](https://izimodal.marcelodolza.com/)实现。

### 技术栈
 - Docker
 - NodeJS
 - MongoDB
 - Express
 - Vue
 - Webpack
 - TypeScript
 - ESLint
 - Babel

### 工作流
 - Kubernetes
 - helm
 - drone
 - github

## 实现方案（法二）

在[NodeBB](https://nodebb.org/)开源论坛源码的基础上进行修改。


### 技术栈
 - Docker
 - NodeJS
 - NodeBB
 - MongoDB

### 工作流
 - Kubernetes
 - helm
 - drone
 - github
 
