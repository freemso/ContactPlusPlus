# 小组讨论记录

## 9 月 16 号
### 议程

1. 项目选题
2. 工作流、沟通渠道、代码仓库搭建

### 备选题

1. Text analysis tool, online/offline
2. Advanced contact app 【最终选择】
3. 课程网站生成器
4. ...

### 沟通渠道

1. WeChat
2. Email
3. 代码仓库：https://github.com/freemso/pm_course.git
4. Trello

-----

## 10 月 12 日

### 议程

1. 技术栈选择
2. 市场调研
3. 需求分析
4. 工作量分析与分工
5. Trello 的使用

### 技术栈选择

我们要开发一个通讯录 app，自然而然，应当开发一个桌面端/移动端的客户端，而不是一个网站。  
同时，鉴于小组成员开发环境的多样性，我们希望它是一个跨平台的应用，同时支持 macOS，Windows，和 Linux。  
更进一步地，我们未来希望在移动端也可以使用。

因此，我们选择使用 [Electron](https://electronjs.org/) 作为桌面端的开发平台，在未来使用 React Native 作为移动端的开发平台。  
这意味着我们将全栈使用 JavaScript 作为主要的开发语言。

### 市场调研

最常用的通讯录应用，就是大家手机或电脑上的那个操作系统自带的。

目前市面上有[很多很好的**商用**通讯录管理软件](https://www.techradar.com/news/best-contact-management-software)，比如 [Insightly](https://www.insightly.com)，[Maximizer](https://www.maximizer.com)，[FullContact](https://www.fullcontact.com/)，和 [Nutshell](https://www.nutshell.com) 等。但他们都是面向公司、团队的，侧重商业关系的维持和管理，并且整合了许多诸如项目管理、日程管理等功能。他们大多价格不菲，不是普通用户能够接受的。

同时，市面上也有一大堆面向个人用户的通讯录管理软件，比如 [CardHop](https://flexibits.com/cardhop)，[Folk](https://folk.io/)，[Cloze](https://www.cloze.com/)，[Addappt](http://site.addappt.com/)，[Sync.Me](https://sync.me/)，[Contact+](https://www.contactspls.com/)，和 [Covve](https://covve.com/) 等。其中不乏做得非常好的。它们之中有 macOS 客户端，有 iOS 客户端，还有 Android 与 iOS 都支持的。它们之中有单机版的（即不需要注册，安装即可用的），也有需要注册的。

其中，最符合我们的需求的，是 [Cloze](https://www.cloze.com/)。我们决定在一定程度上参考 Cloze 的设计。

### 需求分析（功能列表）

我们要做的通讯录应用，首先得有通讯录的基础功能：

- 与主流通讯录服务（比如 Outlook、Google、iCloud）的整合
- 支持联系人的增删改查
- 支持联系人分组、tag 系统
- Import from vCard/CSV
- Export to vCard/CSV

其次，要加入这几个大的功能：

- 社交平台整合（RSS）。通过官方或非官方的 API，实现与主流社交平台的联结，从而能够订阅不同社交平台关于某个用户的更新。根据 API 的不同，可能会提供 post to 的功能。
- 你与TA的互动记录（LOG）。整合主流邮件服务、社交平台的私信（if possible）和主流即时通讯软件（if possible）中你与 TA 的互动记录。根据 API 的不同，可能会提供发信的功能。参考 [Buffer](https://buffer.com/)。
- 多媒体文件管理。【太难，考虑放弃】。

### 工作量分析与分工

我们首先要做一个基于 Electron 的桌面端应用，移动端先放弃。因此，不需要移动端开发和后端开发，只有一个桌面端。Electron 是跨平台的，因此不论用 Linux，Windows 还是 macOS 的人都可以参与开发并在自己的机器上部署测试。即便是桌面应用，还是可以分为前端和后端，具体怎么分，等大家对 Electron 稍微熟悉一点之后再讨论。

大的来看，目前可以看到的工作按时序排有以下几个：

1. 需求分析；原型设计（UI 设计和交互设计）；社交平台和即时通讯软件调研
   1. 如果老师没有特殊要求的话，需求分析上面写的就足够了，具体的细节，可以找项目经理欧承祖沟通
   2. 原型设计使用 Adobe XD 做，它是跨平台的软件，Windows 和 macOS 都可以使用
   3. 社交平台和即时通讯软件调研，主要是列举大家最常用的的社交平台（比如 Twitter、豆瓣）和即时通讯软件（Telegram，Slack），调查是否有官方或非官方的 API 提供
2. 后端开发；前端开发；第三方服务整合；
   1. 后端开发包括后台逻辑，本地文件 IO 操作等，需要熟悉 Electron，属于事务逻辑层和 Database 层
   2. 前端开发包括界面开发（HTML+CSS）和与后端的交互（JS），属于 View 层
   3. 第三方服务整合包括与通讯录和邮件服务（这两个一般在一起）、社交平台服务、即时通讯软件的联结逻辑，基本属于对外网络层
3. 单元测试和集成测试
   1. 单元测试由相应模块的开发人员自己写，最好找另一个人 review 一下
   2. 集成测试等完成三个模块的全部开发之后再做。

### Trello 的使用

本项目将使用 [Trello](https://trello.com) 作为项目管理的工具。项目的 [Trello 链接](https://trello.com/b/dv9FUoqx/%E9%80%9A%E8%AE%AF%E5%BD%95-%E9%A1%B9%E7%9B%AE%E7%AE%A1%E7%90%86%E8%AF%BE%E7%A8%8B%E9%A1%B9%E7%9B%AE)。