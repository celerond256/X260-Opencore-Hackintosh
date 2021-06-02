# X260-Opencore-Hackintosh

## Introduction

Files and steps related to Hackintosh-ing a Thinkpad X260 laptop using Opencore bootloader.
Before using any of these files, make sure you have similar hardware.
> *Though your cases may vary..*

## My Specs

💻 **Laptop**
* Brand       :	Lenovo Thinkpad X260
* BIOS version: R02ET74W 1.47
* Monitor     : 12,5" TN panel 1366x768 HD
* Battery     : Dual = 3-cell 23Whr internal + 6-cell 72Whr external
  > My _new_ internal battery only recognize with 17Whr max capacity in Windows 10, despite doing many workaround.
  > Sometimes _Lenovo Vantage_ shows 25% wears in my internal battery information.
  > But still, I get satisfying battery life from both Windows and macOS, which is 10+ hours for doing simple tasks.
* Processor   :	Intel® CORE ™ i5-6300U 2,4GHz vPro
* iGPU        :	Intel® Skylake GT2 [HD Graphics 520]
* dGPU        :	-
* RAM         :	1 x 8 GB, DDR4, 2133MHz, PC17000
* Audio Codec :	Realtek ALC293
* Keyboard    : Japan layout
* Trackpad    : Synaptics 2104 SMBus
  > Trackpad_Clickpad: touchpad with three physical button
* Storage     :	Samsung 870 EVO 500GB SSD 2,5"
  - 250GB macOS Catalina, APFS (install first; after success booting macOS, create 250GB _exFAT_ partition with Disk Utility)
  - 250GB Windows ```Win10.Pro.2009.Superlite+Compact.X64.GhostSpectre.(N)``` & Data (install after macOS) 
    - 130GB System, NTFS
    - 120GB Data, NTFS
    > Why NTFS over exFAT for Data? Well, formatted it with exFAT may require more tweaks...
* Card Reader  : Realtek RTS522A PCI Express Card Reader
* Web Cam      : 720p
* Wireless LAN : Intel ® Dual Band Wireless-AC 8260 (with bluetooth)
* Ethernet     : Intel Ethernet Connection I219-LM
* Bootloader   : OpenCore 0.6.8
* OS Version   : ```macOS Catalina 10.15.7 (Build 19H15)```
* Installer    : GibMacOS


**Other Hardware:**
  > Which I used daily with this hackintosh machine
* 45Watts AC adapter
* Logitech Pebble mouse (with usb receiver & bluetooth connection)
* 32GB HP flasdiksk USB 2.0 (for macOS first install)
* 16GB Sandisk flashdisk USB 3.0 (first I use for Windows installer; later I flashed it with Clover, used for dumping DSDT & reset NVRAM)
* 16GB HP flashdisk USB 2.0 (for testing after install)
* VGA to miniDP connector (I use an external monitor with VGA connector)
* Simbadda Bluetooth Speaker (model no: CST370N)
* iPhone 6 (iOS version 12.5.3 / 16H41), and several Apple device logged in using my Apple ID
* RedmiGo (Android version 8.1.0)
* External harddisk USB 3.0, formatted as NTFS and used for data backup

**BIOS Settings**
* Enable  : Swap Fn - Ctrl, trackpad, trackpoint, card reader, Intel TPM (set to _inactive_), Execution Prevention, Intel Virtualization Technology, Intel VT-d Feature
* Disable : Always on usb, WiGig, WWAN, Anti Theft, Intel SGX, Computrace, Device Guard, Secure Boot,
* Boot    : include only _ATA Drive_ & _FD HDD_, UEFI only, CSM = No

***Worked***
- [x] iGPU with external monitor
  > only work after waking from sleep
- [x] CPU power management
- [x] Backlight
- [x] Webcam
- [x] Sound: speaker, microphone
- [x] Wifi
- [x] Ethernet / LAN
- [x] Bluetooth
- [x] All USB Ports
- [x] Battery notification: charging, full charge, etc
- [x] Trackpad, trackpoint, 3 physical button, & gesture (Trackpad showed in System Preferences)
- [x] Keyboard --remap with [Karabiner-Elements](https://karabiner-elements.pqrs.org) 
- [x] Power management
- [x] iMessage, Facetime, Appstore
- [x] DRM Support, tested based on [Dortania Opencore Post Install](https://dortania.github.io/OpenCore-Post-Install/universal/drm.html#testing-drm)
- [x] Card reader 


**_not yet_ Worked or May Not Work**
* Logitech Pebble mouse with Bluetooth connection
> Logitech Pebble are known have problem with Catalina, some source says
* Handoff
* Airdrop

**Steps will written down in seperate .md files**

**Source:**
* Picel Media Group, Youtube Channel [Belajar bareng cara install Hackintosh Catalina (OpenCore) di Lenovo T440p](https://youtu.be/zdcPPpd-g8I)
* Hackintosh Telegram group, [H4CK1NTOSH L0V3R](https://t.me/HackintoshLover)
* MSzturc, Github [Lenovo-T460-OpenCore](https://github.com/MSzturc/Lenovo-T460-OpenCore)
