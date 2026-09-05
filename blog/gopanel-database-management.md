# 这么多年，我还是最习惯 phpMyAdmin

数据库管理，有非常多优秀的工具。

但这么多年，我还是最习惯 phpMyAdmin。

不是因为它漂亮。是因为它**顺手**。

也因为，我们认识二十多年了。

从最早的网吧，到后来的公司，它一直都在。

### 开始用 PostgreSQL 了

后来，PostgreSQL 成了我的主力数据库，SQLite 也偶尔会用。

我发现自己每天都在几个工具之间来回切换。

管 MySQL，打开 phpMyAdmin；

管 PostgreSQL，打开 pgAdmin；

看 SQLite，又换另一个工具。

时间久了，我越来越希望，无论是什么数据库，都能用同一套交互、同一种操作方式。

至于偶尔的大库导入导出，我也更希望它能在后台慢慢执行，而不是一直占着浏览器等待完成。

### 所以，我把这套习惯搬进了 GoPanel

GoPanel 里内置了数据库管理。打开就能用，不用再装 PHP，也不用再单独部署 phpMyAdmin，它默认就内置好了数据库管理。

或许有人会问，为什么还要造一个数据库管理工具？

因为我每天都在用。

使用频率高到，我只想让它再方便一点。

所以就做了。

![GoPanel 数据库列表](../assets/gopanel/GoPanel-database-list.png)

学会一种操作方式，就能管理 MySQL、PostgreSQL 和 SQLite。

交互逻辑基本沿用了 phpMyAdmin。

点进去看表结构、改字段、加索引，跟 phpMyAdmin 一模一样的操作逻辑：

![GoPanel 数据库字段管理](../assets/gopanel/GoPanel-database-manage-fields.png)

该有的都有：字段类型、长度、默认值、注释、主键、自增。不用写一行 SQL。

### 大库导入导出

这些年我自己觉得不太顺手的地方，我尽量把它补上。

因为导入导出走的是后端进程，不是 PHP 那个 30 秒就超时的 HTTP 请求。

传一个 500MB 的 SQL 文件，后端慢慢跑，前端看进度条。跑完了告诉你。

![GoPanel 数据库备份进度](../assets/gopanel/GoPanel-database-backup.png)

备份也是一样，实时进度看得见，不会跑到一半超时给你一个白屏。

### 为什么不直接用命令行

能用。

我天天用。

但是我就是不想敲 `psql -U postgres -d mydb -c "SELECT * FROM users LIMIT 10"` 这种东西。

有些时候，我只是想快速看一眼表里有几条数据、某个字段是什么类型。

### 关于 GoPanel

GoPanel 是一个开源的服务器管理面板，支持多服务器管理。

不只是数据库——网站、容器、SSL 证书、定时任务、文件管理，都能管。

而且它不只是用来管远程服务器的——直接装在你本地电脑（Mac/Linux）或局域网 NAS 上，当本地面板用。本地开发管数据库、跑容器、看日志，一个面板全搞定。

如果你也受够了每次管数据库都要开终端或装一堆工具，可以试试：

👉 [在线演示](https://demo.gopanel.run)

👉 [GoPanel GitHub项目地址](https://github.com/hoxiai/gopanel)

开源免费，自己部署，数据在你自己服务器上。

### 最后

好的工具不需要你学习它，而是它适应你。

很多成熟的软件，真正值得学习的不是代码，而是那些已经被无数人验证过的交互习惯。

phpMyAdmin 教会了我这一点。我只是把它搬了个家。

一直关注我的朋友应该知道，我最近一直在写《底层重构》，这些年我做过的项目、思考的点、对产品的理解、遇到的问题以及解决方案，后续的故事连载里都会写进去。

有兴趣的朋友欢迎看看：👉 [底层重构](https://github.com/hoxiai/Refactoring-the-Self)

咱长长久久。

![Visits](https://svgstat.com/svg/refactoring-the-self/counter/visits.svg?page_id=blog/gopanel-database-management)
