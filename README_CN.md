# 千址盒

<div align="center">

![Android](https://img.shields.io/badge/Android-8.0%2B-3DDC84.svg)
![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF.svg)
![Java](https://img.shields.io/badge/Java-17-ED8B00.svg)
![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-2026.02.01-4285F4.svg)
![Room](https://img.shields.io/badge/Room-2.8.4-1976D2.svg)
![Version](https://img.shields.io/badge/version-7.8.3-blue.svg)

**本地优先的网址收藏、分类管理和应用内浏览工具**

[中文](README_CN.md) · [English](README.md) · [日本語](README_JA.md)

[项目网站](https://qzh.336954.xyz/) · [隐私政策](https://qzh.336954.xyz/privacy.html) · [用户协议](https://qzh.336954.xyz/agreement.html) · [下载最新版](https://github.com/wstar31/qianzhihe-site/releases/latest)

</div>

> 千址盒是一款面向个人用户的 Android 网址管理应用。它专注于收藏、分类、搜索、导入导出和应用内浏览，数据主要保存在用户设备本地，不提供注册登录功能，也不主动把收藏内容上传到开发者服务器。

---

## 当前版本

| 项目 | 内容 |
|------|------|
| 应用名称 | 千址盒 |
| 包名 | `com.star.qianzhihe` |
| 当前版本 | `7.8.3` |
| versionCode | `783` |
| 最低系统 | Android 8.0 / API 26 |
| 目标 SDK | API 36 |
| 官网域名 | `qzh.336954.xyz` |

## 下载

最新版 APK 可从 GitHub Releases 下载：

- [GitHub Releases](https://github.com/wstar31/qianzhihe-site/releases/latest)
- [v7.8.3 APK](https://github.com/wstar31/qianzhihe-site/releases/download/v7.8.3/qianzhihe_7.8.3_release.apk)
- [更新清单 update.json](https://qzh.336954.xyz/release/update.json)

> 如果安装时提示“已安装了签名冲突的应用”，说明手机上已有同包名但不同签名的旧版应用。请先在旧版内导出数据，再卸载旧版后安装新版。

---

## 项目简介

千址盒用于管理个人常用网址。用户可以添加网址、设置标题、分类、标签和备注，并通过搜索、分类筛选、置顶和访问统计快速定位收藏内容。

应用内置 WebView 浏览器，可以直接打开收藏网址或用户输入的网址，提供网页工具栏、页内搜索、复制链接、分享链接、当前页面收藏、桌面/移动浏览模式切换等能力。

## 主要功能

- **本地网址收藏**：保存网址、标题、分类、标签、备注、置顶状态和访问统计。
- **分类管理**：支持按分类组织收藏，并提供分类编辑和删除能力。
- **搜索与筛选**：可按标题、网址、标签、备注和分类进行快速筛选。
- **排序与置顶**：默认按置顶、最近访问和最近更新排序，支持标题排序逻辑。
- **导入导出**：支持 Markdown、JSON 和浏览器书签 HTML 格式，方便备份和迁移。
- **应用内浏览器**：通过 WebView 打开网页，支持多页面、返回/前进、刷新、主页、复制、分享、收藏。
- **桌面/移动模式**：内置浏览器支持桌面 UA 和移动模式切换，适配平板横竖屏缩放。
- **HTTPS 优先访问**：无协议网址默认补全为 HTTPS，失败时可回退 HTTP 并给出提示。
- **灵动岛工具栏**：主页和浏览器均提供顶部灵动岛快捷操作，支持拖动停靠、滑动隐藏和自动收起。
- **深色/浅色模式**：支持黑夜/白昼主题切换。
- **安全/沉浸模式**：可切换系统栏显示策略，兼顾沉浸体验和安全显示。
- **自动检查更新**：启动时可检查站点发布的 `update.json`，下载并引导安装新版 APK。

## 截图

### 主页与收藏列表

主页用于快速添加、搜索、筛选和打开收藏的网址。顶部灵动岛提供设置、主题和沉浸/安全显示的快捷入口。

<p align="center">
  <img src="assets/screenshots/home.jpg" alt="千址盒主页与收藏列表" width="320">
</p>

### 设置页 - 第1张

这张截图主要展示显示内容区：沉浸/安全、黑夜/白昼、毛玻璃、标签、备注、访问次数和自动隐藏。

<p align="center">
  <img src="assets/screenshots/settings-display-first.jpg" alt="设置页第1张截图" width="320">
</p>

### 设置页 - 第2张

这张截图展示较完整的设置抽屉，包括打开与浏览、更新检查、重置和帮助入口。

<p align="center">
  <img src="assets/screenshots/settings-overview-second.jpg" alt="设置页第2张截图" width="320">
</p>

### 网址管理

管理抽屉支持快速添加、直接打开、导入导出、清空数据和分类管理。

<p align="center">
  <img src="assets/screenshots/management.jpg" alt="网址管理与分类管理" width="320">
</p>

### 应用内浏览器

内置浏览器支持桌面/移动模式、页内搜索、返回前进、刷新、主页、复制、分享、收藏和多页面管理。

<p align="center">
  <img src="assets/screenshots/browser.jpg" alt="应用内浏览器与网页工具栏" width="320">
</p>

---

## 技术栈

| 模块 | 技术 |
|------|------|
| 平台 | Android |
| 语言 | Kotlin + Java |
| UI | Jetpack Compose + XML View |
| 架构 | MVVM / ViewModel / Flow |
| 数据库 | Room |
| 浏览器 | Android WebView / AndroidX WebKit |
| 图片加载 | Coil Compose |
| 构建 | Gradle Kotlin DSL / Android Gradle Plugin |
| 最低 JDK | Java 17 |

---

## 项目结构

```text
QZH/
├── app/                                      # Android 应用模块
│   ├── build.gradle.kts                     # 应用构建配置、版本号、签名配置
│   └── src/
│       ├── main/
│       │   ├── AndroidManifest.xml          # 权限、Activity、FileProvider 配置
│       │   ├── java/com/star/qianzhihe/
│       │   │   ├── MainActivity.kt          # 应用入口与主页挂载
│       │   │   ├── BrowserActivity.java     # 应用内浏览器
│       │   │   ├── AppPrefs.kt              # 本地偏好设置
│       │   │   ├── UpdateManager.kt         # 更新检测、APK 下载和安装
│       │   │   ├── data/                    # Room 数据库、DAO、实体
│       │   │   ├── ui/main/                 # 主页、抽屉、卡片、导入导出、灵动岛组件
│       │   │   └── ui/theme/                # 主题、颜色、字体
│       │   └── res/                         # XML 布局、图标、资源文件
│       └── test/                            # 单元测试
├── assets/                                  # README 资源和截图
│   └── screenshots/
├── release/                                 # 本地发布清单和 APK 目录
│   ├── update.json
│   └── download/
├── gradle/                                  # Gradle 版本目录
├── key/                                     # 本地签名文件目录，不提交到仓库
└── README.md
```

---

## 数据模型

核心数据表为 `site_table`，实体为 `SiteItem`。

| 字段 | 说明 |
|------|------|
| `title` | 收藏标题 |
| `url` | 原始网址 |
| `normalizedUrl` | 去重和匹配用规范化 URL |
| `category` | 分类，默认“未分类” |
| `tags` | 标签文本 |
| `note` | 备注 |
| `isPinned` | 是否置顶 |
| `visitCount` | 访问次数 |
| `lastVisitedAt` | 最近访问时间 |
| `openMethod` | 打开方式：自动、应用内、外部浏览器 |
| `updatedAt` | 最近更新时间 |

---

## 导入导出格式

### Markdown

支持标准 Markdown 链接和裸 URL：

```markdown
- [GitHub](https://github.com/)
- https://example.com
```

导出时会包含分类、标签和备注：

```markdown
- [GitHub](https://github.com/)
  - 分类：开发
  - 标签：代码,开源
  - 备注：常用代码托管平台
```

### JSON

支持根数组或 `{ "items": [...] }` 结构。导出示例：

```json
{
  "version": 2,
  "items": [
    {
      "title": "GitHub",
      "url": "https://github.com/",
      "category": "开发",
      "tags": "代码,开源",
      "note": "常用代码托管平台",
      "isPinned": false,
      "visitCount": 0,
      "lastVisitedAt": 0,
      "openMethod": "AUTO"
    }
  ]
}
```

### 浏览器书签 HTML

支持解析 Netscape Bookmark HTML：

```html
<!DOCTYPE NETSCAPE-Bookmark-file-1>
<DL><p>
  <DT><H3>开发</H3>
  <DL><p>
    <DT><A HREF="https://github.com/">GitHub</A>
  </DL><p>
</DL><p>
```

---

## 更新机制

应用通过站点上的更新清单检查新版本：

```text
https://qzh.336954.xyz/release/update.json
```

更新清单示例：

```json
{
  "versionName": "7.8.3",
  "versionCode": 783,
  "apkName": "qianzhihe_7.8.3_release.apk",
  "downloadUrl": "https://qzh.336954.xyz/release/download/v7.8.3/qianzhihe_7.8.3_release.apk",
  "releaseNotes": "更新内容：...",
  "releasePageUrl": "https://qzh.336954.xyz/release/download/v7.8.3/"
}
```

更新流程：

1. 读取当前已安装版本。
2. 拉取 `update.json`。
3. 对比 `versionCode`。
4. 下载 APK。
5. 校验文件类型、包名、版本号。
6. 通过 `FileProvider` 调起系统安装器。

> Android 8.0 及以上系统需要用户授予“安装未知应用”权限。

---

## 构建与运行

### 环境要求

- Android Studio / Android SDK
- JDK 17
- Gradle Wrapper
- Android SDK Platform 36
- Android Build Tools

### 克隆项目

```bash
git clone https://github.com/<owner>/<repo>.git
cd QZH
```

### Debug 构建

Windows：

```powershell
.\gradlew.bat :app:assembleDebug
```

Linux / macOS：

```bash
./gradlew :app:assembleDebug
```

### Release 构建

项目支持读取 `key/key.properties` 进行 release 签名：

```properties
storeFile=key/qianzhihe-release.jks
storePassword=your_store_password
keyAlias=qianzhihe
keyPassword=your_key_password
```

构建：

```powershell
.\gradlew.bat clean assembleRelease
```

输出位置：

```text
app/build/outputs/apk/release/app-release.apk
```

> `key/` 目录已被 `.gitignore` 忽略，请不要把签名文件和密码提交到公开仓库。

---

## 发布流程

以 `7.8.3` 为例：

1. 修改 [app/build.gradle.kts](app/build.gradle.kts) 中的版本号。

```kotlin
versionCode = 783
versionName = "7.8.3"
```

2. 构建 Release APK。

```powershell
.\gradlew.bat clean assembleRelease
```

3. 复制 APK 到发布站点结构。

```text
release/download/v7.8.3/qianzhihe_7.8.3_release.apk
```

4. 更新 `release/update.json`。

5. 提交并推送 `qianzhihe-site`。

6. 创建 GitHub Release，并上传 APK：

```powershell
gh release create v7.8.3 release/download/v7.8.3/qianzhihe_7.8.3_release.apk `
  --repo wstar31/qianzhihe-site `
  --target main `
  --title "v7.8.3" `
  --notes "发布 v7.8.3 APK" `
  --latest
```

---

## 权限说明

| 权限 | 用途 |
|------|------|
| `INTERNET` | 打开网页、检查更新、下载 APK |
| `REQUEST_INSTALL_PACKAGES` | 引导用户安装下载的新版本 APK |

应用还使用 `FileProvider` 向系统安装器临时授予 APK 文件读取权限。

---

## 隐私说明

千址盒采用本地优先设计：

- 不提供注册登录。
- 收藏数据主要保存在设备本地 Room 数据库。
- 导入导出文件由用户主动选择和保存。
- 应用内浏览器只打开用户主动输入或收藏的网址。
- 检查更新时会访问 `qzh.336954.xyz` 获取版本清单。
- favicon 或网页加载可能会向目标网站或第三方图标服务发起请求。

完整说明请查看：

- [隐私政策](https://qzh.336954.xyz/privacy.html)
- [用户协议](https://qzh.336954.xyz/agreement.html)

---

## 已知问题

- 如果用户设备上已安装同包名但不同签名的旧版 APK，系统会提示签名冲突，无法直接覆盖安装。请先导出数据，再卸载旧版后安装新版。
- 某些网站可能限制 WebView、桌面 UA 或 HTTP 访问，应用会尽量提示并回退，但无法保证所有网页都能正常打开。
- 明文 HTTP 回退仅用于兼容不支持 HTTPS 的站点，优先推荐使用 HTTPS。

---

## Roadmap

- [ ] 补充应用截图和演示动图
- [ ] 增加更多导入源兼容性
- [ ] 增加数据备份恢复向导
- [ ] 优化平板和大屏布局
- [ ] 完善浏览器错误页与网络诊断提示
- [ ] 增加更多自动化测试

---

## 贡献

目前项目主要面向个人维护。欢迎通过 Issue 或 Pull Request 提交：

- Bug 复现步骤
- UI/交互建议
- 导入导出兼容性问题
- 浏览器适配问题
- 文档改进

提交代码前建议先运行：

```powershell
.\gradlew.bat :app:compileDebugKotlin :app:compileDebugJavaWithJavac
```

---

## 免责声明

本项目用于个人网址收藏和本地管理。用户应自行确认所访问网页、导入文件和下载 APK 的来源安全性。

开发者不对用户主动访问的第三方网页内容、第三方站点可用性、用户自行导入的数据内容或非官方渠道 APK 导致的问题承担责任。

---

## License

当前仓库暂未显式声明开源许可证。如需公开协作或二次分发，请先补充 LICENSE 文件并明确授权范围。

---

<div align="center">

**如果这个项目对你有帮助，欢迎 Star。**

</div>
