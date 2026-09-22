# Sonara — local AI music studio (Android)

On-device music studio inspired by the [YuE2](https://github.com/multimodal-art-projection/YuE) workflow: **write a scene → get an editable score → hear it**.

YuE2 itself is a 3B GPU model (24 GB VRAM). Sonara is the phone-sized analogue: a local composer + synthesizer that runs fully on-device, with optional Grok arrangement for lyrics and style. No cloud audio render. No account.

## Install the APK

**[Download Sonara-1.0.0.apk](https://github.com/iaz54/sonara/raw/main/dist/Sonara-1.0.0.apk)** — debug-signed, Android 8+ (API 26). Also on [Releases](https://github.com/iaz54/sonara/releases/tag/v1.0.0).

On the phone: allow unknown sources. If Chrome says the file is uncommon, tap Keep, then Install.

GitHub Actions builds a fresh debug APK on every push to `main` (artifact **`sonara-debug`**).

## Features

- Text-to-song with genre detection (jazz, lo-fi, synthwave, flamenco, emo, R&B, electronic, folk, hip-hop, latin, ambient, rock)
- Editable chord score, section map, and lyrics sheet
- On-device Web Audio synth (drums, bass, harmony, lead, pad, vocalise)
- Stem mixer and live transport
- Zero-shot restyle / cover into another genre
- Agent-style revisions (darker, faster, instrumental)
- Local library (stays on the device)
- WAV export / share

## Try

```
smoky midnight jazz trio, walking bass, brushed snare
1986 synthwave night drive, analog bass, no vocals
Spanish flamenco, nylon guitar, palmas, phrygian fire
```

## Build

JDK 17 + Android SDK 35:

```
cd android
echo "sdk.dir=$ANDROID_HOME" > local.properties
gradle :app:assembleDebug
```

Package `app.sonara.studio` · minSdk 26 · targetSdk 35

YuE2 is CC BY-NC for weights; this studio’s original code is MIT and does not bundle YuE2 weights.
