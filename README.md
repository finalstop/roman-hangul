# Roman Hangul

**A revolution in English–Korean typing starts with the keys you already know.**

Type Korean as you hear it on a familiar QWERTY layout. `annyeonghaseyo` becomes **안녕하세요**; `saranghae` becomes **사랑해**. Suggestions help you choose a word, and a short English meaning appears where available. Roman Hangul is an Android keyboard built around the idea that switching from English letters to Hangul should feel immediate.

**Created by Harsh Gattani** · [Final Stop — yourfinalstop.com](https://yourfinalstop.com)

## What it does

- **Romanized Korean → Hangul:** live composition, curated corrections, Korean suggestions and English meaning hints.
- **English and Hinglish:** local dictionaries, suggestions, apostrophe and spelling correction, conservative personal learning and word use stats.
- **Japanese and Hindi:** Japanese kana conversion and candidates; Hindi phonetic typing with a visible **।** key. All five modes have writing review with different levels of coverage.
- **Comfortable daily typing:** two symbols pages, emoji search, original fan art stickers, themes, one handed mode, adjustable sizing, haptics and optional key sounds.
- **Useful tools:** clipboard text and image paste, cursor gestures, incognito controls, optional voice input and GIPHY GIF browsing with your own API key.

The keyboard works offline for typing, dictionaries and writing checks. GIPHY needs internet and an API key; voice typing uses the Android speech service selected on your phone. Word meanings and corrections are aids, not guaranteed translations or a full grammar model.

## Get the Android app

[**Download Roman Hangul for Android**](https://github.com/finalstop/roman-hangul/releases/latest/download/RomanHangul-3.3.2.apk) · [Release details](https://github.com/finalstop/roman-hangul/releases/latest)

After it downloads, tap the APK and follow Android’s install prompt. If asked, allow your browser or Files app to install apps. Then open Roman Hangul, tap **Enable keyboard**, and choose it under **Select keyboard**. Android may show a standard warning because this app is installed directly rather than through the Play Store.

## Install and try

The current version is **3.3.2** (Android 8.0+). Install the signed `RomanHangul-3.3.2.apk`, open the app, tap **Enable keyboard**, then **Select keyboard**. You can test it in the app or any text field:

```text
annyeonghaseyo  → 안녕하세요
gamsahamnida    → 감사합니다
saranghae       → 사랑해
```

Version 3.3.2 installs over releases 3.1 and later without removing the app. Releases through 3.0 used another signing key; see [release history](docs/RELEASE-HISTORY.md) before switching from those versions. Keep the maintainer's release signing key private; it is **not** in this repository. A locally built debug APK has a different signing certificate and cannot update the signed release in place.

## Download the full source from this repository

GitHub limits uploads through its web interface, so the 3.3.2 source archive is stored as two parts. Download both `RomanHangul-GitHub-ready.zip.part-*` files into one folder, then reassemble and extract them:

```bash
cat RomanHangul-GitHub-ready.zip.part-* > RomanHangul-GitHub-ready.zip
unzip RomanHangul-GitHub-ready.zip
```

## Build from source

Open this directory in Android Studio with Android SDK 35 and Java 17. The Android Gradle Plugin version is defined in `build.gradle`; the project does not include a Gradle wrapper. Android Studio can build a debug APK from the `app` module. The maintainer's release script, `tools/build-release.py`, requires SDK build tools, ECJ and the private release keystore. You can run the non Android host tests with:

```bash
python3 tests/run-host-tests.py /path/to/ecj.jar
```

The current release passed 46 host suites and its package, assets and v2/v3 signature were checked. Keyboard appearance, IME interactions and GIF/image handoff still need testing across real apps and devices. [Device checks](DEVICE-CHECKS-3.3.md) and the [full release history](docs/RELEASE-HISTORY.md) describe scope and limitations.

## Privacy and credits

Typing, dictionaries, learning and writing review run on the device. Incognito disables personal learning and clipboard access where Android or the user signals private mode. Voice input may be processed by your selected speech provider; GIPHY receives only searches you make there. See the app settings for controls and the exact feature behavior.

App concept and original code: **Harsh Gattani**. Project: [yourfinalstop.com](https://yourfinalstop.com). The bundled dictionary data, writing engines, GIF attribution and notices belong to their respective creators and retain their own terms; see `app/src/main/assets/DICTIONARY-CREDITS.txt`, `GRAMMAR-CREDITS.txt`, `INTEGRATION-CREDITS.txt` and `app/src/main/assets/grammar/licenses/`. The Taehyung inspired stickers are original fan art, with no official artist affiliation.

No project wide licence for the original app code has been selected. The third party licences above still apply to their components.
