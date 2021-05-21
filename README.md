# 微星 MAG B460M MORTAR WIFI OpenCore EFI

## 介绍

- 可用于引导~~Bug~~Big Sur 11.3.1
- OpenCore 版本:0.6.9
  - 声卡设备地址为`PciRoot(0x0)/Pci(0x1F,0x3)`
  - USB controller 为`0xA3AF`，因此`USBInjectAll.kext`和`XHCI-unsupported.kext`也需要修改
  - `USBInjectAll.kext`需要添加`iMac20,2`
  - 以上`USBInjectAll.kext` 以及 `XHCI-unsupported.kext` 可以在[Modified Kexts](./Modified%20Kexts)中找到

### 正常工作

- [x] 板载声卡
- [x] 板载网卡
- [x] 核显硬解
- [x] Airdrop / Handoff / Sidecar
- [x] 睡眠 / 唤醒
- [x] USB2.0 / USB 3.0
- [x] DRM

### 待解决问题

- [ ] 暂无，若有可在 issue 提出

## 我的配置

|    硬件    |           型号            |
| :--------: | :-----------------------: |
|    主板    | MSI MAG B460M MORTAR WIFI |
|    CPU     |     QTB1(i9 10900 ES)     |
|    内存    |    棘蛇 DDR4 2666 16G     |
|    硬盘    |      西数 SN720 500G      |
| 蓝牙及无线 |  BCM94360CD(FENVI-T919)   |

## Tips

- 请自行修改 config.plist 中的`MLB`, `SystemSerialNumber`以及`SystemUUID`(型号为 iMac20,2)
- USB 已经进行定制，如果 USB 端口与本主板不一致可以使用 repo 中的[`USBInjectAll.kext`](./Modified%20Kexts/USBInjectAll.kext)再自己进行定制
- 无线网卡使用的是 PCIE，主板自带的 AX200 所占用的 USB(HS04) 已被[`USBPorts.kext`](./EFI/OC/Kexts/USBPorts.kext)禁用，否则免驱卡的蓝牙会无法使用

## 鸣谢

[Dortania's OpenCore Install Guide](https://dortania.github.io/getting-started/)
