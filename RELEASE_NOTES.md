# Release Notes

## v2.0.0

发布日期：2026-06-02

这是 Web 控制台的第二个正式版本，重点降低首页复杂度，并补充更多通知平台。

### 本版更新

- 新增 `Slack Incoming Webhook` 通知
- 新增 `Gotify` 通知
- Web 控制台重构为单页卡片式布局
- 设置项改为弹出式二级界面
- 历史记录与诊断日志默认仅展示最近四条，可按需查看完整内容
- 通知通道输入框会根据平台显示对应的地址提示

### Gotify 配置

创建 Gotify 应用并取得 Token 后，填写完整消息接口地址：

`https://gotify.example/message?token=...`

---

## v1.0.0

发布日期：2026-04-24

这是当前第一版稳定可交付版本，适合个人生产环境使用。

### 本版包含

- `C4D` 渲染完成通知
- `C4D` 渲染队列完成通知
- 超时提醒
- 飞书 `Webhook`
- `Server酱`
- 通用 `Webhook`
- 托盘常驻
- 开机自启
- 静默启动，无黑框
- 浏览器 Web 控制台
- 中文界面
- 通知模板配置
  - 渲染完成
  - 超时提醒
  - 测试消息
- 通知字段编排
  - 状态
  - 机器
  - 工程
  - 时间
  - 渲染模式
  - 输出路径
  - 开始时间

### 当前正式入口

- `watcher/TongzhiWatcher.exe`

### 配置位置

程序运行时默认读取：

`%APPDATA%\TongzhiRenderNotifier\`

其中主配置文件为：

`%APPDATA%\TongzhiRenderNotifier\tongzhi_render_notifier.json`

### 迁移说明

如果你在当前机器上已经配置好通知通道和模板，打包版会默认继续使用这些设置。

如果要迁移到另一台电脑，请一并复制：

`%APPDATA%\TongzhiRenderNotifier\tongzhi_render_notifier.json`

### 已知边界

1. 渲染状态采集仍依赖 `C4D Python` 插件
2. 完成识别包含兜底推断逻辑
3. 输出文件判断依赖实际渲染结果落盘
