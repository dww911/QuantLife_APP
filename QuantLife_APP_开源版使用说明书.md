# QuantLife APP 开源版使用说明书

版本说明：当前开源代码版本为 `0.3.0+10`。本文件夹内现有 Android 安装包为旧版 `0.1.0 build6`，如需最新版安装包，需要重新打包生成。

## 1. QuantLife 是什么

QuantLife 是一个“人生努力可视化系统”App，用来记录行动、打卡、成长主线、阶段任务和个人复盘。

这个开源版面向粉丝和个人用户，核心原则是：

- 数据优先保存在用户本机。
- 不内置作者的服务器。
- 不内置作者的 API Key。
- 用户可以自己配置 AI API 来使用 AI 功能。
- 是否打赏支持完全自愿，不影响 App 使用。

## 2. 文件夹内容说明

当前文件夹里可能包含：

- `QuantLife_local_v0.1.0_build6.apk`：Android 安装包，旧版。
- `IOS版本使用方式.txt`：iOS / TestFlight 使用说明。
- `支持 QuantLife.pdf`：项目支持说明。
- `QuantLife_APP_开源版使用说明书.md`：当前说明书。

如果后续生成了新版 APK，建议命名为：

```text
QuantLife_local_v0.3.0_build10.apk
```

## 3. Android 手机怎么安装

1. 把 `.apk` 文件发送到 Android 手机。
2. 在手机文件管理器中点击 APK。
3. 如果系统提示“禁止安装未知来源应用”，请按提示允许当前文件管理器或浏览器安装。
4. 安装完成后打开 QuantLife。

注意：

- Android 安装包不能用于 iPhone。
- 当前文件夹内 APK 是旧版 `0.1.0 build6`，不是最新 `0.3.0+10`。
- 如果你想给粉丝发布最新版，请先重新生成 Android APK。

## 4. iPhone 怎么使用

iPhone 不能直接安装 Android 的 `.apk` 文件。

iOS 版本需要通过 TestFlight 或 App Store 分发。当前项目已配置 Codemagic 的 iOS TestFlight 构建流程，仓库地址：

```text
https://github.com/dww911/quantlife-app
```

Codemagic workflow：

```text
ios-testflight
```

成功上传到 TestFlight 后，用户可以通过 TestFlight 邀请链接安装。

## 5. 第一次打开 App

首次打开时，App 会让你创建本地档案：

1. 填写昵称。
2. 填写最近想推进的目标。
3. 点击“开始使用”。

本地版会把成长数据保存在当前设备上。卸载 App、清空应用数据或更换设备，都可能导致本地数据丢失。重要数据请自行备份。

## 6. AI 功能怎么用

开源版不自带作者的 AI 服务和 API Key。

用户可以自己配置 OpenAI 兼容接口：

1. 打开 App。
2. 进入“我的”。
3. 点击“设置”。
4. 进入“AI 助手设置”。
5. 开启“使用自己的 AI API”。
6. 填写：

```text
Base URL
API Key
Model
```

示例：

```text
Base URL: https://api.openai.com/v1
Model: gpt-4o-mini
```

API Key 请填写用户自己的密钥。作者不会提供，也不会收集。

## 7. 支持哪些 AI 接口

目前按 OpenAI 兼容接口设计，调用路径为：

```text
/v1/chat/completions
```

理论上支持：

- OpenAI 官方 API。
- 兼容 OpenAI 格式的第三方服务。
- 自己部署的兼容网关。
- 本地大模型服务，只要它兼容 `/v1/chat/completions`。

如果接口不兼容，AI 解析或 AI 规划可能失败。

## 8. 本地数据和隐私说明

开源本地版默认不连接作者服务器。

用户自己填写的 AI API 配置保存在手机本机。使用 AI 功能时，用户输入的内容会发送到自己配置的 AI 服务商。因此：

- 请确认你信任所填写的 AI 服务商。
- 不建议输入身份证号、银行卡号、住址等敏感信息。
- 如果使用第三方 API，请自行阅读该服务商的隐私政策和计费规则。

## 9. 常见问题

### 为什么 AI 功能提示需要配置 API？

因为开源版不内置作者的 API Key。请到“我的 > 设置 > AI 助手设置”中填写自己的 API。

### 为什么 Android 包不是最新版？

因为当前文件夹里的 APK 是之前生成的旧包。最新代码已经到 `0.3.0+10`，需要重新打包才会生成新版 APK。

### 为什么 iPhone 不能安装 APK？

APK 是 Android 安装包。iPhone 需要通过 TestFlight 或 App Store 安装。

### 数据会同步到云端吗？

开源本地版默认不接作者服务器。当前主要按本地存储使用。后续如果用户自己接服务器，需要自行承担部署、数据安全和维护责任。

### 我可以修改源码自己发布吗？

可以按开源仓库的许可证要求使用。发布前请确认：

- 不要把自己的 API Key 写进源码。
- 不要把服务器密钥、证书、`.p8` 文件上传到公开仓库。
- 修改 Bundle ID、应用名、图标等发布信息，避免和原项目冲突。

## 10. 给开发者的打包提示

Android 打包示例：

```bash
flutter build apk --release \
  --build-name=0.3.0 \
  --build-number=10 \
  --dart-define=LOCAL_EDITION=true \
  --dart-define=BETA_INVITE_GATE=false
```

iOS TestFlight 使用 Codemagic：

```text
workflow: ios-testflight
```

每次上传 TestFlight，build number 都必须递增。例如：

```text
0.3.0+10
0.3.0+11
0.3.0+12
```

## 11. 项目支持

如果 QuantLife 对你有帮助，欢迎自愿支持项目继续维护。

支持不是购买功能，也不会影响任何功能使用。你也可以通过 Issue、PR、建议反馈、产品设计、UI/UX、开发共创等方式参与项目。

开源仓库：

```text
https://github.com/dww911/quantlife-app
```

让努力可视化，人生不再模糊。
