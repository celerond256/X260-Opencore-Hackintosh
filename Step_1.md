## GOALS
``Dual boot MacOS and Windows 10 in single 500gb SSD, with ±250gb APFS for Mac, ±130GB NTFS for Windows 10, ~120GB NTFS remaining for shared data.``

## GATHERING FILES
Im using Windows 10 Pro with other SSD with Windows 10 installs to gather files.

**1. Download macOS using GibMacOS (downloaded files around 8 gigs), requires:**
  * python-3.9.2-amd64 (recommended 3.7)
  * gibMacOS-master (download from https://github.com/corpnewt/gibMacOS)
    * _Possible Problems:_
      - MacOS Downloaded files corrupted / unfinished --> _redownload_
      - Check list and filesize in \gibMacOS-master\macOS Downloads\publicrelease\001-57224 - 10.15.7 macOS Catalina
![Picture1](https://user-images.githubusercontent.com/85201626/120457750-e7801480-c3c0-11eb-9719-9f468392804b.png)
  * Steps to `make macOS installer until booting without USB` are well describe in [Picel YT Channel](https://www.youtube.com/watch?v=zdcPPpd-g8I&t=245s)
  * Download [Opencore 0.6.8](https://github.com/acidanthera/opencorepkg/releases) from acidanthera
  * You may want to read the [Dortania documentation](https://dortania.github.io/getting-started/), to make sure files I included in EFI were legit 😁
  * Important Notice:
    * Include only _priority files_ and config.plist settings for first time boot / install. If you're not sure yet, read the Dortania documentation again and again..
  > For example:
  > In my _config.plist_, I had set my latest _layout-id_ --which is 29-- for audio device in _DeviceProperties_. You may want to delete it, 
  > and test the layout-id in _boot-args_ section for your first install.
  > Use USBInjectAll.kext when installing. My USBMap.kext was made after installation.

**2. Download WIN10.PRO.2009.SUPERLITE+COMPACT.X64.GHOSTSPECTRE.(N) using Internet Download Manager or XDM (downloaded files around 2,76 gigs, as 5 part zipped files, unzipped after download)**
   > flash to a flashdisk using [Rufus](https://rufus.ie/en/)
  * Steps to install Windows 10 are described in [Brandon Yen YT Channel](https://youtu.be/ztxHRGdX0Sw)
    * _Possible Problems:_
      - "I can't do steps at `dism /Get-WimInfo /WimFile:D:\sources\install.esd`"
      > It's seems Windows 10 Ghost Spectre made from macOS ecosystem, so you should use another command (see the video description)
      > `dism /Get-WimInfo /WimFile:D:\Sources\install.wim` and friends.
## INSTALL MACOS CATALINA
**1. Make sure you already have bootable macOS installer, and the installer listed in Thinkpad boot menu**
  > Once booted to the picker, format SSD with APFS, then install macOS Catalina
  > If you can't get into the picker, you may remake the installer again..
  > It's important that you have either **another SSD with Windows 10 installed**, or another computer to troubleshoot
**2. After success booting your fresh installed macOS (still using USB installer), do the following:**
  * Make sure your wifi and other hardware worked, you may want to use USB cable mouse at this time, because trackpad and trackpoint may not work.
  * Mount your Flashdisk EFI using [MountEFI](https://github.com/corpnewt/MountEFI), copy the whole EFI folder to the Desktop or somewhere safe. Unmount Flashdisk EFI.
  * Mount your mac SSD EFI, copy the EFI folder from Flashdisk to the SSD EFI.
    * _Possible Problems:_
      - Still can't boot without Flashdisk! Some text showed up in the upper left corner without further information --> well, then boot with Flashdisk, choose your mac SSD, and repair the structure in your mac SSD EFI
      > Make sure you copied the `EFI folder` to the mac SSD EFI with the right structure: 
      > /EFI  _(this is a Volume named EFI in your Mac Hardisk)_
      > |--/EFI  _(this is a folder named EFI)_
      > |----/BOOT  _(this is a folder)_
      > |----/OC  _(this is a folder)_
  * If you can now boot without Flashdisk, boot into recovery from Opencore picker, and open `Disk Utility`. Then create another partition for Windows install. In my case, I made 250GB for Windows and Data partition. For now, formatted it as exFAT.
  * You may want do normal reboot first, to clarify the partition already created without any problems.
 
## INSTALL WINDOWS 10 GHOST SPECTRE
**Its easier to follow the guide from [Brandon Yen YT Channel](https://youtu.be/ztxHRGdX0Sw). You can watch from your handphone while installing**
**Make sure Windows Boot Manager listed in Thinkpad boot menu**
> If not.. Well, reinstall Windows! --or you can Google "missing Windows Boot Manager"
> Calm down, many people experienced it...

## DUAL BOOT INSTALL _DRAMA_ WAS DONE !
> Well, not yet.. It's just the first episode...
> to be continued...
