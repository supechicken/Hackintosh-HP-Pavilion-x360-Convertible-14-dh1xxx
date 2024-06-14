# [SUCCESS] HP Pavilion x360 Convertible 14-dh1xxx

> [!NOTE]
> This repository is forked from [Avtera/Hackintosh-HP-Pavilion-x360-Convertible-14-dh1xxx](https://github.com/Avtera/Hackintosh-HP-Pavilion-x360-Convertible-14-dh1xxx), with brightness key patch and updated OC/kext for Sonoma
>
> Thanks a lot to [Avtera](https://github.com/Avtera) for the EFI work :)

> [!IMPORTANT]
> This EFI is tested on macOS Sonoma (14.4)
>
> Be aware that the MLB/Serial/AppleROM field in `config.plist` is blank, you need to fill it yourself (you can generate one with `macserial.py`)

## Specifications
| Type        | Hardware Model                                     | Status |
| :---        | :---                                               | :---: |
| **CPU**         | Intel Core i5-10210U, QuadCore 3.5 GHz, Comet Lake | ✅ |
| **Memory**      | Kingston SK Hynix/Nanya 2x8 GB DDR4-2666           | ✅ |
| **iGPU**        | Intel® UHD Graphics 630 (CML-GT2) (1.5 GB)         | ✅ |
| **eGPU**        | AMD Radeon RX570 4GB (connected via M.2 NVMe slot) | ✅ |
| **Disk**        | Samsung 870 EVO (500 GB, with Intel RST on)        | ✅ |
| **Keyboard**    | Standard PS/2 Keyboard (brightness key works!)     | ✅ |
| **Touchpad**    | Synaptics `(Hardware Id: SYNA328B)`                | ✅ |
| **Touchscreen** | ELAN `(Hardware Id: ELAN2514)`                     | ✅ |
| **Webcam**      | HP Wide Vision HD Camera                           | ✅ |
| **Battery**     | 333-1C-3B-A HT03041XL                              | ✅ |
| **Audio**       | Realtek ALC295 `Don't update the AppleALC.kext!`   | ✅ |
| **WiFi/BT**     | Intel AX201 160MHz CNVio2 (NOT preinstalled)       | ✅ |
| **Fingerprint** | Synaptics WBDI Fingerprint Reader                  | ❌ |
| **dGPU**        | ~~NVIDIA GeForce MX130 (GM108)~~ (my variant doesn't have dGPU) | ❌ |

## BIOS Settings
| Option              | Status                     |
| :---                | :---                       |
| Secure Boot         | Disabled                   |
| Intel SGX           | S/W Controlled or Disabled |

*No other bios option needs to be changed unless you want to*

## Tutorial? at this point do u still need a tutorial? jk!
Just download this repo and copy paste the EFI folder to your EFI partition. 
Dont forget to add a compatible SMBIOS inside the config.plist before booting, [you can follow this guide](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#platforminfo).

## Some hacky tricks (not really lol)
### 1. Issues with Touchpad and Touchscreen
- Solution 1: Sometimes the touchpad (TPD0) is detected on IOReg but its not working, how to fix that? idk lol 🤡. To circumvent this error, restart macOS to windows (with windows bootloader), restart 1x in windows to windows (make sure the touchpad is working), then reboot to OpenCore and select the macOS, if the touchpad still disabled try restart 1x in macOS to macOS. Good luck!
- Solution 2: Add VoodooI2CELAN.kext and remove the VoodooRMI.kext then Snapshot the config.plist. This method will disable the touchscreen and let the touchpad work flawlessly without any disruption.
### 2. Internet
A laptop without working WiFi and no Ethernet port included is REAL PAINFUL 💩, the solution is Android USB Tethering (HoRNDIS 9.2 kext), Native iPhone USB Tethering, or use an USB Wi-Fi (chris1111 driver).
### 3. Audio
Speakers does not output any sound? just shut down the macOS and power it on again! (must be shutdown, restart wont fix this issue.)

## Bug
- Touchpad broke after wake from sleep (pls help)

## All the thanks goes to
- [Dortania](https://github.com/dortania) for [OpencCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [Acidanthera](https://github.com/acidanthera) and other contributors for [OpenCore](https://github.com/acidanthera/OpenCorePkg) *lol obviously 😂*
- [Dr.NooB](https://github.com/itsdrnoob) for [Mi NoteBook 14 Hackintosh EFI Files](https://github.com/itsdrnoob/Mi-NoteBook-14-Hackintosh)
- [h9419](https://github.com/h9419) for [HP Pavilion 14 bf100 Hackintosh EFI Files](https://github.com/h9419/HP_Pavilion_14_bf100_Hackintosh)
- [Joshua Wise](https://github.com/jwise) for [HoRNDIS 9.2 kext](https://github.com/jwise/HoRNDIS)
- r/Hackintosh Paradise Discord Members for troubleshooting assistance
- Last, thanks to anything or anyone that help me build this EFI file, too many to write them down here lol xD

# Enjoy Hackintoshing!
