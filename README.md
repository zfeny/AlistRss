## 介绍
一个针对个人用户、下载爱好者，实现无人RSS订阅下载并推送Alist的服务。

## 使用方法
- 修改data目录下的config.json文件
- 将需要订阅的rss源写入csv文件
  - url、path为必选值，其中path根据设置里用户的基本路径来设置
- 使用`chmod -x start.sh`给脚本赋予可执行权限
- `./start.sh`开启脚本，随后自动订阅RSS源并离线下载至Alist对应存储中。

## 开发计划
### 功能需求
- [x] RSS订阅 ✅ 2023-10-02
- [x] 磁链提取 ✅ 2023-10-02
- [x] Alist集成 ✅ 2023-10-02
	alist的脚本需要完成推送磁链和下载到对应目录的任务。
	之前的文件里需要给它的信息有：磁链，rss源名称。
- [x] 数据库：监控与追踪 ✅ 2023-10-03
	创建一个数据库来存储已处理的RSS项目和磁链，以便追踪下载状态和避免重复工作。
- [x] 定时任务 ✅ 2023-10-03
	设置定时任务，以便定期运行RSS订阅和磁链提取代码。这可以使用Cron或其他调度工具来实现。
- [x] 通知系统 ✅ 2023-10-02
- [ ] 一个易于操作的web前端用户界面
- [ ] 字幕组新作品通知
- [x] 更换rss源订阅信息储存方式 ✅ 2023-10-04
	json文件写起来太麻烦了，要不试试database
- [ ] 通过BagumiID和SubscribeID获取字幕组与番剧信息，生成海报墙
- [ ] 制作一个容易操作的shell脚本面板
- [ ] 增加其他消息推送途径，如钉钉、企业微信应用
- [ ] 下载番剧自动分类功能
- [ ] 完成README上传

### 非功能需求
- [ ] 安全性
- [x] 可扩展性和可维护性 ✅ 2023-10-04
- [x] 将Python函数模块化 ✅ 2023-10-04

## 开发日志
- 2023/10/01
	- 19:58，初步测试了rss订阅。
- 2023/10/02
	- 19:42，集成Alist，初步实现rss推送下载
	- 20:15，集成TGbot，实现任务消息推送
- 2023/10/03
	- 21:08，设置数据库，加快运行速度
- 2023/10/04
	- 22:25，上传README