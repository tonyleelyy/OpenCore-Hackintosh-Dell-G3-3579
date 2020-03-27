# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-10.15.4-orange)](https://www.apple.com/macos/catalina/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.5.7-9cf)](https://github.com/williambj1/OpenCore-Factory/)
[![license](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

<img align="right" src="https://support.apple.com/content/dam/edam/applecare/images/en_US/macos/psp-mini-hero-macos-high-sierra-whats-new_2x.png" alt="Critter" width="250">

English | 中文（同步更新）

### Latest Release: 1.0

Origin: [CerteKim](https://github.com/CerteKim)'s [Dell-G3-3579-Hackintosh-OpenCore](https://github.com/CerteKim/Dell-G3-3579-Hackintosh-OpenCore) (Huge Thanks!)

My version of this EFI is edited from CerteKim's Opencore Hackintosh project.
I made it work for my i5-8300H, GTX1050, no usb type-c version Dell G3 3579.

> I will try to update this project as fast as possible, that means it will be adapted to the latest version of OpenCore and macOS

## Configuration

| Specifications | Detail | Working |
| :------------: | :------: | :--------: |
| Model | Dell G3 3579 | ✅ |
| Processor | Intel Core i5-8300H @ 2.30Ghz | ✅ |
| Memory | 8GB Micron DDR4 2666Mhz | ✅ |
| SSD | Hikvision C2000Pro 512GB | ✅ |
| HDD | WD10SPZX 1TB | ✅ |
| iGPU | Intel UHD Graphics 630i | ✅ |
| dGPU | NVIDIA GeForce GTX 1050 4G | 🚫 |
| Sound Card | Realtek ALC236 | ✅ |
| Ethernet Card | Realtek RTL8111 | ✅ |
| Wireless Card | Inte Wireless-AC 9462 | BT only |

## Working

- macOS 10.15.4
- CPU (Boost to 4.0Ghz)
- iGPU
- Ethernet
- Audio (Layout=15)
- USB (Customed by USBPorts.kext)
- Trackpad
- WebCam
- Bluetooth (With On/Off buttom)

## Issue

- Audio lost sometimes, fixed with reboots.
- Caps Lock light on keyboard

## Not Working

- dGPU (Disabled by SSDT)
- HDMI (Directly link to dGPU, controlled by Optimus)
- Internal SD Card Reader
- Wi-Fi (Will be supported by [itlwm](https://github.com/zxystd/itlwm) later hopefully)

## For Installation

Edit Config.plist, find

```
<key>ShowPicker</key>
<false/>
```

Change the value to ```true```
