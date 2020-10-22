## 都是通用内核扩展 
> 本人使用自定义 USB 端口，当前目录不包含该文件，请自行配置。

## 关于 AppleALC

自己编译的版本并已提交 Pr
https://github.com/acidanthera/AppleALC/pull/611

> 编译版本说明：Lilu 1.4.8 + AppleALC 1.5.3，layout-id 66
  + 支持喇叭和耳机自动切换
  + 前后麦克风使用正常

## 关于 AppleAHCIPort

+ Due to Apple dropping the AppleIntelPchSeriesAHCI class in AppleAHCIPort.kext
+ To resolve, add Catalina's patched AppleAHCIPort.kext with the MinKernel set to 20.0.0

## 关于 XHCI-unsupported

+ Because XHCI-unsupported.kext uses a lower IOProbeScore than the native Info.plist, there is no harm in installing it even if native support exists.
+ Typical xHCI needing XHCI-unsupported.kext:
  + X99-series chipset XHC controller, 8086:8d31 200-series chipset XHC controller, 8086:a2af (depends on macOS version) 300-series chipset XHC controller, 8086:a36d or 8086:9ded
