# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-10.15.4-orange)](https://www.apple.com/macos/catalina/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.5.7-9cf)](https://github.com/acidanthera/OpenCorePkg)
[![license](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

<img align="right" src="https://support.apple.com/content/dam/edam/applecare/images/en_US/macos/psp-mini-hero-macos-high-sierra-whats-new_2x.png" alt="Critter" width="250">

[English](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/blob/master/README.md) | 中文

### 最新的Release：[v2.0](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/releases/tag/v2.0)

**macOS版本：10.15.4 19E287**

**OpenCore版本：[0.5.7 Offical](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.5.7)**

来源: [CerteKim](https://github.com/CerteKim)的 [Dell-G3-3579-Hackintosh-OpenCore](https://github.com/CerteKim/Dell-G3-3579-Hackintosh-OpenCore) （万分感谢！）

我这一版本的EFI修改自CerteKim的OpenCore黑苹果项目。
我将它适配了我的i5-8300H，GTX1050，没有USB Type-C版本的Dell G3 3579。

> 我会尽可能迅速地更新这一项目，尽量保证适配最新版本的OpenCore和macOS系统。

## 更新
- 2020-04-13：

  在重新构建ACPI目录并修改 Config.plist 之后，终于！！！可以使用英特尔WiFi了！！！

  请使用 https://github.com/zxystd/itlwm 尽情网上冲浪！！！

- 2020-04-11：

  更新至 MacOS 10.15.4 19E287。更新 OpenCore 到官方Release 0.5.7 版本并完善了Config.plist的结构。

  更新 Lilu, VirtualSMC, AppleALC, WhateverGreen, SMCBatteryManager, NVMeFix。

  更新并定制了 IntelBluetoothFirmware，驱动文件大幅缩小。同时更新了 IntelBluetoothInjector。

- 2020-03-31：删除了SSDT-USBX并添加了USBPower.kext以实现更好的USB驱动方法。

- 2020-03-28：我发现更新到最新版本后，大小写灯已正常工作！

## 待办事项
- 2020-04-13：检查音频问题。

## 电脑配置

|   配件   |             规格              | 工作状态 |
| :------: | :---------------------------: | :------: |
|   模组   |         Dell G3 3579          |    ✅     |
|  处理器  | Intel Core i5-8300H @ 2.30Ghz |    ✅     |
|   内存   |    8GB Micron DDR4 2666Mhz    |    ✅     |
| 固态硬盘 |   Hikvision C2000Pro 512GB    |    ✅     |
| 机械硬盘 |         WD10SPZX 1TB          |    ✅     |
| 核芯显卡 |    Intel UHD Graphics 630    |    ✅     |
| 独立显卡 |  NVIDIA GeForce GTX 1050 4G   |    🚫     |
|   声卡   |        Realtek ALC236         |    ✅     |
| 有线网卡 |        Realtek RTL8111        |    ✅     |
| 无线网卡 |     Inte Wireless-AC 9462     |  ✅  |

## 工作的部分

- macOS 10.15.4
- CPU（睿频4.0Ghz）
- 核芯显卡
- 有线网卡
- 音频（Layout=15）
- USB（定制USBPorts.kext）
- 触摸板
- 摄像头
- 蓝牙（带有蓝牙开关）
- Wi-Fi（使用[itlwm](https://github.com/zxystd/itlwm))

## 问题

- 音频偶尔不驱动，重启解决。

## 不工作的部分

- 独立显卡（已使用SSDT屏蔽）
- HDMI（使用Optimus技术，直接连接到独立显卡，故无解）
- 内置读卡器

## 安装前

修改Config.plist，找到

```
<key>ShowPicker</key>
<false/>
```

将值改成```true```
