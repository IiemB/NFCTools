# Changelog

## 0.6.18

**Added**
- NFCTools Plus now shows the app icon next to its tiles in Settings › Control Center, and in Sileo / Zebra.
- Customize the NFCTools Plus emulation overlay: choose Pill, Compact, Island, Card, Bubble or Hidden, top, center or bottom of the screen, how it animates in (Drop, Pop, Fade or None), and a countdown bar that empties until auto-stop.
- The NFCTools Plus overlay now shows the emulated tag's own icon and color. Tap **Preview Overlay** to see it.

**Changed**
- NFCTools Plus settings now open in their own page from Settings.

**Fixed**
- Tapping **Read tag** no longer does nothing when the reader can't start: an alert now explains why (reports `99FAD258`, `AABBB3E8`).
- When the NFC service keeps answering "Busy", the app no longer restarts it on every tap, which briefly took down Apple Pay and other NFC features. Tag reading on iOS 17.3 and later is still being investigated.
- If the app wasn't installed with TrollStore, it now says so instead of failing silently. TrollStore is the only supported install method.
- NFCTools Plus no longer fills the log with a line every time the screen locks.

## 0.6.17

**Added**
- New **What's New** page in Settings › Support shows this changelog, with your installed version marked "Current".

**Changed**
- Terms of Use and Privacy Policy are now kept as Markdown files in [`content/legal/`](https://github.com/IiemB/NFCTools/tree/main/content/legal), so they're easier to read on GitHub.
- What's New and Terms & Privacy always load the latest text from GitHub. If they can't load, tap **Try Again** or **View on GitHub**.
- A placeholder now shows while these pages load, instead of a spinner.

## 0.6.16

**Fixed**
- Tried to fix the app still crashing about 2 seconds after starting tag emulation on iOS 15 (report `A6537168`).

## 0.6.15

**Fixed**
- Tried to fix immediate crash when starting tag emulation on iOS 15 (report `BE92E2AA`).

## 0.6.14

**Fixed**
- Tried to fix tag scanning failing or not detecting tags on iOS 17.3+ and iOS 18 (reports `38C4C61C` and `8A6AADDC`).

## 0.6.13

**Fixed**
- Tried to fix the iPhone freezing when emulating with NFCTools Plus (report `2A08D941`, iPhone 15 Pro, iOS 17). Please test and tell me if it still happens.

**Changed**
- Auto-stop is now always on. Pick 5 to 30 seconds in Settings (default is 10 seconds). The "None" option is gone.
- `nfctools autostop` now takes a number from 5 to 30.
