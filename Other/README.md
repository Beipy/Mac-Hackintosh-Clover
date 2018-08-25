# 文件说明

- `ACPIBatteryManager.kext`电池驱动程序，用于实现电量显示，如遇五国卡`BAT0`之类的请删除
- `AppleALC.kext`和`VoodooHDA-2.9.1.kext`黑苹果万能声卡驱动任选其一
- `AppleBacklightInjector.kext`驱动笔记本背光
- `AppleIntelKBLGraphicsFramebufferInjector`核心显卡 ~~暂未知
- `AzulPatcher4600.kext`只适用于核心显卡`HD4600`，其他型号删除
- `VoodooPS2Controller.kext`和`ApplePS2SmartTouchPad.kext`键盘、鼠标、触摸板万能驱动，两者选其一，不可全用
- `ATH9KFixup.kext`用于驱动`AR946x`、`AR956X`、`AR9485`高通无线网卡，根据自己电脑配置选用
- `BrcmFirmwareData.kext`、`BrcmPatchRAM2.kext`蓝牙驱动
- `CodecCommander.kext`补丁解决系统睡眠唤醒后无声
- `CoreDisplayFixup.kext`用于破解`4K`支持，前提显卡要支持4k分辨率输出以及你的显示器也是4K分辨率才可用！1080分辨率不需要此文件
- `CPUFriend.kext`CPU变频动态注入 CPU 电源管理数据
- `FakePCIID`芯片驱动  ！功能未知
- `FakePCIID_Broadcom_WiFi.kext`针对博通无线网卡的FakePCIID驱动
- `FakePCIID_Intel_GbX.kext` Small Tree drivers for Intel chipset
- `FakePCIID_Intel_HD_Graphics.kext` Intel HD Graphic显卡的device-id的仿冒驱动，适用于HD4200/HD4400/HD4600/HD5600系列
- `FakePCIID_Intel_HDMI_Audio.kext` 四代核显HDMI音频驱动
- `FakePCIID_XHCIMux.kext` 老版本USB驱动
- `FakeSMC.kext` 仿冒苹果SMC设备的驱动文件，也是安装黑苹果必备驱动之一。就是欺骗苹果系统我们的设备是苹，通常来说PC是无法直接安装Mac系统的，
- `GenericUSBXHCI.kext` 通用的USB3.0驱动文件！
- `HibernationFixup.kext` 黑苹果睡眠驱动！当安装黑苹果或安装好了黑苹果系统都会测试睡眠功能，如果发现睡眠后无法唤醒、死机、黑屏，可使用此文件
- `IntelGraphicsDVMTFixup.kext` 主要作用于破解苹果的framebuffer kext的64MB值，如果你的电脑无法驱动黑苹果集成显卡可以下载试试，但是需要配置lilu.kext v1.2.2 和IntelGraphicsFixup.kext一起使用。用于五代以上机器，四代及以下删除
- `IntelGraphicsFixup.kext` 当给笔记本还是台式机的核心显卡安装黑苹果系统时，总会遇到黑屏或显卡完美驱动了，也有了水波纹，但是每次开机会闪屏、花屏等问题，或者当我们使用中会偶尔出现闪屏，这时候我们就需要使用
-  `Lilu.kext` Lilu.kext扩展库
-  `NoTouchID.kext`解决macOS High Sierra 10.13.4 中13.3和14.3机型出现的Touch ID卡顿密码的现象，需配合lilu补丁驱动使用。
-  `NvidiaGraphicsFixup.kext`黑苹果显卡驱动 解决Nvidia黑屏 卡顿
-  `SATA-100-series-unsupported.kext`，`SATA-200-series-unsupported.kext`  暂未测试
-  `Shiki.kext`有时候系统会卡顿，或者当我们打开iTunes后报错闪退，这时候我们就需要使用Shiki.kext驱动来帮组我们解决这个现象。
-  `SmallTree-Intel-211-AT-PCIe-GBE.kext`华硕Prime X299 Deluxe的英特尔I211_AT千兆板载网卡所需要
-  `SmallTreeIntel8254x.kext`，`SmallTreeIntel8259x.kext`，`SmallTreeIntel82576.kext`未做测试
-  `USBInjectAll.kext`安装黑苹果系统时经常遇到的最常见的问题，将USB设备插入USB3.0或者USB3.1不识别，这时候我们就需要使用。此次更新支持了最新300系列主板。
- `XHCI`开头的三个`kext`对应适用于`x99`、`200`和`300`系主板，非此类主板删除
- `WhateverGreen.kext`已经更新，合并了`igfx`、`ngfx`，以及`Shiki`，启动参数和以前一样，不论`A`卡、`N`卡还是`Intel`核心显卡，都建议使用


- `RTL8100.kext`、`RTL8111.kext`、`IntelMausiEthernet.kext`、`AppleIGB`、`AppleIntelE1000e.kext`、`SmallTree-Intel-211-AT-PCIe-GBE.kext`、`ALXEthernet.kext`、`AtherosE2200Ethernet.kext`分别对应不同的网卡合理选用

    > 对应关系如下
    
    | RTL8100.kext | RTL8107E、RTL810X、RTL8139 |
    | --- | --- |
    | RTL8111.kext | Realtek RTL8111/8168 B/C/D/E/F/G/H |
    | IntelMausiEthernet.kext | 82578LM、82578LC、82578DM、82578DC、82579LM、82579V、I217LM、I217V、I218LM、I218V、I218LM2、I218V2、I218LM3、I219V、I219LM、I219V2、I219LM2、I219LM2  |
    | AtherosE2200Ethernet.kext | AR816x、AR817x、Killer E220x、Killer E2400、Killer E2500  |
    |SmallTree-Intel-211-AT-PCIe-GBE.kext  |  Intel I211|
    | AppleIntelE1000.kext | Intel系列 82540, 82541, 82542, 82543, 82544, 82545, 82546, 82547, 82578 (P55/H55)  82579 (P67/H67) 82574L 82571 82572 82573 82574 82583 I217V |
    | AppleIGB.kext | Intel 82575, 82576, 82580, dh89xxcc, i350, i210 and i211 |
    | ALXEthernet.kext | Atheros alx Ethernet |
    | FakePCIID_BCM57XX_as_BCM57765.kext | BCM57XX |
    | FakePCIID_Intel_GbX.kext | Small Tree drivers for Intel chipset |
    
----

- `FakePCIID_BCM57XX_as_BCM57765.kext`详细支持列表
  - Broadcom NetXtreme BCM5700 Gigabit Ethernet [14e4:1644]
  - Broadcom NetXtreme BCM5701 Gigabit Ethernet PCIe [14e4:1645]
  - Broadcom NetXtreme BCM5702 Gigabit Ethernet PCIe [14e4:1646]
  - Broadcom NetXtreme BCM5703 Gigabit Ethernet PCIe [14e4:1647]
  - Broadcom NetXtreme BCM5717 Gigabit Ethernet PCIe [14e4:1655]
  - Broadcom NetXtreme BCM5717 Gigabit Ethernet PCIe [14e4:1665]
  - Broadcom NetXtreme BCM5718 Gigabit Ethernet PCIe [14e4:1656]
  - Broadcom NetXtreme BCM5719 Gigabit Ethernet PCIe [14e4:1657]
  - Broadcom NetXtreme BCM5725 Gigabit Ethernet PCIe [14e4:1643]
  - Broadcom NetXtreme BCM5727 Gigabit Ethernet PCIe [14e4:16f3]
  - Broadcom NetXtreme BCM5761 10/100/1000BASE-T Ethernet [14e4:1688]
  - Broadcom NetXtreme BCM5762 Gigabit Ethernet PCIe [14e4:1687]
  - Broadcom NetXtreme BCM57760 Gigabit Ethernet PCIe [14e4:1690]
  - Broadcom NetXtreme BCM57764 Gigabit Ethernet PCIe [14e4:1642]
  - Broadcom NetXtreme BCM57767 Gigabit Ethernet PCIe [14e4:1683]
  - Broadcom NetLink BCM57781 Gigabit Ethernet PCIe [14e4:16b1]
  - Broadcom NetXtreme BCM57782 Gigabit Ethernet PCIe [14e4:16b7]
  - Broadcom NetLink BCM57785 Gigabit Ethernet PCIe [14e4:16b5] -- Confirmed
  - Broadcom NetXtreme BCM57786 Gigabit Ethernet PCIe [14e4:16b3] -- Confirmed
  - Broadcom NetXtreme BCM57787 Gigabit Ethernet PCIe [14e4:1641]
  - Broadcom NetLink BCM57788 Gigabit Ethernet PCIe [14e4:1691]
  - Broadcom NetLink BCM57790 Gigabit Ethernet PCIe [14e4:1694]
  - Broadcom NetLink BCM57791 Gigabit Ethernet PCIe [14e4:16b2]
  - Broadcom NetLink BCM57795 Gigabit Ethernet PCIe [14e4:16b6]
  - Broadcom NetLink BCM5785 Gigabit Ethernet [14e4:1699]
  - Broadcom NetLink BCM5785 Fast Ethernet [14e4:16a0]
  - Broadcom NetLink BCM5787M Gigabit Ethernet PCI Express [14e4:1693]
  - Broadcom Network Adapter [14e4:1689]

----

- `FakePCIID_Intel_GbX.kext`详细支持列表
  - Supported devices for SmallTreeIntel8254x.kext:
  - 8086:1010 82546EB Gigabit Ethernet Controller (Copper)
  - 8086:1011 82545EM Gigabit Ethernet Controller (Fiber)
  - 8086:1012 82546EB Gigabit Ethernet Controller (Fiber)
  - 8086:101d 82546EB Gigabit Ethernet Controller
  - 8086:1026 82545GM Gigabit Ethernet Controller
  - 8086:1027 82545GM Gigabit Ethernet Controller
  - 8086:1028 82545GM Gigabit Ethernet Controller
  - 8086:105e 82571EB Gigabit Ethernet Controller (Also covered by AppleIntel8254XEthernet.kext)
  - 8086:105f 82571EB Gigabit Ethernet Controller
  - 8086:1079 82546GB Gigabit Ethernet Controller
  - 8086:107a 82546GB Gigabit Ethernet Controller
  - 8086:107b 82546GB Gigabit Ethernet Controller
  - 8086:107c 82541PI Gigabit Ethernet Controller
  - 8086:107d 82572EI Gigabit Ethernet Controller (Copper)
  - 8086:107e 82572EI Gigabit Ethernet Controller (Fiber)
  - 8086:10a4 82571EB Gigabit Ethernet Controller
  - 8086:10b5 82546GB Gigabit Ethernet Controller (Copper)
  - 8086:10b9 82572EI Gigabit Ethernet Controller (Copper)
  - 8086:10bc 82571EB Gigabit Ethernet Controller (Copper)

  - SmallTreeIntel82576.kext:
  - 8086:1521 I350 Gigabit Network Connection
  - 8086:1522 I350 Gigabit Fiber Network Connection
  - 8086:1533 I210 Gigabit Network Connection (Also covered by AppleIntelI210Ethernet.kext)

  - SmallTreeIntel8259x.kext:
  - 8086:10c6 82598EB 10-Gigabit AF Dual Port Network Connection
  - 8086:10c7 82598EB 10-Gigabit AF Network Connection
  - 8086:10c8 82598EB 10-Gigabit AT Network Connection
  - 8086:10ec 82598EB 10-Gigabit AT CX4 Network Connection
  - 8086:10d8 82599EB 10 Gigabit Network Connection
  - 8086:10fb 82599ES 10-Gigabit SFI/SFP+ Network Connection
  - 8086:10f1 82598EB 10-Gigabit AF Dual Port Network Connection
  - 8086:151c 82599 10 Gigabit TN Network Connection
  - 8086:150b 82598EB 10-Gigabit AT2 Server Adapter
  - 8086:1528 Ethernet Controller 10-Gigabit X540-AT2
  - 8086:10fc 82599 10 Gigabit Dual Port Network Connection
  - 8086:1560 Ethernet Controller X540
