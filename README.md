# OpenCore EFI for AMD Ryzen Hackintosh

## Specification

| **Component**  | **Model**                           |
| -------------- | ----------------------------------- |
| CPU            | AMD Ryzen 5 3500x @ 3.6GHz          |
| Motherboard    | ASUS B450M Steel Legend             |
| RAM            | 32GB (2 x 16GB) Ballistix @ 2666MHz |
| Audio Chipset  | Realtek ALC892                      |
| GPU            | AsRock RX 5500XT Challenger         |
| Network Card   | Fenvi T919                          |
| OS Disk (NVMe) | Samsung 970 EVO Plus 1TB            |

**macOS version**: 15.4.1 (24E263)
**OpenCore version**: 1.0.4

## Drivers & Kexts

- [[Bootloader] OpenCore](https://github.com/acidanthera/OpenCorePkg)
- [[Patch] AMD_Vanilla](https://github.com/AMD-OSX/AMD_Vanilla)
- [[Driver] OpenRuntime](https://github.com/acidanthera/OpenCorePkg)
- [[Driver] OpenCanopy](https://github.com/acidanthera/OpenCorePkg)
- [[Driver] HFSPlus](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi)
- [[Kext] Lilu](https://github.com/acidanthera/Lilu)
- [[Kext] VirtualSMC](https://github.com/acidanthera/VirtualSMC)
- [[Kext] WhateverGreen](https://github.com/acidanthera/WhateverGreen)
- [[Kext] AppleALC](https://github.com/acidanthera/AppleALC)
- [[Kext] RealtekRTL8111](https://bitbucket.org/RehabMan/os-x-realtek-network/downloads/)

## Not working

- Hypervisor.framework (VirtualBox and XCode iOS emulator works)

## How to use

1. Create directory "EFI" in your EFI partition (e.g. pendrive or hard drive)
2. Clone this repo and paste directiories "BOOT" and "OC" onto created directory
3. Download [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) to generate unique SMBIOS information. Run it and select **Generate SMBIOS**, as model select **iMacPro1,1**.
4. Open config.plist with [**ProperTree**](https://github.com/corpnewt/ProperTree) and go to PlatformInfo > Generic. Set MLB (Board Serial), SystemSerialNumber (Serial) and SystemUUID (SmUUID) to generated values.
5. Make USB installer with [**this guide**](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/)
6. Boot it!

**You CAN NOT use SMBIOS from this repository, it MUST be unique for every macOS installation**

## References

- OpenCore Desktop Guide: [**here**](https://dortania.github.io/OpenCore-Install-Guide/)
