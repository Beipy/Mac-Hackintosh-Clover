
# XPS9550-Catalina

最新适配版本10.15.4！

感谢整理的Clover引导文件，  [wmchris](https://github.com/wmchris/DellXPS15-9550-OSX)

使用引导文件安装完成后，如发现，触摸板不能完美使用，请升级VoodooI2C.kext

如发现声卡不能完美驱动，或者插入耳机后，破音，使用[ComboJack](https://github.com/hackintosh-stuff/ComboJack)进行打补丁修复声卡问题。

文件夹有ComboJack-master文件。


### 配置:

* CPU:i7-6700HQ
* 内存:8GB DDR4 2400 *2
* 显卡:HD530 + GTX960m（然并卵）
* 屏幕:1080P
* 网卡:DW1830
* 硬盘:960PRO 512GB

### 分区:

Win10和macOS双系统:

* macOS:100GB APFS
* Win10:100GB NTFS
* 资料盘:300+GB exFAT

### 版本:

| | | |
|:----:|:----:|----|
|系统|macOS|10.15.4|
| | |19C76|
|引导|CLOVER|5107|
|Kext|AirportBrcmFixup|2.0.6|
| |AppleALC|1.4.7|
| |BT4LEContinuityFixup|1.1.4|
| |BrcmPatchRAM|2.5.1|
| |CPUFriend|1.2.0|
| |FakePCIID|1.3.15|
| |HibernationFixup|1.3.2|
| |Lilu|1.4.2|
| |NoTouchID|1.0.3|
| |VirtualSMC|1.1.1|
| |VoodooI2C|2.2|
| |VoodooPS2Controller|2.1.2|
| |WhateverGreen|1.3.7|
| | | |

### 备注:

**VoodooI2C 2.3版本有BUG，与变频控制SSDT-TPDX有冲突，睡眠后驱动奔溃，[对应issue](https://github.com/alexandred/VoodooI2C/issues/231)**

**Caps Lock 的大写锁定指示灯不会常亮，只会在按下时亮，认为是DSDT之类的问题，但是我不知道怎么修复**
雷电3接口似乎可以用，但是没有设备测试，接手机可以热拔插
耳机孔用的是[ComboJack](https://github.com/hackintosh-stuff/ComboJack)方案
支持10.15的小版本更新（目前）
Other中的icm文件是用DisplayCAL和Spyder5校准的4K色彩文件，macOS下放到`~/Library/ColorSync/Profiles/`目录下即可在显示器设置中使用
 “关于本机” 机型名称在`/User/%用户名%/Library/Preferences/com.apple.SystemProfiler.plist`文件中修改

***

### 不同版本修改:

1080P版本，修改config.plist
Clover Configcurator中：
**启动背景 -> UI比例** 2改为1
文本编辑器：
`<key>UIScale</key><integer>2</integer>` 2改为1

i5版本，（方法来自wmchris的教程，我自己没有i5）修改config.plist
Clover Configcurator中：
**显卡设置 -> ig-platform-id** 0x191b0000改为0x19160000 ；
**设备设置 -> 属性 -> 设备 -> PciRoot(0x0)/Pci(0x2,0x0) -> AAPL,ig-platform-id** 00001B19改为00001619
文本编辑器：
`<key>ig-platform-id</key><string>0x191b0000</string>` 0x191b0000改为0x19160000 ；
`<key>AAPL,ig-platform-id</key><data>AAAbGQ==</data>` AAAbGQ==改为AAAWGQ==