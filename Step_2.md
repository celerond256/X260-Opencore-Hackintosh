## GOALS
> `Fixing Lenovo Thinkpad X260 hardware support for macOS Catalina`

##  GATHERING FILES
Make sure you already have fresh installation of Hackintosh.
Make sure you can boot either macOS or Windows 10 without any problems. Because you may require to boot Windows in process of fixing hardware support.
NOTE:
* after successfully fixing hardware support, I choose to reinstall MacOS and use whole SSD for Catalina only, and install Windows 7 64bit in a Virtualbox for daily work.
* if you want to keep Windows 10 installation, `I recommend use clover bootloader to clean NVRAM`. Because Opencore builtin ResetNVRAM will wipe your Windows Boot Manager.

##  DOWNLOAD TOOLS
### From [Corptnewt](https://github.com/corpnewt) 
* [MountEFI](https://github.com/corpnewt/MountEFI)
* [SSDTTime](https://github.com/corpnewt/SSDTTime)
* [ProperTree](https://github.com/corpnewt/ProperTree)
* [MaciASL](https://github.com/acidanthera/MaciASL/releases/tag/1.6.1)
* [Hackintool](https://github.com/headkaze/Hackintool/releases/tag/3.6.1)
* [USBMap](https://github.com/corpnewt/USBMap)
* [Lilu-and-Friends](https://github.com/corpnewt/Lilu-and-Friends)
* [Clover](https://github.com/CloverHackyColor/CloverBootloader/releases) ==> for clean NVRAM if you have separate EFI for Windows 10 installation.

##  DOWNLOAD FILES, SSDT, Apps & KEXT
* [OpenCore](https://github.com/acidanthera/opencorepkg/releases) ==> Download both `Realease` and `Debug`. Remember to consistent when using any of the files included, dont mix.
* [Daliansky Files Translated](https://github.com/5T33Z0/OC-Little-Translated) ==> from here we took:some SSDT, pci-aspm-default settings
* [SSDT-USBX](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/compiled/SSDT-EC-USBX-LAPTOP.aml)
* [AppleALC](https://github.com/acidanthera/applealc/releases)
* [AirportItlwm](https://github.com/OpenIntelWireless/itlwm/releases/tag/v1.3.0) ==> download `AirportItlwm_v1.3.0_stable_Catalina.kext.zip`
* [IntelBluetoothInjector & IntelBluetoothFirmware](https://github.com/OpenIntelWireless/IntelBluetoothFirmware/releases/tag/1.1.3)
* [VirtualSMC pack](https://github.com/acidanthera/VirtualSMC/releases/tag/1.2.4) ==> VirtualSMC come with few kext we need, but some may not.
* [VoodooPS2Controller](https://github.com/acidanthera/VoodooPS2/releases/tag/2.2.3) ==> use only VoodooPS2Keyboard, remove other plugins inside.
* [VoodooRMI](https://github.com/VoodooSMBus/VoodooRMI/releases/tag/1.3.3) ==> VoodooSMBus already included in the RMI package, no need to download separately.
* [CPUFriend](https://github.com/acidanthera/CPUFriend/releases)
* [CPUFriendFriend](https://github.com/corpnewt/CPUFriendFriend)
* [USBInjectAll](https://github.com/Sniki/OS-X-USB-Inject-All/releases) ==> After mapping, we will replace it with USBMap.kext created with USBMap tool.
* [SSDT-KBRD & patch](https://github.com/MSzturc/Lenovo-T460-OpenCore/releases/tag/v0.60.1) ==> Need some editing with MaciASL (edit only .dsl, or decompile .aml with iASL first and then edit with MaciASL), also need [ThinkpadAssistant](https://github.com/MSzturc/ThinkpadAssistant/releases/tag/v1.9.2.1) to make Function Keys works.


##  TIPS
* Create Alias (shortcut) for tools we use regularly to desktop;
* Make backup (EFI, tools, document) in an External Drive, Dummy USB (remember we have spare partition that can be loaded with files), or a Google Drive;
* Make a document for tracing any change we had done, so if stuff fails we can revert it back quickly.
* DON'T do any hack/fixing in working hour! Do your homework first, backup files, and then.. HACK!
