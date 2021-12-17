MSI B250M-PRO-VH macOS OpenCore EFI 

#macOS & OpenCore Versions
- macOS Big Sur 11.6/Monterey 12.0.1
- OpenCore r0.7.6

Catalina isn't tested!
It may have some issues, but if there's anything ok with it, then contact with me through Telegram: 
t.me/ArixElo

#UEFI Recommended Settings:
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

#Issues during normal usage (this note will be updated):
- There's some problem with macOS updates, basically i can't able to update normally.

#What's working:
- Intel HD Graphics 630 VGA and HDMI outputs (full graphics acceleration and DRM),
- Realtek ALC 887, with layout-id 11,
- Network,
- Night Shift,
- iMessage & FaceTime,
- Bluetooth with a Realtek Dongle (also works on Monterey!),

#What's not working:
- Sleep & Wake

README is heavily inspired by: https://github.com/lshbluesky/OC-GA-B250M-DS3H-Hackintosh