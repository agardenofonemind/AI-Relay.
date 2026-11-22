# AI Relay 当前状态

- 协议版本：0.2
- 项目阶段：M1 — Android 本地任务管理原型
- 总体状态：M1-A — 云端 APK 构建验证进行中
- 最后更新：2026-11-22

## 当前目标

先建立 Android 项目骨架与 GitHub Actions 云端 Debug APK 构建闭环，再进行真机安装验证。M1-B 本地任务管理界面将在构建链路验证后启动。

## 已确认决策

| 项目 | 决策 |
|---|---|
| 实现边界 | Local-first；不调用模型 API |
| 正式状态源 | GitHub 仓库 |
| 本地数据 | MVP 阶段仅作为缓存、草稿和待提交内容 |
| 共享工作区 | GitHub |
| 开发节奏 | Gradual，分阶段交付 |
| 首个集成项目 | Arknights RIIC 排班工具 |
| 任务认领 | 手动认领；不做自动心跳和自动超时回收 |
| 可信度 | 标记具体交付物和结论 |
| 写入保护 | 更新前读取最新远端文件并检查 SHA；冲突时停止覆盖 |
| 仓库写入 | 初期由 GPT 负责，Gemini 提供审查与交接建议 |
| 关键操作 | 发送、覆盖、合并、发布和解除认领前由用户确认 |
| 主协作仓库 | [agardenofonemind/AI-Relay.](https://github.com/agardenofonemind/AI-Relay.)（公开仓库，名称末尾含句点） |
| Android 项目 | `android/`；Kotlin + Jetpack Compose |
| 首期构建 | GitHub Actions 云端构建 Debug APK；暂不要求本地 Android Studio |

## 活跃任务

| Task ID | 标题 | 状态 | Assignee | Claimed At | Last Updated |
|---|---|---|---|---|---|
| AR-0001 | Android 项目骨架与云端 APK 构建验证 | active | GPT | 2026-11-22 | 2026-11-22 |

任务卡：[tasks/AR-0001-android-build.md](tasks/AR-0001-android-build.md)

## 关键阻塞点

- 首次 GitHub Actions 构建尚未运行或验证。
- Debug APK 尚未生成，目标手机尚未安装测试。
- Gradle Wrapper 暂未提交；首次 bootstrap 使用云端固定版本 Gradle，待构建成功后评估补齐。

## 里程碑

- [x] M0：协作协议建立、双模型评审并经用户确认
- [ ] M1-A：Android 项目骨架与云端 Debug APK 构建验证
- [ ] M1-B：Android 本地任务管理原型
- [ ] M2：GitHub 仓库读写与 SHA 版本冲突处理
- [ ] M3：ChatGPT / Gemini 客户端分享交接
- [ ] M4：半自动化、差异比较与复核流程

## 下一步

1. 运行并修复首次 Android 云端构建。
2. 下载 Debug APK，在 iQOO Neo 9 / Android 16 上安装并启动。
3. 将必要源码或 Diff 直接交给 Gemini 独立审查。
4. M1-A 验收通过后启动 M1-B。

## 状态维护规则

- STATE.md 只保存当前项目阶段、活跃任务/认领和最近关键阻塞点。
- 任务完成并完成交接后，在下一次状态更新时从本文件移除，并归档至 archive/。
- 任务认领、解除认领和状态变更应记录执行者及更新时间。
- 本地草稿和缓存不是正式项目状态。

## 安全提醒

本仓库为公开仓库；不得提交 Token、密码、Cookie、私钥、恢复信息或私人资料。
