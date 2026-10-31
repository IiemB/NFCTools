# NFCTools for iOS 📱⚡

<p align="center">
  <b>Comprehensive contactless NFC diagnostic suite, virtual tag emulation, and Control Center companion for iOS.</b>
</p>

<p align="center">
  <b>English</b> | <a href="README.id.md">Bahasa Indonesia</a>
</p>



---

> [!NOTE]
> Some releases are **beta builds**, used to try out new features and gather feedback. They are marked *beta* on the
> Releases page, in the file name, and in the app. A beta build of the app and the tweak **works for 14 days after it
> was built**. After that, the app shows an update screen and the tweak and CLI stop emulating. Download the newest
> build from **[Releases](https://github.com/IiemB/NFCTools/releases/latest)** to keep going. Regular builds don't expire.

---

## 🌟 Overview

**NFCTools** is a versatile NFC diagnostic, virtual tag emulation, and card management toolkit designed specifically for iOS. It combines a feature-rich, standalone SwiftUI application with an optional jailbreak companion tweak to deliver low-level tag reading, advanced card diagnostics, flexible tag organization, virtual tag emulation, and instant system integrations.

---

## 📥 Download

Get the latest build from the **[Releases page](https://github.com/IiemB/NFCTools/releases/latest)**. Beta builds have `beta` in the file name (`NFCTools_<version>-beta+<build>.ipa`, `NFCTools_Plus_<version>~beta+<build>_…deb`).


---

## 📱 NFCTools App (Main Application)

The core app is packaged as a standalone `.ipa` (installed via TrollStore) providing low-level hardware access, deep tag analysis, and in-app virtual tag emulation.

### 📡 Tag Diagnostics & Scanning
- **Universal Technology Detection**: Inspect ISO 14443 Type A, ISO 14443 Type B, ISO 15693 (Vicinity), FeliCa, and MIFARE cards.
- **Deep Hardware Inspection**: View UID / PUPI (4, 7, 8, 10, and 12-byte lengths), ATQA, SAK, memory layout, manufacturer information, and protocol parameters. Long-press any property to copy its value.
- **NDEF Reading & Payload Decoding**: Automatically parse NDEF text, URIs/URLs, and raw payload records.
- **NDEF Writability Check**: Detects physical tag lock states and write-readiness directly upon scanning.

### ⚡ Virtual Tag Emulation
- **Broadcast Saved Virtual Tags**: Emulate saved NFC tags directly from your iPhone as contactless virtual cards.
- **Custom Identifier Transmission**: Broadcast custom UIDs and protocol parameters to external readers and smartphones.
- **Interactive Reader Feedback**: Real-time tactile haptic feedback triggers the instant an external NFC reader makes RF contact with your virtual tag.
- **Type 4 NDEF Virtual Applet**: Responds to standard SELECT and READ BINARY APDUs for seamless NDEF payload reading by third-party devices.
- **Emulate with NFCTools Plus**: With the tweak installed, the app can hand emulation to it, so you get the tweak's small floating pill with a Stop button instead of the full-screen emulation screen.

### 🗃️ Tag Library & Organization
- **Local Tag Vault**: Store your scanned tags with custom nicknames, over 50+ custom SF Symbol glyphs, and selectable color accents.
- **Record Editor**: Create and edit NDEF Text (multi-line) and URL records.
- **Drag-and-Drop Reordering**: Organize your saved tag library with custom order persistence.
- **Portable Backup (`.nftag`)**: Export and import individual tag files with safety verification sheets to share or restore your tag library.

### 🏷️ Magic Tag Cloning & UID Writing
- **Magic Tag Support**: Direct transceive support to write and clone custom UIDs to physical writable cards.
- **Supported Protocols**: Gen3 APDU, Magic Type 2 (NTAG21x / MIFARE Ultralight with automatic BCC checksum calculation and manufacturer byte preservation), and Gen4 UMC tags.

### 🩺 Diagnostics & Reports
- **Diagnostics Page**: Plain-language checks for iOS version, iPhone model, installation, tag reading, emulation, NFC chip, NFC service, storage, saved tags, and NFCTools Plus. Shown on first launch and any time from **Settings › Diagnostics**.
- **Send Report to Developer**: From Settings › Diagnostics, send the results, your iPhone model and iOS version, an optional note, and the app log straight to the developer. The log is encrypted on your iPhone so only the developer can read it. You get a report ID to quote if you follow up on GitHub.

### 🎨 Native User Experience
- **100% Native SwiftUI**: Modern layout with fluid transitions, dark and light theme support, and custom radar animations.
- **Home Screen & Lock Screen Widgets**: An 8-slot Home Screen widget and four circular Lock Screen widgets (iOS 16+) for one-tap emulation. Settings shows live previews that match the real widgets.

---

## ⚙️ NFCTools Plus (Jailbreak Companion)

The tweak ships as a standalone `.deb` package designed for rootless and RootHide jailbreaks (Dopamine, RootHide), bringing quick-access virtual tag emulation directly into iOS system surfaces.

### 🎛️ Control Center Quick Emulation
- **Dedicated Quick Tiles**: Four Control Center tiles ("NFC Tag 1–4") start emulating their assigned tag from anywhere on your device, even with the screen locked (with auto-stop on).
- **Tile Setup in the App**: Assign a saved tag to each tile in **NFCTools › Settings**, where a preview shows the tiles as they appear in Control Center. Then add the tiles in **iOS Settings › Control Center**.
- **Visual Floating HUD**: An on-screen status overlay showing the active virtual tag name, UID, radiating transmission wave, and a quick-stop action.
- **Auto-Stop**: Emulation always stops on its own after 5–30 seconds (default 10).

### 💻 Command-Line Interface (`nfctools`)
A privileged command-line tool accessible via Terminal or SSH:
```sh
nfctools emulate <tile 1-4 | uuid | uid | name>   # Start emulating a tag (no tile needed)
nfctools stop                                     # Stop the active emulation
nfctools list [-v]                                # List saved tags and tile assignments
nfctools assign <tile 1-4> <name|uid|uuid|none>   # Assign a tag to a Control Center tile
nfctools autostop [5-30]                          # Get or set the auto-stop countdown (default 10)
nfctools config                                   # Show tile and auto-stop settings
nfctools status                                   # Show the current emulation state
nfctools help                                     # Show help (and, on beta builds, the end date)
```

---

## 📲 Compatibility & Installation

### Requirements
- An iPhone whose NFC controller supports direct access (e.g. iPhone 12 / 13). Main test device: **iPhone 12 mini, iOS 16.1.2**.
- The Diagnostics page tells you whether your iPhone and install can use each feature.

### Main App (`.ipa`)
- **Compatibility**: iOS 15.0 and later (iOS 18 and later is untested)
- **Installation**: Install `NFCTools_<version>+<build>.ipa` via **TrollStore**.

### Tweak (`.deb`)
- **Compatibility**: iOS 15.0 – 16.5.1+ (Rootless / RootHide)
- **Installation**: Install the matching `.deb` via Sileo, Zebra, or `dpkg -i`, then respring:
  - **Dopamine (Rootless)**: `NFCTools_Plus_<version>+<build>_iphoneos-arm64.deb`
  - **RootHide**: `NFCTools_Plus_<version>+<build>_iphoneos-arm64e.deb`
- The tweak emulates the tags you save in the app, so install the app too.

---

## 💬 Feedback & Reports

Feedback and reports help a lot, so thank you.

1. **Something broken?** Open **Settings › Diagnostics** in the app, tap **Send Report to Developer**, describe what happened in the note, and send it. Keep the report ID it shows you.
2. **Want to discuss it, or suggest a feature?** [Open an issue](https://github.com/IiemB/NFCTools/issues) and include the report ID if you sent one.
3. **Beta build ended?** Download the newest build from [Releases](https://github.com/IiemB/NFCTools/releases/latest).

---

## 📄 Terms & Privacy

The Terms of Use and Privacy Policy are in the app under **Settings › Terms & Privacy**, and the source text is in [`content/legal.json`](content/legal.json). In short, the app has no accounts, ads, or analytics, and sends nothing to the developer unless you choose to send a report.

---

## ⚖️ Disclaimer

- **Authorized Use**: NFCTools is developed for personal, educational, and diagnostic use on tags and hardware you own. Always ensure you have proper authorization before inspecting, writing, or emulating any contactless card.
- **AI-Assisted Project**: This project originally started as a personal, private utility built to fit my own needs and workflow where existing tools fell short. It is shared as-is for anyone who finds it useful—feedback and bug reports are always welcome!
