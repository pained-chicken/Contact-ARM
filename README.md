# Contact

**[한국어](#한국어) | [English](#english)**

---

## 한국어

파일명의 유니코드 인코딩(NFD → NFC)을 일괄 정규화하는 macOS 유틸리티 앱입니다.

> 이 저장소는 [namhokim/cocoa_app](https://github.com/namhokim/cocoa_app)을 포크하여 Apple Silicon(arm64)을 네이티브 지원하는 Universal Binary로 재빌드한 버전입니다.

### 어떤 앱인가요?

macOS와 일부 파일 시스템은 파일명을 NFD(분해 유니코드) 형태로 저장합니다. 이로 인해 시스템 간 파일 이동 시 파일명이 깨지거나 검색이 안 되는 문제가 발생할 수 있습니다. Contact는 파일명을 NFC(정규 유니코드)로 일괄 변환하여 이 문제를 해결합니다.

### 요구 사항

- macOS 11.0 이상
- Apple Silicon(arm64) 또는 Intel(x86_64)

### 사용 방법

1. Contact.app 실행
2. 파일 또는 폴더를 창에 드래그 & 드롭하거나 **Open** 버튼 클릭
3. 앱이 셸 스크립트를 생성하고 실행하여 파일명을 제자리에서 변환

### 빌드 방법

```bash
git clone https://github.com/pained-chicken/Contact-ARM.git
cd Contact-ARM
xcodebuild -scheme Contact -configuration Release ONLY_ACTIVE_ARCH=NO build
```

빌드 결과물 `Contact.app`은 arm64와 x86_64를 모두 지원하는 Universal Binary입니다.

### 원본과의 변경사항

- `ARCHS = arm64 x86_64` 추가로 Universal Binary 지원
- `MACOSX_DEPLOYMENT_TARGET` 10.11 → 11.0 으로 상향
- Xcode용 `.gitignore` 추가

### 라이선스

MIT — [LICENSE](LICENSE) 참고  
원개발자: [namhokim](https://github.com/namhokim) / [namocom.tistory.com/907](https://namocom.tistory.com/907)

---

## English

A macOS utility app that fixes Unicode filename encoding issues (NFD → NFC normalization) via drag & drop.

> This is a fork of [namhokim/cocoa_app](https://github.com/namhokim/cocoa_app) rebuilt as a Universal Binary with native Apple Silicon (arm64) support.

### What it does

macOS and certain file systems store filenames in NFD (Decomposed Unicode), which can cause compatibility issues — broken filenames, failed lookups, or garbled text when moving files between systems. Contact fixes this by batch-renaming files to NFC (Composed Unicode).

### Requirements

- macOS 11.0 or later
- Apple Silicon (arm64) or Intel (x86_64)

### How to use

1. Launch Contact.app
2. Drag and drop files or folders onto the window, or click the **Open** button
3. The app generates a shell script and runs it to rename the files in place

### Build

```bash
git clone https://github.com/pained-chicken/Contact-ARM.git
cd Contact-ARM
xcodebuild -scheme Contact -configuration Release ONLY_ACTIVE_ARCH=NO build
```

The resulting `Contact.app` is a Universal Binary supporting both arm64 and x86_64.

### Changes from original

- Added `ARCHS = arm64 x86_64` for Universal Binary support
- Updated `MACOSX_DEPLOYMENT_TARGET` from 10.11 to 11.0
- Added `.gitignore` for Xcode

### License

MIT — see [LICENSE](LICENSE)  
Original author: [namhokim](https://github.com/namhokim) / [namocom.tistory.com/907](https://namocom.tistory.com/907)
