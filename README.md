# 🎯 QuantLife APP 开源分享包

![platform](https://img.shields.io/badge/platform-Android%20%7C%20iOS-blue)
![edition](https://img.shields.io/badge/edition-local--first-22c55e)
![version](https://img.shields.io/badge/code%20version-0.3.0%2B10-8b5cf6)
![android](https://img.shields.io/badge/android%20apk-0.1.0%20build6-f97316)
![ai](https://img.shields.io/badge/AI%20API-user%20configured-0ea5e9)
![privacy](https://img.shields.io/badge/privacy-no%20built--in%20server-111827)
![status](https://img.shields.io/badge/status-open%20sharing-brightgreen)

QuantLife 是一个 **本地优先的开源人生努力可视化 App**，用于记录打卡、成长主线、阶段任务、长期目标和个人复盘。

这个仓库用于向粉丝分享 QuantLife APP 的开源版安装包与使用说明。开源版不内置作者服务器，不内置作者 API Key，用户可以在本机保存数据，并自行配置 OpenAI 兼容 API 使用 AI 功能。

> 让努力可视化，人生不再模糊。

---

## 📦 仓库内容

| 文件 | 说明 |
| --- | --- |
| `QuantLife_local_v0.1.0_build6.apk` | Android 安装包，当前仓库内现有 APK 为旧版 |
| `IOS版本_使用和下载方式.txt` | iOS / TestFlight 使用说明 |
| `QuantLife_APP_开源版使用说明书.md` | 完整中文使用说明书 |
| `支持 QuantLife.pdf` | 自愿支持项目说明 |

> 注意：当前仓库内 APK 是 `0.1.0 build6`。最新开源代码版本已到 `0.3.0+10`，如需最新版 Android 安装包，需要重新打包生成。

---

## ✨ 核心特性

### 🧭 人生主线

把长期目标拆成阶段、任务和今日行动，让成长路径更清楚。

### ✅ 打卡记录

记录每天的行动、投入时间、完成质量和成长经验。

### 📈 努力可视化

通过等级、经验、成长维度和阶段进度，把抽象努力变成可见反馈。

### 🤖 自定义 AI API

开源版不内置作者的 AI Key。用户可以在 App 内自行配置：

```text
Base URL
API Key
Model
```

支持 OpenAI 兼容的 `/v1/chat/completions` 接口。

### 🔒 本地优先

默认不连接作者服务器。成长数据优先保存在用户本机。

---

## 📱 Android 安装

Android 用户请下载仓库里的 APK 文件安装。

当前 Android 安装包：

```text
QuantLife_local_v0.1.0_build6.apk
```

安装步骤：

1. 点击仓库文件列表里的 `QuantLife_local_v0.1.0_build6.apk`。
2. 点击 GitHub 页面里的 `Download raw file` 下载 APK。
3. 把 APK 发送到 Android 手机，或直接在 Android 手机上下载。
4. 点击 APK 安装。
5. 如果系统提示“未知来源应用”，按提示允许当前浏览器或文件管理器安装。
6. 安装完成后打开 QuantLife，创建本地档案。

说明：

- APK 只能用于 Android 手机，不能用于 iPhone。
- 当前仓库内 APK 是旧版 `0.1.0 build6`。
- 最新开源代码版本是 `0.3.0+10`，如果需要最新版 Android 安装包，需要重新打包。

---

## 🍎 iOS 使用

iPhone / iPad 用户请通过 TestFlight 安装 QuantLife。

TestFlight 邀请链接：

```text
https://testflight.apple.com/join/UrdwF1Z9
```

安装步骤：

1. 在 App Store 搜索并下载 TestFlight。
2. 使用 iPhone 或 iPad 打开上面的 TestFlight 邀请链接。
3. 点击“接受”。
4. 点击“安装”。
5. 安装完成后，在桌面打开 QuantLife。

如果微信里无法直接跳转，请复制链接到 Safari 浏览器中打开。

更多说明请查看：

```text
IOS版本_使用和下载方式.txt
```

注意：

- iPhone 不能安装 Android 的 `.apk` 文件。
- 当前 iOS 版本通过 TestFlight 分发。
- 建议系统版本为 iOS / iPadOS 16 或以上。

开发者可通过 Codemagic 构建 TestFlight 包：

```text
workflow: ios-testflight
```

---

## 🔧 AI API 配置方式

打开 App 后进入：

```text
我的 → 设置 → AI 助手设置
```

然后开启：

```text
使用自己的 AI API
```

填写示例：

```text
Base URL: https://api.openai.com/v1
Model: gpt-4o-mini
API Key: 你自己的 API Key
```

说明：

- API Key 只保存在用户本机。
- 作者不会提供、收集或托管用户的 API Key。
- 使用第三方 AI 服务时，请自行确认费用、隐私政策和可用性。

---

## 🛡️ 隐私与安全

开源分享版遵循以下原则：

- 不内置作者服务器地址。
- 不内置作者 API Key。
- 不上传用户数据到作者服务器。
- 用户自行配置的 API 信息保存在本机。
- 使用 AI 功能时，输入内容会发送到用户自己配置的 AI 服务商。

请不要在公开仓库中提交：

```text
API Key
服务器密码
证书文件
.p8 私钥
数据库密码
```

---

## 🧑‍💻 开源源码

源码仓库：

```text
https://github.com/dww911/quantlife-app
```

当前分享包仓库：

```text
https://github.com/dww911/QuantLife_APP
```

---

## 🚀 开发者打包参考

Android 打包：

```bash
flutter build apk --release \
  --build-name=0.3.0 \
  --build-number=10 \
  --dart-define=LOCAL_EDITION=true \
  --dart-define=BETA_INVITE_GATE=false
```

iOS TestFlight 构建：

```text
codemagic.yaml → ios-testflight
```

每次上传 TestFlight，build number 必须递增：

```text
0.3.0+10
0.3.0+11
0.3.0+12
```

---

## 🤝 参与共创

欢迎通过这些方式参与 QuantLife：

- 提 Issue。
- 提 Pull Request。
- 反馈使用体验。
- 参与 UI / UX 设计。
- 分享成长方法和产品建议。
- 帮助完善文档和安装说明。

---

## ☕ 支持 QuantLife

如果这个项目对你有帮助，欢迎自愿支持项目继续维护。

支持不是购买功能，也不会影响任何功能使用。你也可以通过反馈、共创、设计、开发和传播来支持 QuantLife。

---

## 📌 项目愿景

QuantLife 希望帮助每个人更清楚地看见自己的努力：

```text
记录行动 → 形成反馈 → 看见成长 → 推进人生主线
```

让努力可视化，人生不再模糊。
