## 说明：机型是关键，我的电脑硬件类似 2017 款 iMac（18,2）所以不需要太多修改。主板 BIOS 已经更新至最新版本，并解锁 `CFG Lock`

* 如果你的主板未解锁 `CFG Lock` 请将配置文件中 Kernel -> Quirks `AppleCpuPmCfgLock`、`AppleXcpmCfgLock` 和 UEFI -> Quirks `IgnoreInvalidFlexRatio` 设置为 `True`
* 如果你不是 SATA3 固态硬盘，请将 Kernel -> Quirks `ThirdPartyDrives` 设置为 `False`
* 如果你没有自定义 USB 设备，请将 Kernel -> Quirks `XhciPortLimit` 设置为 `True` 并将 Kernel 中 USBMap.kext Enabled 部分设置为 `False`

> 解锁 CFG Lock 有很多好处，如果主板不支持操作或不想用 BIOS 工具解锁，可以使用 OpenCore Tools 中的 ControlMsrE2.efi 来解锁（参数 unlock）

![截屏2021-11-03 16 08 12](https://user-images.githubusercontent.com/62989049/140026732-197241b9-6a8e-4c39-a308-1f552aac42d0.png)

### 电脑型号：联想启天 Lenovo M415-D339

> **OpenCore 版本：0.7.5**

### 硬件列表：

* 主板 [ib250mh](https://www.baidu.com/s?ie=utf-8&f=8&rsv_bp=1&rsv_idx=1&tn=baidu&wd=ib250mh%E4%B8%BB%E6%9D%BF&fenlei=256&rsv_pq=c93518ed0000074d&rsv_t=9de5tGB5cxBe0Lqtgj9grCvfTMTGMF4cRHg%2F7QkovWpOKDaL3UaMzMvYqsM&rqlang=cn&rsv_enter=1&rsv_dl=ib&rsv_sug3=5&rsv_sug1=5&rsv_sug7=100&sug=ib250mh%25E4%25B8%25BB%25E6%259D%25BF&rsv_n=1)
* CPU Intel i7 7700
* 内存 8G 2666 * 2
* 显卡 蓝宝石 Readon RX 560 4G OC（已自行更换，自带显卡 GT 710/730 也是免驱卡）
* 声卡 Realtek ALC 662（已定制并整合至官方最新版本，layout-id 66）
* 网卡 Realtek RTL8111

> 无线蓝牙、固态等其他硬件需要自行购买。

### 配置文件已更新

* 单硬盘 macOS 配置文件（Config.plist）
* 双硬盘 macOS + Windows 10 配置文件（Config-BootCamp.plist）

> BootCamp 说明：必须已经安装 macOS 系统，另一块硬盘安装 Windows 10 系统。BootCamp 需要在转换助理菜单中自行下载。注意检查（WinPE 中的工具）双系统的启动配置是否正确（应该由 OC 引导）。好处：不用担心时间同步，随时切换系统。

### 配置文件需要自行添加或修改部分：

* MLB
* SystemSerialNumber
* SystemUUID

三码可以通过 [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) 或 Hackintool 生成，一定要验证序列号。
> 注意：验证序列号必须是无效的（推荐）或未使用的（不推荐）才可以用哦，千万别用能查到信息的序列号！

* ROM 值为网卡 MAC 地址（不要复制字符之间的 : 符号）

**机型很重要，机型很重要，机型很重要。**

> ACPI 部分请看目录里的说明。Kexts 部分请看目录里的说明。Drivers 通常只需要 HfsPlus.efi 和 OpenRuntime.efi
