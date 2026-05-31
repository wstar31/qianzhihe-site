# QianZhiHe

<div align="center">

![Android](https://img.shields.io/badge/Android-8.0%2B-3DDC84.svg)
![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF.svg)
![Java](https://img.shields.io/badge/Java-17-ED8B00.svg)
![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-2026.02.01-4285F4.svg)
![Room](https://img.shields.io/badge/Room-2.8.4-1976D2.svg)
![Version](https://img.shields.io/badge/version-7.8.3-blue.svg)

**A local-first bookmark manager, category organizer, and in-app browser for Android**

[中文](README_CN.md) · [English](README.md) · [日本語](README_JA.md)

[Website](https://qzh.336954.xyz/) · [Privacy Policy](https://qzh.336954.xyz/privacy.html) · [User Agreement](https://qzh.336954.xyz/agreement.html) · [Latest Download](https://github.com/wstar31/qianzhihe-site/releases/latest)

</div>

> QianZhiHe is an Android bookmark management app for personal use. It focuses on saving links, organizing categories, searching, importing/exporting data, and browsing pages inside the app. Data is mainly stored locally on the user's device. The app does not provide account registration/login and does not actively upload bookmark data to the developer's server.

---

## Current Version

| Item | Value |
|------|-------|
| App name | QianZhiHe / 千址盒 |
| Package name | `com.star.qianzhihe` |
| Current version | `7.8.3` |
| versionCode | `783` |
| Minimum Android version | Android 8.0 / API 26 |
| Target SDK | API 36 |
| Official domain | `qzh.336954.xyz` |

## Download

The latest APK is available from GitHub Releases:

- [GitHub Releases](https://github.com/wstar31/qianzhihe-site/releases/latest)
- [v7.8.3 APK](https://github.com/wstar31/qianzhihe-site/releases/download/v7.8.3/qianzhihe_7.8.3_release.apk)
- [Update manifest: update.json](https://qzh.336954.xyz/release/update.json)

> If Android reports that an app with a conflicting signature is already installed, your device already has an APK with the same package name but a different signing certificate. Export your data from the old version first, uninstall the old version, and then install the new APK.

---

## Overview

QianZhiHe helps users manage frequently used URLs locally. Users can add a URL, set a title, assign a category, add tags and notes, and quickly find saved links through search, category filters, pinned items, and visit statistics.

The app also includes a WebView-based in-app browser. It can open saved links or user-entered URLs and provides browser actions such as page search, copy link, share link, favorite the current page, switch between desktop/mobile mode, and manage multiple open pages.

## Features

- **Local bookmark storage**: Save URLs, titles, categories, tags, notes, pinned state, and visit statistics.
- **Category management**: Organize bookmarks by category and manage category rename/merge/delete operations.
- **Search and filters**: Search by title, URL, tags, notes, and category.
- **Sorting and pinning**: Default ordering prioritizes pinned items, recent visits, and recent updates.
- **Import and export**: Supports Markdown, JSON, and browser bookmark HTML formats for backup and migration.
- **In-app browser**: Opens web pages with WebView and supports multiple pages, back/forward, refresh, home, copy, share, and favorite actions.
- **Desktop/mobile browsing mode**: Supports desktop user-agent mode and mobile mode, including scaling adjustments for tablets and landscape orientation.
- **HTTPS-first loading**: URLs without a scheme are completed as HTTPS by default, with HTTP fallback when necessary.
- **Dynamic island toolbar**: The home page and browser provide a floating top toolbar with docking, swipe-to-hide, and auto-hide behavior.
- **Dark/light theme**: Supports dark and light appearance modes.
- **Immersive/safe display mode**: Switches system bar behavior for either immersive display or safer visible system bars.
- **Update checking**: Can read the site `update.json`, download a new APK, validate it, and guide the user through installation.

## Screenshots

### Home and Bookmark List

The home page is used to add, search, filter, and open saved links. The floating toolbar provides quick access to settings, theme switching, and immersive/safe display controls.

<p align="center">
  <img src="assets/screenshots/home.jpg" alt="QianZhiHe home page and bookmark list" width="320">
</p>

### Settings

The settings drawer is shown as a continuous set of screenshots, covering display options, browser behavior, update checking, reset actions, and help/about entries.

<p align="center">
  <img src="assets/screenshots/settings-display-first.jpg" alt="QianZhiHe settings display options" width="320">
  <img src="assets/screenshots/settings-overview-second.jpg" alt="QianZhiHe settings browser and update options" width="320">
  <img src="assets/screenshots/settings-overview-third.jpg" alt="QianZhiHe settings reset and help options" width="320">
</p>

### URL Management

The management drawer supports quick add, direct open, import/export, clearing data, and category management.

<p align="center">
  <img src="assets/screenshots/management.jpg" alt="URL management and category management" width="320">
</p>

### In-app Browser

The built-in browser supports desktop/mobile mode, in-page search, back/forward navigation, refresh, home, copy, share, favorite, and multi-page management.

<p align="center">
  <img src="assets/screenshots/browser.jpg" alt="In-app browser and web toolbar" width="320">
</p>

---

## Tech Stack

| Area | Technology |
|------|------------|
| Platform | Android |
| Languages | Kotlin + Java |
| UI | Jetpack Compose + XML View |
| Architecture | MVVM / ViewModel / Flow |
| Database | Room |
| Browser | Android WebView / AndroidX WebKit |
| Image loading | Coil Compose |
| Build system | Gradle Kotlin DSL / Android Gradle Plugin |
| Minimum JDK | Java 17 |

---

## Project Structure

```text
QZH/
├── app/                                      # Android application module
│   ├── build.gradle.kts                     # App build config, version, signing config
│   └── src/
│       ├── main/
│       │   ├── AndroidManifest.xml          # Permissions, activities, FileProvider
│       │   ├── java/com/star/qianzhihe/
│       │   │   ├── MainActivity.kt          # App entry and Compose home screen host
│       │   │   ├── BrowserActivity.java     # In-app browser
│       │   │   ├── AppPrefs.kt              # Local preferences
│       │   │   ├── UpdateManager.kt         # Update check, APK download and install flow
│       │   │   ├── data/                    # Room database, DAO, entities
│       │   │   ├── ui/main/                 # Home UI, drawers, cards, import/export, toolbar
│       │   │   └── ui/theme/                # Theme, colors, fonts
│       │   └── res/                         # XML layouts, icons, resources
│       └── test/                            # Unit tests
├── assets/                                  # README assets and screenshots
│   └── screenshots/
├── release/                                 # Local release manifest and APK folders
│   ├── update.json
│   └── download/
├── gradle/                                  # Gradle version catalog
├── key/                                     # Local signing key folder, not committed
└── README.md
```

---

## Data Model

The core Room table is `site_table`, represented by the `SiteItem` entity.

| Field | Description |
|-------|-------------|
| `title` | Bookmark title |
| `url` | Original URL |
| `normalizedUrl` | Normalized URL for deduplication and matching |
| `category` | Category, defaulting to “Uncategorized” in the UI concept |
| `tags` | Tag text |
| `note` | Note text |
| `isPinned` | Whether the bookmark is pinned |
| `visitCount` | Number of visits |
| `lastVisitedAt` | Last visited timestamp |
| `openMethod` | Open method: auto, in-app, or external browser |
| `updatedAt` | Last updated timestamp |

---

## Import and Export Formats

### Markdown

Markdown import supports both standard Markdown links and plain URLs:

```markdown
- [GitHub](https://github.com/)
- https://example.com
```

Markdown export includes category, tags, and notes:

```markdown
- [GitHub](https://github.com/)
  - Category: Development
  - Tags: code, open source
  - Note: Common code hosting platform
```

> The current app export labels may follow the app's built-in Chinese UI text until full multilingual support is implemented.

### JSON

JSON import supports either a root array or an `{ "items": [...] }` object. Example export shape:

```json
{
  "version": 2,
  "items": [
    {
      "title": "GitHub",
      "url": "https://github.com/",
      "category": "Development",
      "tags": "code,open-source",
      "note": "Common code hosting platform",
      "isPinned": false,
      "visitCount": 0,
      "lastVisitedAt": 0,
      "openMethod": "AUTO"
    }
  ]
}
```

### Browser Bookmark HTML

The app can parse Netscape Bookmark HTML files:

```html
<!DOCTYPE NETSCAPE-Bookmark-file-1>
<DL><p>
  <DT><H3>Development</H3>
  <DL><p>
    <DT><A HREF="https://github.com/">GitHub</A>
  </DL><p>
</DL><p>
```

---

## Update Mechanism

The app checks for new versions through the release manifest:

```text
https://qzh.336954.xyz/release/update.json
```

Example manifest:

```json
{
  "versionName": "7.8.3",
  "versionCode": 783,
  "apkName": "qianzhihe_7.8.3_release.apk",
  "downloadUrl": "https://qzh.336954.xyz/release/download/v7.8.3/qianzhihe_7.8.3_release.apk",
  "releaseNotes": "Update notes...",
  "releasePageUrl": "https://qzh.336954.xyz/release/download/v7.8.3/"
}
```

Update flow:

1. Read the currently installed version.
2. Fetch `update.json`.
3. Compare `versionCode`.
4. Download the APK.
5. Validate file type, package name, and version metadata.
6. Use `FileProvider` to start the Android package installer.

> Android 8.0 and later require the user to grant the “install unknown apps” permission before installing downloaded APK files.

---

## Build and Run

### Requirements

- Android Studio / Android SDK
- JDK 17
- Gradle Wrapper
- Android SDK Platform 36
- Android Build Tools

### Clone

```bash
git clone https://github.com/<owner>/<repo>.git
cd QZH
```

### Debug Build

Windows:

```powershell
.\gradlew.bat :app:assembleDebug
```

Linux / macOS:

```bash
./gradlew :app:assembleDebug
```

### Release Build

The project can read `key/key.properties` for release signing:

```properties
storeFile=key/qianzhihe-release.jks
storePassword=your_store_password
keyAlias=qianzhihe
keyPassword=your_key_password
```

Build the release APK:

```powershell
.\gradlew.bat clean assembleRelease
```

Output path:

```text
app/build/outputs/apk/release/app-release.apk
```

> The `key/` directory is ignored by `.gitignore`. Do not commit signing keys or passwords to a public repository.

---

## Release Workflow

Example for `7.8.3`:

1. Update the version in [app/build.gradle.kts](app/build.gradle.kts).

```kotlin
versionCode = 783
versionName = "7.8.3"
```

2. Build the release APK.

```powershell
.\gradlew.bat clean assembleRelease
```

3. Copy the APK to the release-site structure.

```text
release/download/v7.8.3/qianzhihe_7.8.3_release.apk
```

4. Update `release/update.json`.

5. Commit and push the `qianzhihe-site` repository.

6. Create a GitHub Release and upload the APK asset:

```powershell
gh release create v7.8.3 release/download/v7.8.3/qianzhihe_7.8.3_release.apk `
  --repo wstar31/qianzhihe-site `
  --target main `
  --title "v7.8.3" `
  --notes "Publish v7.8.3 APK" `
  --latest
```

---

## Permissions

| Permission | Purpose |
|------------|---------|
| `INTERNET` | Open web pages, check for updates, and download APK files |
| `REQUEST_INSTALL_PACKAGES` | Guide the user to install a downloaded APK update |

The app also uses `FileProvider` to temporarily grant the Android package installer read access to the downloaded APK file.

---

## Privacy

QianZhiHe is designed as a local-first app:

- No account registration or login is provided.
- Bookmark data is mainly stored in the local Room database on the user's device.
- Import/export files are selected and saved by the user.
- The in-app browser only opens URLs entered or saved by the user.
- Update checking accesses `qzh.336954.xyz` to fetch the release manifest.
- Favicon loading and page browsing may send requests to target websites or third-party icon services.

For the full text, see:

- [Privacy Policy](https://qzh.336954.xyz/privacy.html)
- [User Agreement](https://qzh.336954.xyz/agreement.html)

---

## Known Issues

- If a device already has an APK with the same package name but a different signature, Android will block direct installation. Export your data first, uninstall the old version, and then install the new APK.
- Some websites may restrict WebView, desktop user-agent, or HTTP access. The app will try to show a helpful prompt and fallback when possible, but it cannot guarantee that every website will load correctly.
- HTTP fallback is provided only for compatibility with websites that do not support HTTPS. HTTPS is preferred whenever possible.

---

## Roadmap

- [ ] Add more screenshots and demo animations
- [ ] Improve compatibility with more import sources
- [ ] Add a guided backup/restore flow
- [ ] Optimize tablet and large-screen layouts
- [ ] Improve browser error pages and network diagnostics
- [ ] Add more automated tests
- [ ] Add full in-app multilingual support after the UI text stabilizes

---

## Contributing

This project is currently maintained primarily as a personal project. Issues and pull requests are welcome for:

- Bug reproduction steps
- UI/interaction suggestions
- Import/export compatibility issues
- Browser compatibility issues
- Documentation improvements

Before submitting code, it is recommended to run:

```powershell
.\gradlew.bat :app:compileDebugKotlin :app:compileDebugJavaWithJavac
```

---

## Disclaimer

This project is intended for personal bookmark management and local organization. Users should verify the safety of third-party websites, imported files, and APKs downloaded from non-official channels.

The developer is not responsible for third-party web page content, third-party website availability, user-imported data, or issues caused by APKs distributed outside official release channels.

---

## License

This repository does not currently declare an explicit open-source license. If public collaboration or redistribution is required, add a `LICENSE` file and define the permitted usage scope first.

---

<div align="center">

**If this project is useful to you, a star is appreciated.**

</div>
