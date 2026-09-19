<div align="center">

<img src="fastlane/metadata/android/en-US/images/icon.png" alt="VibeTube Icon" width="120">

# VibeTube

### A modern, private, and feature-rich video client for Android

**Watch · Listen · Download · Explore**

<p>
  <img src="https://img.shields.io/badge/Android-API%2024%2B-3DDC84?style=flat-square&logo=android&logoColor=white" alt="Android API 24+">
  <img src="https://img.shields.io/badge/Kotlin-100%25-B125EA?style=flat-square&logo=kotlin&logoColor=white" alt="Kotlin">
  <img src="https://img.shields.io/badge/Jetpack%20Compose-Material%203-4285F4?style=flat-square&logo=jetpackcompose&logoColor=white" alt="Jetpack Compose">
  <img src="https://img.shields.io/badge/License-GPL--3.0-blue?style=flat-square" alt="GPL-3.0">
</p>

**VibeTube** is an independently developed Android video client based on the PlayTube open-source project, with significant UI, playback, Shorts, download, storage, and performance improvements.

</div>

---

## ✨ Features

### 🎬 Video Experience

- **Modern VibeTube UI** — Clean, premium light and dark themes.
- **Video Playback** — AndroidX Media3 / ExoPlayer.
- **Background Playback** — Continue listening outside the app.
- **Picture-in-Picture** — Watch videos while using other apps.
- **Fullscreen Player** — Dedicated fullscreen playback experience.
- **Playback Controls** — Quality, speed, captions, seeking, and player settings.
- **Watch History** — Resume previously watched content.
- **Subscriptions & Saved Content** — Manage content locally.

### 📱 Shorts

- Dedicated vertical Shorts feed.
- Continuous pagination and preloading.
- Session-based duplicate protection.
- Long-press 2× playback.
- Watch Full support.
- Background playback.
- Download support.
- Smooth swipe-based playback.

### 🔎 Search & Discovery

- Search videos, Shorts, and channels.
- All / Shorts / Videos / Channels filters.
- Related video and Shorts recommendations.
- Cached thumbnails and metadata.
- Independent feed state and pagination.

### ⬇️ Downloads

- Dynamic source-supported quality selection.
- High-quality video downloads.
- Device video downloads.
- Device audio downloads as **real MP3 files**.
- VibeTube internal video downloads.
- Real audio conversion instead of extension renaming.
- MP3 title, artist, duration, and album artwork.
- Download progress, processing, success, and failure notifications.
- File validation before completion.

### 🎧 Audio

- MediaSession system controls.
- Background audio playback.
- Audio-only playback.
- Resume playback position.
- Dynamic audio stream selection.
- MP3 metadata and artwork.

### 🎨 UI

- Material 3.
- Light / Dark themes.
- Premium Watch Page.
- Compact search results.
- Modern Download Sheet.
- Five-tab navigation:
  **Home · Shorts · Subscriptions · Notifications · You**
- Configurable animations and player behavior.

### ⚙️ Settings

Playback · Shorts · Downloads · Appearance · Search · Notifications · Privacy/Data · Player Controls · Storage · Advanced · About

---

## 📸 Screenshots

<div align="center">

<img src="fastlane/metadata/android/en-US/images/phoneScreenshots/homescreen.png" width="18%" alt="VibeTube Home">
&nbsp;
<img src="fastlane/metadata/android/en-US/images/phoneScreenshots/shorts.png" width="18%" alt="VibeTube Shorts">
&nbsp;
<img src="fastlane/metadata/android/en-US/images/phoneScreenshots/watch.png" width="18%" alt="VibeTube Watch">
&nbsp;
<img src="fastlane/metadata/android/en-US/images/phoneScreenshots/downloads.png" width="18%" alt="VibeTube Downloads">
&nbsp;
<img src="fastlane/metadata/android/en-US/images/phoneScreenshots/you.png" width="18%" alt="VibeTube You">

</div>

> Update screenshot filenames above if your repository uses different paths.

---

## 🧩 Technology Stack

| Category | Technology | Purpose |
|---|---|---|
| Language | Kotlin | Android development |
| UI | Jetpack Compose | Declarative UI |
| Design | Material 3 | Components and theming |
| Architecture | MVVM / Clean Architecture | Application structure |
| DI | Hilt | Dependency injection |
| Reactive | Coroutines / StateFlow | Async and reactive state |
| Database | Room | Local data |
| Preferences | DataStore | Settings |
| Playback | AndroidX Media3 / ExoPlayer | Video and audio |
| Extraction | NewPipeExtractor | Stream and metadata extraction |
| Images | Coil | Thumbnail/artwork loading |
| Networking | OkHttp | Network requests |
| Downloads | WorkManager / Download services | Background downloads |
| Audio conversion | FFmpegKit / FFmpeg | Real MP3 encoding |
| Build | Gradle / KSP / Version Catalog | Build system |

---

## 🏗️ Architecture

```text
Jetpack Compose UI
        │
        ▼
ViewModel / StateFlow
        │
        ▼
Domain / Use Cases
        │
        ▼
Repositories
   ┌────┴─────┐
   ▼          ▼
 Room      NewPipeExtractor
DataStore     OkHttp
   │          │
   └────┬─────┘
        ▼
 Media / Download Layer
        │
 Media3 / WorkManager
        │
        ▼
 Device / VibeTube Storage
```

---

## 📥 Download Storage

```text
VibeTube/
└── download/
    ├── VibeTube Video/
    └── VibeTube Audio/
```

Device storage location may vary on modern Android versions because of Scoped Storage and MediaStore rules.

### Device Audio

Audio downloads are exported as valid MP3 files with metadata and, when available, embedded artwork.

### VibeTube Storage

VibeTube internal storage is intended for supported video downloads. Audio selection is not offered for VibeTube internal storage.

---

## 🔐 Privacy

VibeTube follows a local-first approach.

- No mandatory Google account for core usage.
- Local preferences remain on the device.
- Download state is stored locally.
- No VibeTube-owned advertising system.
- No VibeTube-owned analytics service is required for core functionality.

Network requests may still be required to retrieve video, stream, thumbnail, and metadata content.

---

## 🧪 Testing

Before publishing a release, test:

- Fresh installation and update
- Home and Search
- Shorts
- Watch Page
- Fullscreen playback
- Background playback
- Picture-in-Picture
- Video downloads
- Audio / MP3 downloads
- Download notifications
- Gallery and music-player playback
- Light and dark themes
- Android 10+ storage behavior
- App restart during downloads
- Failed and cancelled downloads
- Different Android versions and screen sizes

---

## 🙏 Acknowledgements

VibeTube builds upon open-source work from the Android community.

Special thanks to:

- [PlayTube](https://github.com/arslandaim-hub/PlayTube)
- [NewPipe](https://github.com/TeamNewPipe/NewPipe)
- [NewPipeExtractor](https://github.com/TeamNewPipe/NewPipeExtractor)
- LibreTube
- PipePipe
- Flow
- AndroidX / Jetpack
- Media3 / ExoPlayer
- Coil
- FFmpeg / FFmpegKit
- Kotlin and Android communities

VibeTube contains significant modifications to the original PlayTube project, including branding, UI/UX, playback, Shorts, downloads, audio conversion, notifications, storage handling, and performance improvements.

---

## ⚖️ License & Open-Source Notice

VibeTube is a modified/derivative project based on **PlayTube**, which is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.

Applicable GPL-covered code remains subject to GPL-3.0.

When redistributing VibeTube or modified versions:

- Preserve applicable copyright and license notices.
- Keep GPL-covered code under GPL-3.0.
- Provide corresponding source code as required by the license.
- Clearly document significant modifications.
- Include the complete GPL-3.0 license.

See [`LICENSE`](LICENSE) for the complete license text.

### Upstream Project

**PlayTube:** https://github.com/arslandaim-hub/PlayTube

---

## 👨‍💻 Developer

<div align="center">

### Rahul Haldar

**VibeTube Developer & Maintainer**

</div>

---

## ⚠️ Important Notice

VibeTube is an independent open-source project.

- VibeTube is not affiliated with, endorsed by, or sponsored by Google or YouTube.
- YouTube and related trademarks belong to their respective owners.
- Content availability and stream formats depend on the underlying source and may change.
- Users are responsible for complying with applicable laws, copyright requirements, and service terms.
- Review applicable platform policies before distributing the application through third-party app stores.

---

## ⭐ Support the Project

If VibeTube is useful to you:

- ⭐ Star the repository
- 🐛 Report reproducible bugs
- 💡 Suggest improvements
- 🔧 Contribute code
- 📖 Improve documentation

---

<div align="center">

**VibeTube**

*Watch. Listen. Explore.*

**Developed by Rahul Haldar**

</div>
