# Before It Was Blue

An interactive finger-worn wearable that lets museum visitors feel how firing temperature shaped Jingdezhen blue-and-white porcelain.

Developed for **CDE5312 Beyond the Surface: Exploring Interactive Wearables** (NUS, AY 2026/27) with Singapore ArCH Square, home to porcelain fragments recovered from the Temasek Wreck.

## Overview
Museum displays show finished porcelain behind glass, leaving the craft behind it invisible. *Before It Was Blue* makes the intangible cultural heritage (ICH) of kiln firing tangible: visitors press and hold a touchscreen to advance a simulated firing while their fingertip warms, then see how underfired, ideal firing, or overfired changes the porcelain's blue.

**Visitor journey:** Experience → Discover → Appreciate

## How It Works
- **Heat:** Two Peltier modules on the sides of the finger warm in step with the simulated kiln
- **Vibration:** Two motors on the dorsal side mark checkpoints (single pulse at ~1200°C, double pulse at ~1300°C)
- **Screen and audio:** A browser interface shows the firing stage and outcome (underfired, suitable, overfired) with voice guidance
- **Free fingerpad:** Visitors control the firing and feel its heat with the same finger

## Hardware and Control
- ESP32-WROOM-32 hosting the web interface offline via LittleFS and its own Wi-Fi access point
- K-type thermocouple with MAX6675, sampled every ~500 ms
- PID closed-loop control (Kp 24.0, Ki 0.8, Kd 0.2) targeting 38°C
- Safety cut-off at 41°C, on invalid readings, or after ~1.5 s without a reading
- MOSFET-switched TECs and vibration motors on separate adjustable power branches
- 3D-printed finger housing (Rhino 8) and laser-cut control box

## Strength and Limitation
User testing with six participants rated understanding highest (M = 4.79/5) and usability strongly (M = 4.61/5). Telling the two vibration patterns apart and fitting different finger sizes were the main areas to improve.

## Live Demo
[before-it-was-blue.vercel.app](https://before-it-was-blue.vercel.app/)

## Credits
- **Team:** Chen Shiyu · Hoang Linh Chi · Nadia Wijaya Puspo · Zhu Boning
- **Supervisor:** Dr Cai Shaoyu
- **Technical assistance:** Erin Ng Xin Le · Choi Mijin
