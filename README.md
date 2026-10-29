# NFCTools for iOS 📱⚡

<p align="center">
  <b>Comprehensive contactless NFC diagnostic suite, virtual tag emulation, and Control Center companion for iOS.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-iOS%2015.0%2B-000000?style=for-the-badge&logo=apple&logoColor=white" alt="iOS 15.0+" />
  <img src="https://img.shields.io/badge/SwiftUI-Native-F05138?style=for-the-badge&logo=swift&logoColor=white" alt="SwiftUI" />
  <img src="https://img.shields.io/badge/TrollStore-App%20(.ipa)-34C759?style=for-the-badge" alt="TrollStore" />
  <img src="https://img.shields.io/badge/Jailbreak-Tweak%20(.deb)-5856D6?style=for-the-badge" alt="Jailbreak" />
</p>

---

## 🌟 Overview

**NFCTools** is a versatile NFC diagnostic, virtual tag emulation, and card management toolkit designed specifically for iOS. It combines a feature-rich, standalone SwiftUI application with an optional jailbreak companion tweak to deliver low-level tag reading, advanced card diagnostics, flexible tag organization, virtual tag emulation, and instant system integrations.

---

## 📱 NFCTools App (Main Application)

The core app is packaged as a standalone `.ipa` (installed via TrollStore) providing low-level hardware access, deep tag analysis, and in-app virtual tag emulation.

### 📡 Tag Diagnostics & Scanning
- **Universal Technology Detection**: Inspect ISO 14443 Type A, ISO 14443 Type B, ISO 15693 (Vicinity), FeliCa, and MIFARE cards.
- **Deep Hardware Inspection**: View UID / PUPI (4, 7, 8, 10, and 12-byte lengths), ATQA, SAK, memory layout, manufacturer information, and protocol parameters.
- **NDEF Reading & Payload Decoding**: Automatically parse NDEF text, URIs/URLs, and raw payload records.
- **NDEF Writability Check**: Detects physical tag lock states and write-readiness directly upon scanning.

### ⚡ Virtual Tag Emulation
- **Broadcast Saved Virtual Tags**: Emulate saved NFC tags directly from your iPhone as contactless virtual cards.
- **Custom Identifier Transmission**: Broadcast custom UIDs and protocol parameters to external readers and smartphones.
- **Interactive Reader Feedback**: Real-time tactile haptic feedback triggers the instant an external NFC reader makes RF contact with your virtual tag.
- **Type 4 NDEF Virtual Applet**: Responds to standard SELECT and READ BINARY APDUs for seamless NDEF payload reading by third-party devices.

### 🗃️ Tag Library & Organization
- **Local Tag Vault**: Store your scanned tags with custom nicknames, over 50+ custom SF Symbol glyphs, and selectable color accents.
- **Raw JSON Inspector**: View and copy full, pretty-printed, syntax-colored JSON dumps of any saved tag.
- **Drag-and-Drop Reordering**: Organize your saved tag library with custom order persistence.
- **Portable Backup (`.nftag`)**: Export and import individual tag files with safety verification sheets to share or restore your tag library.

### 🏷️ Magic Tag Cloning & UID Writing
- **Magic Tag Support**: Direct transceive support to write and clone custom UIDs to physical writable cards.
- **Supported Protocols**: Gen3 APDU, Magic Type 2 (NTAG21x / MIFARE Ultralight with automatic BCC checksum calculation and manufacturer byte preservation), and Gen4 UMC tags.

### 🎨 Native User Experience
- **100% Native SwiftUI**: Modern layout with fluid transitions, dark and light theme support, and custom radar animations.
- **Lock Screen & Home Screen Widgets**: Access saved tag shortcuts and monitor active status directly from your Home Screen or Lock Screen.
- **Multilingual Support**: Complete native localization for English and Indonesian.

---

## ⚙️ NFCTools Plus (Jailbreak Companion)

The tweak ships as a standalone `.deb` package designed for rootless and RootHide jailbreaks (Dopamine, RootHide), bringing quick-access virtual tag emulation directly into iOS system surfaces.

### 🎛️ Control Center Quick Emulation
- **Dedicated Quick Tiles**: Four customizable Control Center toggle tiles ("Tile 1" through "Tile 4") to start emulating any assigned virtual tag from anywhere on your device—even with the screen locked.
- **Visual Floating HUD**: An on-screen status overlay showing the active virtual tag name, UID, radiating transmission wave, and a quick-stop action.
- **Configurable Auto-Stop**: Optional timer to automatically stop virtual tag emulation after a configurable countdown.

### 🔧 System Settings Integration
- **Preference Bundle (`Settings > NFC Tools`)**: Directly configure and assign saved virtual tags from your app library to each Control Center tile.
- **Automatic Fallback Mapping**: Tiles automatically map to your library order if unassigned, or can be assigned custom tags.

### 💻 Command-Line Interface (`nfctools`)
A privileged command-line tool accessible via Terminal or SSH:
```sh
nfctools emulate 1         # Start emulating virtual tag assigned to Tile 1
nfctools emulate <name>    # Emulate virtual tag by nickname, UID, or UUID
nfctools list              # List all saved virtual tags and tile assignments
nfctools assign <tile>     # Assign a virtual tag to a Control Center tile
nfctools stop              # Halt active virtual tag emulation
nfctools status            # View current virtual tag emulation state
nfctools help              # Display command help and usage examples
```

---

## 📲 Compatibility & Installation

### Main App (`.ipa`)
- **Compatibility**: iOS 15.0 – 17.0
- **Installation**: Install `NFCTools_<version>.ipa` via **TrollStore**.

### Tweak (`.deb`)
- **Compatibility**: iOS 15.0 – 16.5.1+ (Rootless / RootHide)
- **Installation**: Install the appropriate `.deb` package via Sileo, Zebra, or `dpkg -i`, then respring:
  - **Dopamine (Rootless)**: `NFCTools_Plus_<version>_iphoneos-arm64.deb`
  - **RootHide**: `NFCTools_Plus_<version>_iphoneos-arm64e.deb`

---

## ⚖️ Disclaimer

*NFCTools is developed for educational, diagnostic, and authorized security research purposes on tags and hardware you own. Always ensure you have proper authorization before inspecting, writing, or emulating any contactless card.*
