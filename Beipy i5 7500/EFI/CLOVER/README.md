## 文件说明


必有|文件名称|作用
:----|:-----:|-----:
true | config.plist | clover配置文件
true | ACPI | 存放DSDT.aml/SSDT.aml
false | doc | clover的帮助文档
false |drivers-Off| 个人备份文件
false | drivers32 | 使用传统模式加载32位clover.efi所需的驱动（需验证）
false|drivers32UEFI| 使用传统模式加载32位clover.efi在模拟uefi环境下所需的驱动
true|drivers64|使用传统模式加载64位clover.efi所需的驱动（需验证）
true|drivers64UFI|使用传统模式加载64位clover.efi在模拟uefi环境下所需的驱动
true|kexts|使用kexts注入时，kext的存放位置
false|misc|使用clover环境下的截图，提取dsdt.aml/ssdt.aml的存放位置
false|OEM|分文件夹存放ACPI,config.plist等信息,及加载,实现单个U盘引导多个黑果平台
false|ROM|显卡rom存放位置
true|themes|clover主题存放位置
true|tools|EFI Shell存放位置,放置用于进入shell环境的.efi，不可用于引导OSX，但可运行一些.efi程序


## Clover快捷键

```
都写到这里了，一块都写出来吧以备不时之需！
```

| 快捷键 | 功能 |
:----|:-----:|-----:
|Esc|退出子菜单或刷新主菜单|
|F1|显示帮助信息|
|F2|保存preboot.log日志文件到/EFI/misc|
|F4|保存原始DSDT到/EFI/ACPI/origin|
|F5|保存初步修复的DSDT到/EFI/ACPI/origin|
|F6|保存显卡Bios文件到/EFI/misc|
|F10|保存屏幕截图到/EFI/misc|   
|F12|推出选中的（DVD）宗卷|
|空格键|显示选定项的,子菜单项,的详细信息|
|数字1-9|菜单快捷键|
|A|关于菜单|
|O|选项菜单|
|R|重启|
|U|关机|


##启动顺序

bios引导：

* BIOS->boot0->boot1->BOOT->CLOVERIA32.efi->Apple's boot.efi->mach_kernel
* BIOS->boot0->boot1->BOOT->CLOVERX64.efi->Apple's boot.efi->mach_kernel
* UEFI BOOT：
* UEFI BIOS->CLOVERX64.efi->Apple's boot.efi->mach_kernel

