# AR-0001：Android 项目骨架与云端 APK 构建验证

- 状态：active
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

- [ ] 仓库具有完整且可构建的 Android 项目骨架。
- [ ] GitHub Actions 成功完成 Debug APK 构建。
- [ ] 用户能够下载构建产物。
- [ ] APK 能在 iQOO Neo 9 / Android 16 安装。
- [ ] 应用能够正常启动并显示最小 Compose 页面。
- [ ] Gemini 收到必要源码或 Diff 后完成独立审查。

## 当前实现说明

- Android 项目位于 `android/`，避免与仓库根目录的协议文档混杂。
- 首次云端构建使用 GitHub Actions 安装固定版本 Gradle，再直接执行 Gradle 命令。
- Gradle Wrapper 暂未提交；这是首次 bootstrap 的临时简化，后续可在构建成功后补齐。

## 交付物与可信度

| 交付物 | 可信度 | 证据 |
|---|---|---|
| Android 项目骨架 | unverified | 已提交源码，尚未完成云端构建 |
| GitHub Actions 工作流 | unverified | 已提交工作流，尚未运行 |
| Debug APK | unverified | 尚未生成 |
| 真机安装与启动 | unverified | 尚未测试 |
