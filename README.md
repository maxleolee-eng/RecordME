# RecordME

macOS 原生录像与录屏工具，将屏幕、摄像头和声音组合成一段本地视频。

**当前版本：1.4.13（35） · macOS 14.0 或更新版本 · Apple Silicon / Intel 通用版**

[下载安装包](https://github.com/maxleolee-eng/RecordME/releases/latest) · [提交 Bug](https://github.com/maxleolee-eng/RecordME/issues/new?template=bug_report.yml) · [版本更新](CHANGELOG.md) · [使用许可](LICENSE.txt) · [隐私说明](PRIVACY.md)

## 产品功能

| 功能 | 说明 |
| --- | --- |
| 组合录制 | 屏幕、摄像头可独立启用；支持画中画、左右分屏、上下分屏，可调整画面比例与位置。 |
| 两路声音 | 可选麦克风、系统声音，混合为一条 AAC 音轨。建议使用耳机减少回声。 |
| 录制控制 | 实时预览、悬浮控制胶囊、菜单栏状态提示、手动暂停和继续；点击开始后才写入录像。 |
| 画质选择 | 720p、1080p、4K；24、30、60 fps；多档编码质量。实际性能取决于设备与来源。 |
| 无人暂停 | 可选本地人体检测，摄像头启用时按无人超时自动暂停、检测到人后恢复；不识别身份。 |
| 时间与地点 | 时间水印、地点水印可分别关闭；地点通过 macOS 定位与地理编码服务获得。 |
| 录像管理 | 日历周/月视图浏览录像；按开始年月归档，支持自选保存文件夹。 |
| 中断恢复 | 分段写盘，异常结束后提供保留片段的恢复合并；不能保证断电零损失。 |
| 中英文界面 | 支持简体中文和 English。 |

默认画质为 1080p / 30 fps。4K / 60 fps 长时录制和复杂人体检测场景仍需按你的设备评估；本发布未完成跨 Mac 实体采集验收。应用通过 ScreenCaptureKit 排除自身窗口，具体捕获结果应以实际视频为准。

## 下载与安装

1. 阅读[使用许可](LICENSE.txt)。当前仅授权个人非商业使用；工作、经营、付费内容制作等商业用途需另行获得书面许可。
2. 从 [Releases](https://github.com/maxleolee-eng/RecordME/releases/latest) 下载 `RecordME-1.4.13-universal-signed.dmg`，打开后将 `RecordME-1.4.13.app` 拖入“应用程序”。安装后可将应用名称改为 `RecordME.app`。应用安装包仅提供 DMG，不提供 ZIP。
3. 从“应用程序”启动 RecordME，按需授予录屏、摄像头、麦克风权限。地点水印需要额外定位授权。
4. 选择来源与布局，点击开始。停止后在日历窗口查看保存结果。

关闭正在录制的预览窗口会停止并保存；最小化会继续录制。未录制时关闭预览返回菜单栏待机。退出请使用菜单栏“退出 RecordME”。

默认录像位置为当前用户文稿目录下的 `RecordME/录像/yyyy-MM/`，可在设置中更改。更新前请先停止并保存正在进行的录像。不要删除尚待恢复的 `.RecordME-Sessions` 目录；合并时需要额外可用磁盘空间。

安装包已使用 Developer ID 签名，App 与 DMG 均附加 Apple 公证票据。公证不等于 App Store 审核或产品质量认证。首次启动与设备权限仍由 macOS 决定；不需要关闭 Gatekeeper。

### 校验下载

将安装包和 `SHA256SUMS.txt` 放在同一文件夹，在该文件夹打开终端。例如校验 DMG：

```sh
shasum -a 256 RecordME-1.4.13-universal-signed.dmg
```

将输出与 `SHA256SUMS.txt` 对应行比较。下载全部附件后也可执行 `shasum -a 256 -c SHA256SUMS.txt`。

## 隐私、依赖与反馈

录像与设置保存在本地或你选择的目录。当前版本没有账户登录、广告或第三方统计 SDK，不自动向开发者上传录制内容。可选定位涉及 Apple 系统服务；同步文件夹和公开 Issues 各有自己的数据处理方式，详见[隐私说明](PRIVACY.md)。

运行无需安装 Xcode、Homebrew、Python、FFmpeg、模型文件或其他开发工具。依赖与路径检查范围见[依赖说明](DEPENDENCIES.md)。

请按[支持说明](SUPPORT.md)提交可复现的 Bug。Issues 是公开的，请先遮盖截图中的个人信息，不要上传完整录像、账号凭证或未经清理的日志。

## 仓库与许可范围

本仓库只发布产品文档、许可、反馈模板与版本记录。可运行文件通过 Releases 提供。应用源码、构建脚本、测试、内部记录、签名私钥和开发历史不公开，也不接收代码贡献。

这是闭源专有软件，采用[个人非商业使用许可](LICENSE.txt)，禁止未经授权的商业使用、修改、二次开发、换皮、魔改、功能或界面改版、衍生、重新打包、再分发和转售。许可证不提供技术防破解保证，适用法律的强制例外仍有效。

GitHub 会自动显示本仓库的 ZIP/TAR 下载与平台操作入口；其中只有本仓库的公开文档，不含 RecordME 应用源码。

---

RecordME is a native macOS screen and camera recorder. Requires macOS 14+, supports Apple Silicon and Intel. Download signed and notarized builds from [Releases](https://github.com/maxleolee-eng/RecordME/releases/latest). This is a binary distribution and support repository; application source code is private. Personal, non-commercial use only. Modification, secondary development, reskinning, altered versions, derivative works, redistribution and commercial use require written permission. Read [LICENSE.txt](LICENSE.txt) before use.
