# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-10.15.4-orange)](https://www.apple.com.cn/macos/catalina/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.5.7-9cf)](https://github.com/acidanthera/OpenCorePkg)
[![license](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

<img align="right" src="https://support.apple.com/content/dam/edam/applecare/images/en_US/macos/psp-mini-hero-macos-high-sierra-whats-new_2x.png" alt="Critter" width="250">

English | [中文](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/blob/master/README_CN.md)（同步更新）

### Latest Release: [v2.0](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/releases/tag/v2.0)

**macOS Version: 10.15.4 19E287**

**OpenCore Version: [0.5.7 Offical](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.5.7)**

This OpenCore hackintosh repo is made for i5-8300H, GTX1050, no USB Type-C version of Dell G3 3579.

> I will try to update this project as fast as possible, which means it will be adapted to the latest version of OpenCore and macOS
>
> Although the project has been completely separated from the support of [CerteKim](https://github.com/CerteKim)'s [Dell-G3-3579-Hackintosh-OpenCore](https://github.com/CerteKim/Dell-G3-3579-Hackintosh-OpenCore), but I still want to thank him. Without his support there would be no such project.

## Update
- 2020-04-13:

  WiFi works again. Instruction down below.

- 2020-04-13: 

  There are some problems of the WiFi. Don't know how to fix it, please wait.

- 2020-04-13: 

  After rebuilding my ACPI folder and fix my config.plist, Intel WiFi is FINALLY supported!!!

  Please check https://github.com/zxystd/itlwm and enjoy!!!

- 2020-04-11: 

  Updated to MacOS 10.15.4 19E287. Changed OpenCore to offical release 0.5.7 ver. and fixed the structure of Config.plist.

  Updated Lilu, VirtualSMC, AppleALC, WhateverGreen, SMCBatteryManager, NVMeFix.

  Customized and updated IntelBluetoothFirmware, now the size is much smaller. Updated IntelBluetoothInjector.

- 2020-03-31: Deleted SSDT-USBX and added USBPower.kext.

- 2020-03-28: I found that the Caps Lock light work perfectly after the lastest update!

## WiFi Instruction

1. Download Xcode via App Store.

2. Clone master in [itlwm](https://github.com/zxystd/itlwm), unzip.

3. Open itlwm.xcodeproj in Xcode.

4. You may find a yellow "⚠️1" icon at the top of Xcode's interface, click it - "Update to recommded settings" - "Perform Changes".

5. Return to "File" on the left, find "mac80211.cpp".

6. Use Command + F to find "zxyssdt112233".

7. Change your WiFi name in ssid_name = "" 

   And password in ssid_pwd = ""

   Use Command + S to save your changes.

8. Click the little block next to "My Mac" and choose "itlwm".

9. Press the Play button to build.

10. Find "Products" folder on the left and right click "itlwm.kext", "Show in Finder".

11. Copy "itlwm.kext" to a place you knew.

12. **SHUTDOWN your computer, and boot again in OC(do not reboot from Windows)**

13. **Unplug your Ethernet first!! (I don't konw why)**

14. Use Terminal to run these: (replace "itlwm.kext" with your file address like "/Users/tony/Downloads/itlwm.kext")

```
cp -R itlwm.kext /tmp
sudo chown -R root:wheel /tmp/*.kext
sudo kextutil /tmp/*.kext
```

14. Enjoy your wifi~ The speed might be slow.

Credit:
https://github.com/zxystd/itlwm

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
| Wireless Card | Inte Wireless-AC 9462 | ✅ |

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
- Wi-Fi (Supported by [itlwm](https://github.com/zxystd/itlwm))

## Issue

- Audio lost sometimes, fixed with reboots.

## Not Working

- dGPU (Disabled by SSDT)
- HDMI (Directly link to dGPU, controlled by Optimus)
- Internal SD Card Reader

## For Installation

Edit Config.plist, find

```
<key>ShowPicker</key>
<false/>
```

Change the value to ```true```
