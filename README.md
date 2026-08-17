# CinaHub

**Turn any phone into a universal remote for your home theater — over Wi‑Fi, no infrared needed.**

CinaHub is a free, cross‑platform remote‑control app. Instead of juggling a drawer of remotes (or buying an expensive control hub like Control4 / ELAN), CinaHub talks to your gear directly over your home Wi‑Fi network. One app, one phone, every device.

[![Download on the App Store](https://img.shields.io/badge/App_Store-Download-0A7CF5?logo=apple&logoColor=white)](https://apps.apple.com/us/app/cinahub/id6790016957?utm_source=github&utm_medium=repo)
[![Get it on Google Play](https://img.shields.io/badge/Google_Play-Download-414FA1?logo=googleplay&logoColor=white)](https://play.google.com/store/apps/details?id=com.cinahub.app&utm_source=github&utm_medium=repo)
[![Get it from Microsoft Store](https://img.shields.io/badge/Microsoft_Store-Download-0078D4?logo=microsoft&logoColor=white)](https://apps.microsoft.com/store/detail/9pdxn0618930?utm_source=github&utm_medium=repo)

---

## Why CinaHub

- **No hub, no extra hardware** — a phone on your LAN is all you need.
- **No infrared** — control works through Wi‑Fi / local network, so any phone works, even one with no IR blaster.
- **Free** — no subscription, no license fee.
- **Cross‑platform** — Android, iOS and Windows from a single Flutter codebase.
- **Real‑time sync** — power, volume and input source update live as you use them.

## Features

- Universal remote for multiple brands in one screen
- One‑tap scenes ("Watch a movie", "Listen to music") generated from your device setup
- Live device status (volume, input source, power)
- Directional pad, home / back / menu / OK for each device
- Per‑device volume, mute and source switching

## Supported devices

| Brand / Device | Protocol | Notes |
|----------------|----------|-------|
| **Denon / Marantz** AVR | Telnet (23) + HTTP API | Full series: AVR‑X2800H, X3800H, X4800H, AVC‑X6800H, SR7015, SR8015, etc. |
| **Apple TV** | mDNS + MRP | 2015+ models (HD 2015, 4K 1–3 gen 2017–2022) |
| **Roku** | HTTP (8060) | Streaming players & Roku TVs |
| **Samsung** Smart TV | WebSocket + JSON‑RPC (8001) | Modern Tizen models |
| **Sony Bravia** | REST API + IRCC (20060) | Android TV models |
| **VidOn** (威动) | TCP (33080) | Media players / servers |
| **Xiaomi / Redmi** TV | HTTP (6095) | Source switching limited to HDMI 1 / 2 by the TV API |

**Planned:** LG OLED (WebSocket 3000), Epson projectors (ESC/VP21), and more.

## Download

Pick your platform:

- **iPhone / iPad** — [App Store](https://apps.apple.com/us/app/cinahub/id6790016957?utm_source=github&utm_medium=repo)
- **Android** — [Google Play](https://play.google.com/store/apps/details?id=com.cinahub.app&utm_source=github&utm_medium=repo) or sideload the latest APK from [GitHub Releases](https://github.com/Benjamin-LY777/cinahub/releases)
- **Windows** — [Microsoft Store](https://apps.microsoft.com/store/detail/9pdxn0618930?utm_source=github&utm_medium=repo)

> Android users in regions without Google Play can install the APK from GitHub Releases. Allow "Install from unknown sources" when prompted.

## How it works

CinaHub runs entirely on your local network. It discovers devices via SSDP / mDNS and controls them through their native IP protocols — there is no cloud relay, so control keeps working even when the internet is down.

## Privacy

CinaHub does not upload your usage or device data. See the [privacy policy](https://benjamin-ly777.github.io/cinahub/privacy.html).

## Development

```bash
# Build the Android release APK (signed with cinahub-release.jks)
cd cinehub_app
flutter build apk --release

# Serve the APK on your LAN for phone install
python serve_apk.py

# Run the device simulator GUI (no real hardware needed for testing)
python -m cinehub.simulators.run_gui
```

## License

MIT
