# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-10.15.4-orange)](https://www.apple.com/macos/catalina/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.5.8-9cf)](https://github.com/acidanthera/OpenCorePkg)
[![license](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

<img align="right" src="https://support.apple.com/content/dam/edam/applecare/images/en_US/macos/psp-mini-hero-macos-high-sierra-whats-new_2x.png" alt="Critter" width="250">

[English](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/blob/master/README.md) | 中文

### 最新的Release：[v2.3](https://github.com/tonyleelyy/OpenCore-Hackintosh-Dell-G3-3579/releases/tag/v2.3)

**macOS版本：10.15.4 19E287**

**OpenCore版本：[0.5.8 Offical](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.5.8)**

本 OpenCore 黑苹果项目适配 i5-8300H，GTX1050，没有USB Type-C版本的Dell G3 3579。

> 我会尽可能迅速地更新这一项目，尽量保证适配最新版本的OpenCore和macOS系统。
>
> 尽管这个项目已经完全脱离了 [CerteKim](https://github.com/CerteKim) 的 [Dell-G3-3579-Hackintosh-OpenCore](https://github.com/CerteKim/Dell-G3-3579-Hackintosh-OpenCore) 项目，但我仍要感谢他。没有 CerteKim 的支持就不会有这个项目的诞生。

## 更新
- 2020-05-15：

  修复了触控板无法使用的问题。

- 2020-05-04:

  OpenCore 0.5.8 更新。所有驱动更新到最新版本。

  继续精简 config.plist，OC 更新移除 ApfsDriverLoader.efi。

  音频修复（貌似不会偶尔没声音了）。核显频率恢复正常。大小写灯恢复正常。

- 2020-04-27:

  CPU 变频修复，通过重写 `DeviceProperties` 精简了 `config.plist`。

- 2020-04-21：

  在新的 Release 中添加了供安装使用的 EFI，仅改变了 `ShowPicker` 和 `Timeout` 的值，其他无变化。使用 Release v2.0 的朋友无需更新。

- 2020-04-13：

  WiFi可以重新工作了，使用指南请看下方。

- 2020-04-13：

  使用WiFi的过程中出现问题，暂时不知道如何解决，请耐心等候一下。

- 2020-04-13：

  在重新构建ACPI目录并修改 Config.plist 之后，终于！！！可以使用英特尔WiFi了！！！

  请使用 https://github.com/zxystd/itlwm 尽情网上冲浪！！！

- 2020-04-11：

  更新至 MacOS 10.15.4 19E287。更新 OpenCore 到官方Release 0.5.7 版本并完善了Config.plist的结构。

  更新 Lilu, VirtualSMC, AppleALC, WhateverGreen, SMCBatteryManager, NVMeFix。

  更新并定制了 IntelBluetoothFirmware，驱动文件大幅缩小。同时更新了 IntelBluetoothInjector。

- 2020-03-31：删除了SSDT-USBX并添加了USBPower.kext以实现更好的USB驱动方法。

- 2020-03-28：我发现更新到最新版本后，大小写灯已正常工作！



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

其他保持默认设置。

## EFI.zip 和 EFI_Install.zip 的区别
 `EFI_Install.zip` 的 config.plist:

```
<key>ShowPicker</key>
<true/>

<key>Timeout</key>
<integer>10</integer>
```

 `EFI.zip` 的 config.plist:

```
<key>ShowPicker</key>
<false/>

<key>Timeout</key>
<integer>0</integer>
```


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

## WiFi使用指南

1. 在 App Store 下载 Xcode。

2. Clone [itlwm](https://github.com/zxystd/itlwm) 的 master 分支，解压缩。

3. 用 Xcode 打开 itlwm.xcodeproj。

4. 打开之后可能会看到一个黄色的“⚠️1”在界面的上面，点击它，"Update to recommded settings" - "Perform Changes"。

5. 点击左侧的文件夹按钮，找到 "mac80211.cpp" 点击进入。

6. 使用 Command + F 找到 "zxyssdt112233"。

7. 把 ssid_name = "" 的 ssdt 改成你的Wi-Fi名

   把 ssid_pwd = "" 的 zxyssdt112233 改成你的Wi-Fi密码

   Command + S 保存

8. 点击上面 "My Mac" 左边的小方块，选 "itlwm"。

9. 点击播放按钮 Build。

10. Build successful之后在左边找到 Products 文件夹，右键 "itlwm.kext"，"Show in Finder"。

11. 复制 "itlwm.kext" 到一个你熟悉的目录。

12. **关机！然后再开机选择OC启动，切记不要从Windows重启，否则无法使用。**

13. **先拔掉网线！（我也不知道为什么一定要这样才行）**

14. 用终端运行以下命令：（把下面的 "itlwm.kext" 改成文件的详细地址，如 "/Users/tony/Downloads/itlwm.kext"）

```
cp -R itlwm.kext /tmp
sudo chown -R root:wheel /tmp/*.kext
sudo kextutil /tmp/*.kext
```

14. 开始享受你的Wi-Fi吧！

驱动作者和版权：
https://github.com/zxystd/itlwm

## 不工作的部分

- 独立显卡（已使用SSDT屏蔽）
- HDMI（使用Optimus技术，直接连接到独立显卡，故无解）
- 内置读卡器
