## 建议自定义 USB 
> 本人使用自定义 USB 端口，当前目录不包含该文件，请自行配置。

## 常用内核扩展

在配置文件中可以看到使用了哪些内核扩展，请在 https://github.com/acidanthera 或 https://github.com/headkaze/Hackintool 中下载最新版本。

## 关于 AppleALC

自己编译的内容已经整合到官方最新版本，layout-id 66
  + 支持喇叭和耳机自动切换
  + 前后麦克风使用正常

## 关于 AppleAHCIPort

+ Due to Apple dropping the AppleIntelPchSeriesAHCI class in AppleAHCIPort.kext
+ To resolve, add Catalina's patched AppleAHCIPort.kext with the MinKernel set to 20.0.0

## 关于 XHCI-unsupported

+ Because XHCI-unsupported.kext uses a lower IOProbeScore than the native Info.plist, there is no harm in installing it even if native support exists.
+ Typical xHCI needing XHCI-unsupported.kext:
  + X99-series chipset XHC controller, 8086:8d31 200-series chipset XHC controller, 8086:a2af (depends on macOS version) 300-series chipset XHC controller, 8086:a36d or 8086:9ded
