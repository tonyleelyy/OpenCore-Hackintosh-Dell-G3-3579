# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-11.0-orange)](https://www.apple.com.cn/macos/big-sur-preview/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.6.3-9cf)](https://github.com/acidanthera/OpenCorePkg)
[![license](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

<img align="right" src="https://support.apple.com/content/dam/edam/applecare/images/en_US/macos/psp-mini-hero-macos-high-sierra-whats-new_2x.png" alt="Critter" width="250">

[English](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/blob/master/README.md) | 中文

### 最新的Release：[v4.3](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/releases/tag/v4.3)

**macOS版本：11.0.1**

**OpenCore版本：[0.6.3 Official](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.6.3)**

本 OpenCore 黑苹果项目适配 i5-8300H，GTX1050，没有USB Type-C版本的Dell G3 3579。

> 我会尽可能迅速地更新这一项目，尽量保证适配最新版本的OpenCore和macOS系统。
>
> 没有 [CerteKim](https://github.com/CerteKim) 的支持就不会有这个项目的诞生，感谢。
>
> [vv-byte](https://github.com/vv-byte) 协助解决了节能五项的问题，感谢。
>
> [CalvinXu](https://github.com/CalvinXu17) 提供了 OC 启动 Windows 的方法，感谢。
>
> PyhNOVWH 提供了i2C触控板中断模式的SSDT，感谢。
>
> 戴尔G3黑苹果交流群：1028961766，感谢群友帮忙测试。

Tips：

- 如果你的电脑无法从睡眠中被唤醒，在 系统偏好设置>节能 中关闭小憩。（感谢 [DongRih](https://github.com/DongRih)）

## 更新
- 2020-11-20

  修复了issue [#38](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/issues/38)
  
  升级至 OC 0.6.3

<details>
  <summary>2020-10-27</summary>
  升级至 OC 0.6.2 
</details>

<details>
  <summary>2020-10-05</summary>
  - 增加了原生可视化界面
  <br>
  - 提升了蓝牙稳定性（存疑） 
</details>

<details>
  <summary>2020-09-18</summary>
  - Bug 修复 [#30](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/issues/30)。
  <br>
  - 使用 [AirportItlwm](http://bbs.pcbeta.com/viewthread-1848662-1-1.html) 作为 WiFi 驱动（原生菜单，接力支持）
</details>

<details>
  <summary>2020-09-08</summary>
  - 更新至 OC 0.6.1 正式版。所有驱动更至最新。
  <br>
  - 增加了i2C触控板中断模式的SSDT。（感谢PyhNOVWH）
</details>

<details>
  <summary>2020-08-04</summary>
  - 更新至 OC 0.6.0 正式版。所有驱动更至最新。
  <br>
  - 支持 macOS 11.0 Big Sur。
  <br>
  - 请使用 [HeliPort](https://github.com/OpenIntelWireless/HeliPort) 作为 WiFi 客户端。
</details>

<details>
  <summary>2020-07-25</summary>
  - 为使用 DW1820A 的朋友重新定制了USBPorts。更新了 IntelBluetooth，NoTouchID。
  <br>
  - 在 OC 0.6.0 和 Big Sur 正式版出来之前可能都不会有大更新了，能完善的都已经完善了~
</details>

<details>
<summary>2020-06-26</summary>
  - 更新了 VoodooI2C 和 itlwm
  <br>
  - 增加了 OC 启动 Windows 支持（感谢 [CalvinXu](https://github.com/CalvinXu17)）
</details>

<details>
  <summary>2020-06-02</summary>
  - 更新至 OpenCore 0.5.9，顺带更新驱动，开始进入慢速更新状态。
  <br>
  - 支持 macOS 10.15.5
  <br>
  - 添加了 itlwm.kext 以驱动WiFi，请在 /OC/Kexts/itlwm.kext/Contents/Info.plist 里添加自己的WiFi信息。
</details>

<details>
  <summary>2020-05-27</summary>
  - 修复了节能五项（笔记本只有四项），优化了禁用独显的SSDT。（[vv-byte](https://github.com/vv-byte) 协助了此次更新，感谢）
</details>

<details>
  <summary>2020-05-24</summary>
  - 添加了 /Boot 文件夹，请尽量使用 BOOTx64.efi 来引导。更新了 WiFi 驱动教程。
</details>

<details>
  <summary>2020-05-15</summary>
  - 修复了触控板无法使用的问题。
</details>

<details>
  <summary>2020-05-04</summary>
  - OpenCore 0.5.8 更新。所有驱动更新到最新版本。
  <br>
  - 继续精简 config.plist，OC 更新移除 ApfsDriverLoader.efi。
  <br>
  - 音频修复（貌似不会偶尔没声音了）。核显频率恢复正常。大小写灯恢复正常。
</details>

<details>
  <summary>2020-04-27</summary>
  - CPU 变频修复，通过重写 `DeviceProperties` 精简了 `config.plist`。
</details>

<details>
  <summary>2020-04-21</summary>
  - 在新的 Release 中添加了供安装使用的 EFI，仅改变了 `ShowPicker` 和 `Timeout` 的值，其他无变化。使用 Release v2.0 的朋友无需更新。
</details>

<details>
  <summary>2020-04-13</summary>
  - WiFi可以重新工作了，使用指南请看下方。
</details>

<details>
  <summary>2020-04-13</summary>
  - 使用WiFi的过程中出现问题，暂时不知道如何解决，请耐心等候一下。
</details>

<details>
  <summary>2020-04-13</summary>
  - 在重新构建ACPI目录并修改 Config.plist 之后，终于！！！可以使用英特尔WiFi了！！！
  <br>
  - 请使用 https://github.com/zxystd/itlwm 尽情网上冲浪！！！
</details>

<details>
  <summary>2020-04-11</summary>
  - 更新至 MacOS 10.15.4 19E287。更新 OpenCore 到官方Release 0.5.7 版本并完善了Config.plist的结构。
  <br>
  - 更新 Lilu, VirtualSMC, AppleALC, WhateverGreen, SMCBatteryManager, NVMeFix。
  <br>
  - 更新并定制了 IntelBluetoothFirmware，驱动文件大幅缩小。同时更新了 IntelBluetoothInjector。
</details>

<details>
  <summary>2020-03-31</summary>
  - 删除了SSDT-USBX并添加了USBPower.kext以实现更好的USB驱动方法。
</details>

<details>
  <summary>2020-03-28</summary>
  - 我发现更新到最新版本后，大小写灯已正常工作！
</details>

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

## BIOS 设置

| **System Configuration** |      |
| --- | --- |
| SATA Operation       | AHCI |
|                      |      |
| **Secure Bootxu**   |      |
| Secure Boot Enable   | Disabled（取消勾选） |
|  |                    |
| **Intel Software Guard Extensions** |                    |
| Intel SGX Enable | Disabled           |
|  |                    |
| **POST Behavior** |                    |
| Fastboot | Thorough           |
|  |                    |
| **Virtualization Support** |                    |
| VT for Direct I/O | Disabled（取消勾选） |

请更新 BIOS 至最新版本！

其他保持默认设置。

## 工作的部分

- macOS 11.0.1
- CPU（睿频4.0Ghz）
- 核芯显卡
- 有线网卡
- 音频（Layout=15）
- USB（定制USBPorts.kext）
- 触摸板
- 摄像头
- 蓝牙（带有蓝牙开关）
- Wi-Fi（使用 [AirportItlwm](http://bbs.pcbeta.com/viewthread-1848662-1-1.html)))

## 不工作的部分

- 独立显卡（已使用SSDT屏蔽）
- HDMI（直接连接到独立显卡）
- 内置读卡器
