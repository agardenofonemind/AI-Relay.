# AR-0001：Android 项目骨架与云端 APK 构建验证

- 状态：active（真机验证通过，待 Gemini 独立审查）
- 优先级：P1
- 主执行者：GPT
- 复核者：Gemini
- 关联里程碑：M1-A
- 目标设备：iQOO Neo 9 / Android 16

## 背景

用户主要通过 Android 手机浏览器操作 GitHub，没有可默认依赖的 Android Studio 桌面开发环境。因此先验证 GitHub 云端构建 APK 的工作流，建立手机端开发与真机测试闭环。

## 范围

### 包含
- 创建最小 Kotlin + Jetpack Compose 项目。
- 配置 Android Gradle Plugin、Gradle 云端构建环境和依赖。
- 创建 GitHub Actions Debug APK 构建工作流。
- 保存可下载的构建产物。
- 在目标手机上安装并启动。

### 不包含
- GitHub 正式状态同步功能。
- Room / SQLite。
- ChatGPT / Gemini 模型 API。
- Accessibility Service。
- 完整任务管理界面。

## 验收条件

- [x] 仓库具有完整且可构建的 Android 项目骨架。
- [x] GitHub Actions 成功完成 Debug APK 构建。
- [x] 用户能够下载构建产物。
- [x] APK 能在 iQOO Neo 9 / Android 16 安装。
- [x] 应用能够正常启动并显示最小 Compose 页面。
- [ ] Gemini 收到必要源码或 Diff 后完成独立审查。

## 当前实现说明

- Android 项目位于 `android/`，避免与仓库根目录的协议文档混杂。
- GitHub Actions 已成功完成 Debug APK 构建；为兼容当前 Compose 依赖，compileSdk 使用 37，工作流显式安装 `platforms;android-37.0`。
- 首次 bootstrap 暂未提交 Gradle Wrapper；后续可评估补齐。
- 真机验证由用户于 2026-11-22 明确确认：APK 安装成功，应用正常启动，首页显示正常，无黑屏、闪退或报错。
- 本任务仍保持 active，原因是 Gemini 独立审查尚未完成。

## 构建与真机验证证据

| 项目 | 结果 |
|---|---|
| GitHub Actions Run | [#5](https://github.com/agardenofonemind/AI-Relay./actions/runs/45002335541) |
| Run ID | 45002335541 |
| Commit | `f9b53f3d3a1329fdd8bb49786488d14c2880b2bd` |
| 构建结果 | success |
| Artifact | `ai-relay-debug-apk` |
| Artifact ID | 14746167208 |
| APK SHA-256 | `a5437e72d110e34470e2a6d79046a14a1cd95bc0b6a8d84c389c12037bf00029` |
| 目标设备 | iQOO Neo 9 / Android 16 |
| 安装与启动 | 用户确认正常 |

## 交付物与可信度

| 交付物 | 可信度 | 证据 |
|---|---|---|
| Android 项目骨架 | verified | GitHub Actions Run #5 构建成功 |
| GitHub Actions 工作流 | verified | Run #5 全步骤成功 |
| Debug APK | verified | Artifact 14746167208 已上传且可下载 |
| 真机安装与启动 | verified | 用户确认安装、启动、首页显示均正常 |
| Gemini 独立审查 | pending | 尚未完成源码 / Diff 交接与审查 |
