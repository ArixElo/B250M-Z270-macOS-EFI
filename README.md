# MSI B250M-PRO-VH/Gigabyte GA-Z270-Gaming-K3 macOS OpenCore EFI 

## macOS & OpenCore Versions
- macOS Big Sur 11.7/Monterey 12.6/Ventura 13.5.
- OpenCore r0.8.4

**Catalina is not supported!**

**Ethernet connection is required.**

## Usage guide:
- Make macOS Installer by following this link: https://dortania.github.io/OpenCore-Install-Guide/installer-guide/
- After making it, simply download latest version of EFI, and unpack EFI folder, use https://github.com/corpnewt/GenSMBIOS to generate your SMBIOS configs for **iMac18,1** or **iMac18,3** if you want to use dedicated GPU.
- P.S for Gaming K3 motherboard, pick the **slave-v2-z270** branch instead.
- After that, simply drag your EFI folder to root of your macOS Installer USB drive.
- Reboot to UEFI and set recommended settings that are under this.
- Save and reboot to Boot Menu, pick your USB drive, and select macOS Installer/Name of your USB Drive (external),
- Go to Disk Utility and format your disk as APFS (sometimes it needs to be formatted as macOS Journaled due to strange issue with APFS when it doesn't create EFI partition,)
- After that go to Big Sur/Monterey/Ventura installation, and pick your newly formatted drive, it will reboot a couple of times, then simply go to Boot Menu and select your USB drive, after that simply select "macOS Installer" and lately select the name of your macOS drive,
- After configuring macOS download and open MountEFI script: https://github.com/corpnewt/MountEFI
- Mount your USB drive and macOS drive EFI partitions,
- Copy EFI folder from USB to EFI Partition on your macOS drive, 
- Unmount all EFI partitions after so. 
- SSD/NVMe drives recommended.

- For Ventura installation you need to use this variable for macrecovery to download Internet Recovery Image: **Mac-4B682C642B45593E**

## UEFI Recommended Settings for MSI Board:
```
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
```
## UEFI Recommended Settings for Gigabyte Board:

```
- BIOS
    - Fast boot: Disabled
    - Windows 8/10 Features: OtherOS
    - LAN PXE Boot Option ROM: Disabled
    - Storage Boot Option Control: UEFI
    - Other PCI devices: UEFI

- Peripherals
    - Initial Display Output: PCIe 1 Slot
    - USB 3.0 DAC-UP 2: Normal
    - USB Configuration -> XHCI Hand-Off: Enabled
    - SATA and RST Configuration -> Agressive LPM Support: Disabled (Enable can cause graphical freezes)

- Chipset
    - VT-d: Disabled
    - Internal graphics: Enabled
    - DVMT Pre-Allocated: 64MB
    - DVMT Total Gfx-Mem: 128MB
```

That EFI doesn't have verbose mode turned on by default, but you can simply set it by adding:
**-v** parameter to config.plist at NVRAM section in boot-args string.

## Specs that are used by this EFI:
- Motherboard: MSI B250M-PRO-VH/Gigabyte GA-Z270-Gaming-K3,
- CPU: Intel Core i7 7700 (4x3.6GHz+ Turbo Boost to 4.20GHz),
- GPU Intel HD Graphics 630/AMD Radeon RX 570 4GB,
- Memory: 32GB DDR4,
- Disk on which macOS is installed: GOODRAM IRDM 128GB (SSD, SATA)

## What's working:
- Intel HD Graphics 630 VGA and HDMI outputs (full graphics acceleration and software DRM),
- Dedicated GPU Acceleration
- Realtek ALC 887, with layout-id 52/ALC 1220 with layout-id 1,
- Network,
- Night Shift,
- Bluetooth with a Realtek Dongle (also works on Monterey!),
- iMessage and FaceTime after running iMessageFix (https://t.me/arixnara/29) **For Ventura this fix is not required.**,
- System updates.

## What's not working:
- Sleep & Wake (can't be fixable on MSI)

README is heavily inspired by: https://github.com/lshbluesky/OC-GA-B250M-DS3H-Hackintosh