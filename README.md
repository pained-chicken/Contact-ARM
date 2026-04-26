# Contact

A macOS utility app that fixes Unicode filename encoding issues (NFD → NFC normalization) via drag & drop.

> This is a fork of [namhokim/cocoa_app](https://github.com/namhokim/cocoa_app) rebuilt as a Universal Binary with native Apple Silicon (arm64) support.

## What it does

macOS and certain file systems store filenames in NFD (Decomposed Unicode), which can cause compatibility issues — broken filenames, failed lookups, or garbled text when moving files between systems. Contact fixes this by batch-renaming files to NFC (Composed Unicode).

## Requirements

- macOS 11.0 or later
- Apple Silicon (arm64) or Intel (x86_64)

## How to use

1. Launch Contact.app
2. Drag and drop files or folders onto the window, or click the **Open** button
3. The app generates a shell script and runs it to rename the files in place

## Build

```bash
git clone https://github.com/pained-chicken/Contact-ARM.git
cd Contact-ARM
xcodebuild -scheme Contact -configuration Release ONLY_ACTIVE_ARCH=NO build
```

The resulting `Contact.app` is a Universal Binary supporting both arm64 and x86_64.

## Changes from original

- Added `ARCHS = arm64 x86_64` for Universal Binary support
- Updated `MACOSX_DEPLOYMENT_TARGET` from 10.11 to 11.0
- Added `.gitignore` for Xcode

## License

MIT — see [LICENSE](LICENSE).  
Original author: [namhokim](https://github.com/namhokim) / [namocom.tistory.com/907](https://namocom.tistory.com/907)
