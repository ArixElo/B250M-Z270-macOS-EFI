# MSI B250M-PRO-VH macOS OpenCore EFI 

## macOS & OpenCore Versions
- macOS Big Sur 11.7/Monterey 12.6/Ventura 11.0.
- OpenCore r0.8.4

**Catalina is not supported!**

**Ethernet connection is required.**

## Usage guide:
- Make macOS Installer by following this link: https://dortania.github.io/OpenCore-Install-Guide/installer-guide/
- After making it, simply download latest version of EFI and unpack EFI folder, use https://github.com/corpnewt/GenSMBIOS to generate your SMBIOS configs for **iMac18,1** model,
- After that, simply drag your EFI folder to root of your macOS Installer USB drive.
- Reboot to UEFI and set recommended settings that are under this,
- Save and reboot to Boot Menu, pick your USB drive, and select macOS Installer (external),
- Go to Disk Utility and format your disk as APFS (sometimes it needs to be formatted as macOS Journaled due to strange issue with APFS when it doesn't create EFI partition,)
- After that go to Big Sur/Monterey/Ventura installation, and pick your newly formatted drive, it will reboot a couple of times, then simply go to Boot Menu and select your USB drive, after that simply select "macOS Installer" and lately select the name of your macOS drive,
- After configuring macOS download and open MountEFI script: https://github.com/corpnewt/MountEFI
- Mount your USB drive and macOS drive EFI partitions,
- Copy EFI folder from USB to EFI Partition on your macOS drive, 
- Unmount all EFI partitions after so. 
- SSD/NVMe drives recommended.

- For Ventura installation you need to use this variable for macrecovery to download Internet Recovery Image: **Mac-4B682C642B45593E**

## UEFI Recommended Settings:
- Hyper-Threading Technology: Enabled
- Intel Speed Boost: Enabled
- Fast Boot: Disabled
- MSI Fast Boot: Disabled
- OS Type: Windows 8 / 10
- Secure Boot: Disabled
- Serial(COM) Port: Disabled
- Parallel Port: Disabled
- XHCI Hand-Off: Enabled
- SATA Mode: AHCI
- VT-d: Disabled
- DVMT Pre-Allocated Memory: 64~128 MB
- PTT can be enabled if you have installed Windows 11 on separate drive.

That EFI doesn't have verbose mode turned on by default, but you can simply set it by adding:
**-v** parameter to config.plist at NVRAM section in boot-args string.

## Specs that are used by this EFI:
- Motherboard: MSI B250M-PRO-VH,
- CPU: Intel Core i7 7700 (4x3.6GHz+ Turbo Boost to 4.20GHz),
- GPU Intel HD Graphics 630,
- Memory: 16GB DDR4,
- Disk on which macOS is installed: GOODRAM IRDM 128GB (SSD, SATA)

## What's working:
- Intel HD Graphics 630 VGA and HDMI outputs (full graphics acceleration and software DRM),
- Realtek ALC 887, with layout-id 52,
- Network,
- Night Shift,
- Bluetooth with a Realtek Dongle (also works on Monterey!),
- iMessage and FaceTime after running iMessageFix (https://t.me/arixnara/29) **For Ventura this fix is not required.**,
- System updates.

## What's not working:
- Sleep & Wake (can't be fixable)

README is heavily inspired by: https://github.com/lshbluesky/OC-GA-B250M-DS3H-Hackintosh
