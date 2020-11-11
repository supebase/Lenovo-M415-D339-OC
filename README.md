## 声明：我所使用主板 BIOS 已经更新至最新版本，并解锁 `CFG Lock`

* 如果你的主板未解锁 `CFG Lock` 请将配置文件中 `AppleCpuPmCfgLock`、`AppleXcpmCfgLock` 和 `IgnoreInvalidFlexRatio` 设置为 `True`
* 如果你不是 SATA3 固态硬盘，请将 `ThirdPartyDrives` 设置为 `False`
* 如果你没有自定义 USB 设备，请将 `XhciPortLimit` 设置为 `True` 并将 USBMap.kext Enabled 部分设置为 `False`

### 电脑型号：联想启天 Lenovo M415-D339

> **OpenCore 版本：0.6.3**

### 硬件列表：

* 主板 [ib250mh](https://www.baidu.com/s?ie=utf-8&f=8&rsv_bp=1&rsv_idx=1&tn=baidu&wd=ib250mh%E4%B8%BB%E6%9D%BF&fenlei=256&rsv_pq=c93518ed0000074d&rsv_t=9de5tGB5cxBe0Lqtgj9grCvfTMTGMF4cRHg%2F7QkovWpOKDaL3UaMzMvYqsM&rqlang=cn&rsv_enter=1&rsv_dl=ib&rsv_sug3=5&rsv_sug1=5&rsv_sug7=100&sug=ib250mh%25E4%25B8%25BB%25E6%259D%25BF&rsv_n=1)
* CPU Intel i7 7700
* 内存 8G 2666 * 2
* 显卡 蓝宝石 Readon RX 560（已自行更换，自带显卡 GT 710/730 也是免驱卡）
* 声卡 Realtek ALC 662（已定制并整合至官方最新版本，layout-id 66）
* 网卡 Realtek RTL8111

+ 以下设备非该电脑型号原装，需自行购买：
  + 无线蓝牙 BCM43602 (14E4:43BA) 
  + 硬盘 SanDisk Plus 120G

### 配置文件需要自行添加或修改部分：

* MLB
* SystemSerialNumber
* SystemUUID

三码可以通过 [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) 生成
> 注意：验证序列号必须是无效的或未使用的才可以用哦，千万别用能查到信息的序列号！

* ROM 值为网卡 MAC 地址（不要复制字符之间的 : 符号）

**机型很重要，机型很重要，机型很重要。**

> ACPI 部分请看目录里的说明。Kexts 部分请看目录里的说明。Drivers 通常只需要 HfsPlus.efi 和 OpenRuntime.efi
