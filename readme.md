# Hackintosh Opencore MAG MSI B550 TOMAHAWK

**OpenCore : 1.0.1**

**macOS ： 15.0 (24A335)**

**SMBIOS : MacPro7,1**

### Specification

| **Component**    | **Model**                  |
| ---------------- | -------------------------- |
| CPU              | RYZEN R5 5600X             |
| Motherboard      | MAG MSI B550 TOMAHAWK      |
| RAM              | 32GB(16G×2) DDR4 3600 C18  |
| GPU              | POWER COLOR RED DEVIL 6900XT   |
| WiFi & Bluetooth | BROADCOM BCM4360 (M.2 via PCIEX1 adapter)  |
| MAC OS Disk(sata)    | SAMSUNG 860 EVO 512GB      |
| WINDOW Disk(NVME)    | SAMSUNG PM9A1 512GB    |

please use [OpenCore Configurator](https://mackie100projects.altervista.org/opencore-configurator/) or  [OC Auxiliary](https://github.com/ic005k/QtOpenCoreConfig)  or  [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)  to generate yourself SMBIOS

### BIOS
My bios version is **[7C91vAC](https://download.msi.com/bos_exe/mb/7C91vAC.zip)**, With this bios you just need to disable secure boot. 

Bios after `7C91vAC` that link `above 4G Decoding` and `Re-size BAR Support`, then I don't want to use it.

| **Option**            | **Status**           |
| --------------------- | -------------------- |
| SATA Mode             | AHCI                 |
| Above 4G Decoding     | Enabled				|
| EHCI/XHCI Hand-off    | Enabled              |
| SVM                   | Enabled              |
| CSM                   | Disabled             |
| Secure Boot           | Disabled             |
| Serial Port           | Disabled             |
| Parallel Port         | Disabled             |
| IOMMU         		| Disabled             |

### Guide to follow:
**[Ryzen-Hackintosh](https://github.com/mikigal/ryzen-hackintosh)**
and 
**[Dortania Guide for ZEN](https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html)**

There 2 config files, one for usb installer and one for EFI partition of MacOS disk when everything is done.
both have `AMD Kernel Patch`, `PAT Patch` use Shaneee's Patch, `USB FIX`,  
### Working:
- Just install successful.
- Use Shaneee's Patch to increase RX 6900XT performace.\
- Fix monitor wake after sleep.
- Fix USB.
- Fix Broadcom Wifi. Other things is not check yet.
### Issue:
I face boot loop issue when installer going to phase 2 or phase 3: after the "29 minutes remaining" is done.
This because of `SecureBootModel` is setting to `Default`, To fix this set it to `Disabled` and `reset NVRAM` at least `twice` and MacOs Installer will continue.
If not, try to run Installer from begining: choose "Install MacOS xxx" instead of "MacOs Installer" in picker.


## Credits
- [Apple](https://apple.com) for macOS
- [Acidanthera](https://github.com/acidanthera) for OpenCore and most of used kexts
- [Dortania](https://github.com/dortania) for OpenCore configuration guides
- [ybakiame](https://github.com/ybakiame/Ryzen-Hackintosh-OpenCore-MSI-B550M-MORTAR-WIFI) for bios version and `npci=0x3000`
- [mikigal](https://github.com/mikigal/ryzen-hackintosh) for good guide of AMD
- [AMD-OSX Developers](https://github.com/AMD-OSX) for kernel patches for AMD CPUs
- [EliteMacx86](https://elitemacx86.com/) for [Broadcom wifi fix topic](https://elitemacx86.com/threads/how-to-fix-broadcom-wifi-on-macos-sonoma-and-later.1415/)
- [AMD-OSX Community](https://amd-osx.com) for a lot topic that I can follow