# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-10.15.4-orange)](https://www.apple.com/macos/catalina/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.5.7-9cf)](https://github.com/williambj1/OpenCore-Factory/)
[![license](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

<img align="right" src="https://support.apple.com/content/dam/edam/applecare/images/en_US/macos/psp-mini-hero-macos-high-sierra-whats-new_2x.png" alt="Critter" width="250">

[English](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/blob/master/README.md) | 中文

### 最新的Release：[v1.1](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/releases/tag/v1.1)

**macOS版本：10.15.4**

**OpenCore版本：0.5.7**

来源: [CerteKim](https://github.com/CerteKim)的 [Dell-G3-3579-Hackintosh-OpenCore](https://github.com/CerteKim/Dell-G3-3579-Hackintosh-OpenCore) （万分感谢！）

我这一版本的EFI修改自CerteKim的OpenCore黑苹果项目。
我将它适配了我的i5-8300H，GTX1050，没有USB Type-C版本的Dell G3 3579。

> 我会尽可能迅速地更新这一项目，尽量保证适配最新版本的OpenCore和macOS系统。

## 更新
- 2020-03-31：删除了SSDT-USBX并添加了USBPower.kext以实现更好的USB驱动方法。
- 2020-03-28：我发现更新到最新版本后，大小写灯已正常工作！

## 待办事项
- 2020-03-29：正在尝试重建SSDT，看看能否修复音频和使得Windows在OpenCore进入可用。

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
| 无线网卡 |     Inte Wireless-AC 9462     |  仅蓝牙  |

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

## 问题

- 音频偶尔不驱动，重启解决。

## 不工作的部分

- 独立显卡（已使用SSDT屏蔽）
- HDMI（使用Optimus技术，直接连接到独立显卡，故无解）
- 内置读卡器
- Wi-Fi（有希望在[itlwm](https://github.com/zxystd/itlwm)得到适配)

## 安装前

修改Config.plist，找到

```
<key>ShowPicker</key>
<false/>
```

将值改成```true```
