# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-11.2-orange)](https://www.apple.com.cn/macos/big-sur-preview/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.6.7-9cf)](https://github.com/acidanthera/OpenCorePkg)
[![license](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

<img align="right" src="https://support.apple.com/content/dam/edam/applecare/images/en_US/macos/psp-mini-hero-macos-high-sierra-whats-new_2x.png" alt="Critter" width="250">

English | [中文](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/blob/master/README_CN.md)（同步更新）

### Latest Release: [v4.3](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/releases/tag/v4.3)

**macOS Version: 11.2.2**

**OpenCore Version: [0.6.7 Official](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.6.7)**

This OpenCore hackintosh repo is made for i5-8300H, GTX1050, no USB Type-C version of Dell G3 3579.

> I will try to update this project as fast as possible, which means it will be adapted to the latest version of OpenCore and macOS
>
> Without [CerteKim](https://github.com/CerteKim)'s support there would be no such project.
>
> [vv-byte](https://github.com/vv-byte) helped solve the battery management problem, thanks!
>
> [CalvinXu](https://github.com/CalvinXu17) helped add Windows boot support, thanks!
>
> PyhNOVWH provide SSDT for i2C trackpad, thanks!
>
> Dell G3 Hackintosh QQ Group: 1028961766

Try this EFI for further updates and Thunderbolt supports:(Credit: CalvinXu)

https://github.com/CalvinXu17/OpenCore-Dell-G3-3579-1060mq

## Updates
- 2021-03-02

  OC 0.6.7 & kexts updated.
  
<details>
  <summary>2020-11-20</summary>
  - Fixed issue [#38](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/issues/38)
  <br>
  - OC 0.6.3 updated.
</details>

<details>
  <summary>2020-10-27</summary>
  OC 0.6.2 updated.
</details>

<details>
  <summary>2020-10-05</summary>
  - Add gui theme for OC.
  <br>
  - Enhanced the stability of Bluetooth.
</details>

<details>
  <summary>2020-09-18</summary>
  - Bug fixed [#30](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/issues/30).
  <br>
  - Use [AirportItlwm](http://bbs.pcbeta.com/viewthread-1848662-1-1.html) as wifi driver.(Handoff supported)
</details>

<details>
  <summary>2020-09-08</summary>
  - Updated OC 0.6.1 Official. All kexts are up to date.
  <br>
  - Added SSDT for i2C trackpad. (Thanks PyhNOVWH)
</details>

<details>
  <summary>2020-08-04</summary>
  - Updated OC 0.6.0 Official. All kexts are up to date.
  <br>
  - Supported macOS 11.0 Big Sur.
  <br>
  - Please use [HeliPort](https://github.com/OpenIntelWireless/HeliPort) as WiFi Client.
</details>

<details>
  <summary>2020-07-25</summary>
  - Fixed USBPorts.kext for DW1820A. Updated IntelBluetooth, NoTouchID.
  <br>
  - Still waiting for OC 0.6.0...
</details>

<details>
<summary>2020-06-26</summary>
  - Updated VoodooI2C, itlwm
  <br>
  - Add Windows boot support in OC (Thanks [CalvinXu](https://github.com/CalvinXu17))
</details>

<details>
  <summary>2020-06-02</summary>
  - Updated OpenCore 0.5.9. All kexts are up to date.
  <br>
  - Supprot macOS 10.15.5.
  <br>
  - Add itlwm.kext, edit your WiFi info in /OC/Kexts/itlwm.kext/Contents/Info.plist.
</details>

<details>
  <summary>2020-05-27</summary>
  - Fixed battery management. Optimized dGPU blocking SSDT. (Helped by [vv-byte](https://github.com/vv-byte), thanks!)
</details>

<details>
  <summary>2020-05-24</summary>
  - Add /Boot folder. WiFi guide updated.
</details>

<details>
  <summary>2020-05-15</summary>
  - Fixed trackpad issue.
</details>

<details>
  <summary>2020-05-04</summary>
  - OpenCore 0.5.8 Upadted. All kexts are up to date.
  <br>
  - Simplified config.plist. Remove ApfsDriverLoader.efi.
  <br>
  - Audio fix. iGPU frequence is now normal. Caps Lock light works again.
</details>

<details>
  <summary>2020-04-27</summary>
  - CPU boost fixed. Simplified `config.plist` in `DeviceProperties`.
</details>

<details>
  <summary>2020-04-21</summary>
  - Add EFI for intall in Release, which changed `ShowPicker` and `Timeout`. No other differences between these two files. No need to update if you use Release v2.0.
</details>

<details>
  <summary>2020-04-13</summary>
  - WiFi works again. Instruction down below.
</details>

<details>
  <summary>2020-04-13</summary>
  - There are some problems of the WiFi. Don't know how to fix it, please wait.
</details>

<details>
  <summary>2020-04-13</summary>
  - After rebuilding my ACPI folder and fix my config.plist, Intel WiFi is FINALLY supported!!!
  <br>
  - Please check https://github.com/zxystd/itlwm and enjoy!!!
</details>

<details>
  <summary>2020-04-11</summary>
  - Updated to MacOS 10.15.4 19E287. Changed OpenCore to offical release 0.5.7 ver. and fixed the structure of Config.plist.
  <br>
  - Updated Lilu, VirtualSMC, AppleALC, WhateverGreen, SMCBatteryManager, NVMeFix.
  <br>
  - Customized and updated IntelBluetoothFirmware, now the size is much smaller. Updated IntelBluetoothInjector.
</details>

<details>
  <summary>2020-03-31</summary>
  - Deleted SSDT-USBX and added USBPower.kext.
</details>

<details>
  <summary>2020-03-28</summary>
  - I found that the Caps Lock light work perfectly after the lastest update!
</details>

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

## Working

- macOS 11.2.2
- CPU (Boost to 4.0Ghz)
- iGPU
- Ethernet
- Audio (Layout=15)
- USB (Customed by USBPorts.kext)
- Trackpad
- WebCam
- Bluetooth (With On/Off buttom)
- Wi-Fi (Supported by [AirportItlwm](http://bbs.pcbeta.com/viewthread-1848662-1-1.html))

## Not Working

- dGPU (Disabled by SSDT)
- HDMI (Directly link to dGPU)
- Internal SD Card Reader
