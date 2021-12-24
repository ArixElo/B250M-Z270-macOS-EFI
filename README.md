# MSI B250M-PRO-VH macOS OpenCore EFI 

## macOS & OpenCore Versions
- macOS Big Sur 11.6/Monterey 12.0.1
- OpenCore r0.7.6

**Catalina isn't supported at all!**

## Usage guide:
- Make macOS Installer by following this link: https://dortania.github.io/OpenCore-Install-Guide/installer-guide/
- After making it, simply download latest version of EFI and unpack it to the EFI folder on root of your installer USB,
- Reboot to UEFI and set recommended settings that are under this,
- Save and reboot to Boot Menu, pick your USB, and select macOS Installer (external),
- Go to Disk Utility and format your disk as APFS,
- After that go to Big Sur/Monterey installation, and pick your newly formatted drive, it will reboot a couple of times, then simply go to Boot Menu and select your USB, after that simply select "macOS Installer" and lately select the name of your macOS drive,
- After configuring macOS download and open MountEFI script: https://github.com/corpnewt/MountEFI
- Mount your USB and drive EFI's,
- Copy EFI folder from USB to EFI Partition on your macOS drive, 
- Unmount all EFI partitions after so. 
- SSD/NVMe drives recommended.

## UEFI Recommended Settings:
- Hyper-Threading Technology: Enabled
- Intel Speed Boost: Enabled
- Fast Boot: Disabled
- MSI Fast Boot: Disabled
- OS Type : Windows 8 / 10
- Secure Boot : Disabled
- Serial(COM) Port: Disabled
- Parallel Port: Disabled
- XHCI Hand-Off : Enabled
- SATA Mode: AHCI
- VT-d : Disabled
- DVMT Pre-Allocated Memory : 64~128 MB
- Secure Boot and PTT can be enabled if you have installed Windows 11 on separate drive.

That EFI doesn't have verbose mode turned on by default, but you can simply set it by adding:
**-v** parameter to config.plist at NVRAM section in boot-args string.

## Issues during normal usage (this note will be updated):
None.

## What's working:
- Intel HD Graphics 630 VGA and HDMI outputs (full graphics acceleration and DRM),
- Realtek ALC 887, with layout-id 12,
- Network,
- Night Shift,
- Bluetooth with a Realtek Dongle (also works on Monterey!),
- iMessage and FaceTime after running iMessageFix (https://t.me/arixnara/29),
- System updates.

## What's not working:
- Sleep & Wake

README is heavily inspired by: https://github.com/lshbluesky/OC-GA-B250M-DS3H-Hackintosh
