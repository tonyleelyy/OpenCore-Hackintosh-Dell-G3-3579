# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-10.15.4-orange)](https://www.apple.com.cn/macos/catalina/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.5.7-9cf)](https://github.com/williambj1/OpenCore-Factory/)
[![license](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

<img align="right" src="https://support.apple.com/content/dam/edam/applecare/images/en_US/macos/psp-mini-hero-macos-high-sierra-whats-new_2x.png" alt="Critter" width="250">

English | [中文](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/blob/master/README_CN.md)（同步更新）

### Latest Release: [v1.0](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/releases/tag/v1.0)

**macOS Version: 10.15.4**

**OpenCore Version: 0.5.7**

Origin: [CerteKim](https://github.com/CerteKim)'s [Dell-G3-3579-Hackintosh-OpenCore](https://github.com/CerteKim/Dell-G3-3579-Hackintosh-OpenCore) (Huge Thanks!)

My version of this EFI is edited from CerteKim's Opencore Hackintosh project.
I made it work for my i5-8300H, GTX1050, no USB Type-C version of Dell G3 3579.

> I will try to update this project as fast as possible, which means it will be adapted to the latest version of OpenCore and macOS

## Update
- 2020-03-31: Deleted SSDT-USBX and added USBPower.kext.
- 2020-03-28: I found that the Caps Lock light work perfectly after the lastest update!

## To-Do
- 2020-03-29: I'm trying to rebuild my SSDT, hope that can fix audio and add OpenCore Windows support.

## Configuration

| Specifications | Detail | Working |
| :------------: | :------: | :--------: |
| Model | Dell G3 3579 | ✅ |
| Processor | Intel Core i5-8300H @ 2.30Ghz | ✅ |
| Memory | 8GB Micron DDR4 2666Mhz | ✅ |
| SSD | Hikvision C2000Pro 512GB | ✅ |
| HDD | WD10SPZX 1TB | ✅ |
| iGPU | Intel UHD Graphics 630 | ✅ |
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
