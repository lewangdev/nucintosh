Nucintosh  - Hackintosh on Intel NUC8
=====================================

## Avaiable Devices

* NUC8i5BEH
* NUC8i7BEH

## OpenCore Version

* 0.5.9

## BIOS Settings

Press F2 key to enter BIOS and press F9 to reset BOIS 

* Boot -> Boot Priority -> Legacy Boot Priority -> Legacy Boot  : Disable
* Boot -> Boot Configuration
    * UEFI Boot -> Fast Boot : Disable
    * UEFI Boot -> Boot USB Devices First  : Enable
    * UEFI Boot -> Boot Network Devices Last  : Enable
    * Boot Devices -> Network Boot : Disable 
* Boot -> Secure Boot -> Secure Boot  : Disable
* Security -> Security Features -> Inter VT for directed I/VO (VT -d)  : Disable
* Power -> Secondary Power Settings -> Wake on LAN from S4/S5  : Stay Off 
* Devices -> Onboard Devices (If you want to use BCM943602CS, otherwise keep WLAN and Bluetooth Enable)
    * WLAN : Disable
    * Bluetooth : Disable

## Make a bootable macOS Udisk

* [How to create a bootable installer for macOS](https://support.apple.com/en-us/HT201372) [[中文](https://support.apple.com/zh-cn/HT208496)]
* Mount UDisk EFI Partition and copy OpenCore to it

```txt
macOS\ Installer
    └── EFI
        ├── BOOT
        ├── OC
```

## Install macOS

* Boot from udisk and install macOS

## Configurations After Installing macOS

* Mount macOS EFI Partition and Copy OpenCore to it
* Change SN/SLB/DeviceUUID
    * Use Hackintools to generate the 3 codes
    * Use ProperTree to update the 3 codes in `EFI/OC/config.plist`

## Notice

* ``EFI-OC-Apple``for Apple Broadcom WiFi/Bluetooth card, such as BCM943602CS
* ``EFI-OC-Intel``for onboard Intel WiFi and Bluetooth
