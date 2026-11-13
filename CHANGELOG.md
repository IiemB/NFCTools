# Changelog

## 0.7.7

**Fixed**
- Another attempt at "Can't Start Reader (Busy)" on iOS 17.3.1. If you still see it, please send a report from Diagnostics.

## 0.7.6

**Changed**
- The Ko-fi link in Settings is now a banner at the top of the page.

## 0.7.5

**Added**
- Support on Ko-fi: a new link in Settings › About if you'd like to support development.

**Fixed**
- Widget reliability improvements on iOS 17 and later.

**Changed**
- The Diagnostics "Widgets" check now also reports whether the widget can read its tag data, so a Send Report can pinpoint why a widget shows no icon. If your widget icon isn't showing, please open Settings › Diagnostics and send a report.

## 0.7.4

**Added**
- Send Report now has an optional Contact field, so we can reply to you about your report.
- Reports can include attachments: recent crash logs from NFCTools (included by default, with a switch to leave them out), plus up to 4 photos or files. Like the log, attachments are encrypted so only the developer can read them.

**Fixed**
- "Can't Start Reader… (Busy)" on some devices, notably iOS 17.3.1. If you still see it on this version, please send a report.

## 0.7.3

**Changed**
- "Update Available" is now a card on top of your tags, with a Download button. Swipe it aside like any card, or tap ✕ to hide it until the next release.

## 0.7.2

**Added**
- A tag you read and save now gets a random card color, different from your other tags where possible. You can still change it.

**Changed**
- New Home: your saved tags are now a stack of cards in each tag's color and icon. Swipe left or right to move through them (it loops), and tap **▶** on a card to emulate it.
- Tap a card to open it: it grows into the tag's details. Tap the card, or pull down and let go, to go back.
- In a tag's details, the buttons are **Emulate**, **Records**, **Write** and **More**. **Update from Tag** and the other actions are in **More**.
- Add and Settings are now buttons below the cards.
- **Reorder Tags** and **Export All Tags** moved to Settings › Tags.
- Settings now opens as a sheet.
- New Read screen: waves at the top of the screen show where the iPhone's NFC reader is, so you know where to hold the tag.
- New Emulate screen: shows the tag's card, and flashes and vibrates when a reader touches your iPhone.
- Write, Update from Tag and Clone now use the same screen as Read, each in its own color, showing the saved tag's card.

**Fixed**
- Reading a tag no longer closes the Read screen straight away when the NFC service is busy and NFCTools restarts it.
- If the NFC service doesn't answer, the Read screen now closes with a message after a few seconds instead of staying on "Starting reader…".

**Removed**
- Search on Home.

## 0.6.19

**Added**
- Home now tells you when a new version is available on GitHub, with a **Download** button for the release. Close it to hide it until the next version.
- **Check for Updates** in Settings › Support checks GitHub right away and tells you whether a new version is available.

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
