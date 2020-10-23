## 声明：本人使用的主板 BIOS 已经更新到最新版本，并解锁 CFG Lock

* 注意：如果未解锁 CFG Lock 的主板，请将配置文件中 `AppleCpuPmCfgLock` 和 `AppleXcpmCfgLock` 设置为 `True`

### 电脑型号：联想 Lenovo 启天 M415-D339

> OpenCore 版本：0.6.2

### 硬件列表：

* 主板 同上型号，请自行拆机查看。
* CPU Intel i7 7700
* 内存 8G 2666 * 2
* 显卡 蓝宝石 Readon RX 560 (本人已自行更换，自带显卡 GT 730 是免驱卡)
* 声卡 Realtek ALC 662（已定制并提交 pr，layout-id 66）
* 网卡 Realtek RTL8111

+ 以下设备非该电脑型号原装，需自行购买：
  + 无线蓝牙 BCM43602 (05AC:8290) 
  + 硬盘 SanDisk Plus 120G

### 配置文件需要自行添加或修改部分：

* MLB
* SystemSerialNumber
* SystemUUID

三码可以工具生成：https://github.com/corpnewt/GenSMBIOS
> 注意：验证序列号必须是无效的或未使用的才可以用哦，千万别用能查到信息的序列号！

* ROM 值为网卡 MAC 地址（不要复制 : 符号）

**机型很重要，机型很重要，机型很重要。**

> 配置文件中包含了 4 项 ACPI Delete 列表，都是和 Windows 相关的，如果你是双系统，请删除。

> 关于 **SIP** 问题（推荐操作）：建议将 `csr-active-config` 键值删除，不要写入 **NVRAM** 中。因为系统默认是 Enable 状态，如果想禁用 SIP，请在 Recovery 的终端输入 `csrutil disable` 命令（恢复命令 `csrutil enable`）。注意：配置文件中 csr-active-config 已经移除，如果有问题请自行添加。

> ACPI 部分请看目录里的说明。Kexts 部分请看目录里的说明。Drivers 通常只需要 HfsPlus.efi 和 OpenRuntime.efi
