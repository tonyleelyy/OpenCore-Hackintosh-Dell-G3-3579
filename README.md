# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-10.15.4-orange)](https://www.apple.com.cn/macos/catalina/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.5.8-9cf)](https://github.com/acidanthera/OpenCorePkg)
[![license](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

<img align="right" src="https://support.apple.com/content/dam/edam/applecare/images/en_US/macos/psp-mini-hero-macos-high-sierra-whats-new_2x.png" alt="Critter" width="250">

English | [中文](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/blob/master/README_CN.md)（同步更新）

### Latest Release: [v2.5](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/releases/tag/v2.5)

**macOS Version: 10.15.4 19E287** 

**OpenCore Version: [0.5.8 Official](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.5.8)**

This OpenCore hackintosh repo is made for i5-8300H, GTX1050, no USB Type-C version of Dell G3 3579.

> I will try to update this project as fast as possible, which means it will be adapted to the latest version of OpenCore and macOS
>
> Without [CerteKim](https://github.com/CerteKim)'s support there would be no such project.
>
> [vv-byte](https://github.com/vv-byte) helped solve the battery management problem, thanks!

## Updates
- 2020-05-27:

  Fixed battery management. Optimized dGPU blocking SSDT. (Helped by [vv-byte](https://github.com/vv-byte), thanks!)

- 2020-05-24:

  Add /Boot folder. WiFi guide updated.

- 2020-05-15:

  Fixed trackpad issue.

- 2020-05-04:

  OpenCore 0.5.8 Upadted. All kexts are up to date.

  Simplified config.plist. Remove ApfsDriverLoader.efi.

  Audio fix. iGPU frequence is now normal. Caps Lock light works again.

- 2020-04-27:

  CPU boost fixed. Simplified `config.plist` in `DeviceProperties`.

- 2020-04-21:

  Add EFI for intall in Release, which changed `ShowPicker` and `Timeout`. No other differences between these two files. No need to update if you use Release v2.0.

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

## BIOS Configuration

| **System Configuration** |      |
| ------- | ---|
| SATA Operation       | AHCI |
|                      |      |
| **Secure Bootxu**   |      |
| Secure Boot Enable   | Disabled (Uncheck) |
|  |                    |
| **Intel Software Guard Extensions** |                    |
| Intel SGX Enable | Disabled           |
|  |                    |
| **POST Behavior** |                    |
| Fastboot | Thorough           |
|  |                    |
| **Virtualization Support** |                    |
| VT for Direct I/O | Disabled (Uncheck) |

Please update BIOS to the newest version.

Everything else is set default.

## Differences between EFI.zip and EFI_Install.zip

In `EFI_Install.zip` config.plist:

```
<key>ShowPicker</key>
<true/>

<key>Timeout</key>
<integer>10</integer>
```

In `EFI.zip` config.plist:

```
<key>ShowPicker</key>
<false/>

<key>Timeout</key>
<integer>0</integer>
```

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
- Wi-Fi (Supported by [itlwm](https://github.com/zxystd/itlwm)([Guide](http://bbs.pcbeta.com/forum.php?mod=viewthread&tid=1856461)) and [IntelWifi](http://bbs.pcbeta.com/viewthread-1856465-1-2.html))

## Not Working

- dGPU (Disabled by SSDT)
- HDMI (Directly link to dGPU)
- Internal SD Card Reader
