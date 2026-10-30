# Changelog

## 0.6.14

**Fixed**
- Fixed immediate crash when starting tag emulation on iOS 15 (report `BE92E2AA`).
- Tried to fix tag scanning failing or not detecting tags on iOS 17.3+ and iOS 18 (reports `38C4C61C` and `8A6AADDC`).

## 0.6.13

**Fixed**
- Tried to fix the iPhone freezing when emulating with NFCTools Plus (report `2A08D941`, iPhone 15 Pro, iOS 17). Please test and tell me if it still happens.

**Changed**
- Auto-stop is now always on. Pick 5 to 30 seconds in Settings (default is 10 seconds). The "None" option is gone.
- `nfctools autostop` now takes a number from 5 to 30.
