# Ezorith's Latitude 3310
This EFI is built for Dell Latitude 3310 (with touchscreen), based on OpenCore.

![laptop](https://github.com/ezorith/Latitude-3310/assets/155196263/18c5a20e-7d90-46ea-82bd-221ceefcffda)

> [!TIP]
> Please use this EFI as reference towards building your own.</br>
> <sup>Building EFI from scratch can be challenging, but it's also rewarding.</sup>

## 🛟 About This Hack
    Model: MacBookPro16,3              WF+BT: Intel Wireless-AC 9560  
    CPU:   Intel Core i5-8265U         Sound: Realtek ALC3246        
    GPU:   Intel UHD Graphics 620      Image: Integrated Webcam      
    RAM:   1x16GB SK Hynix DDR4-2666   Type:  PS/2 Keyboard          
    NVMe:  Samsung 980 500GB           Point: I2C ELAN Touchpad      
    LAN:   Realtek RTL8111HSD          Touch: I2C ELAN Touchscreen  

> [!IMPORTANT]
> `PlatformInfo` > `Generic` details required. SMBIOS `MacBookPro 16,3` chosen for this build based on specs and release year.

## ✨ Features
- Based on OpenCore-Mod-1.0.0, tested on macOS Sonoma 14.3.1.
- Working display, HDMI/USB-C out, brightness and graphics acceleration.
- Working built-in mic and stereo, HDMI/USB-C out, headphone jack.
- Working USB, ethernet, webcam, and microSD card reader.
- Working sleep, wake, native CPU power management and charger detect.
- Working keyboard including volume, brightness, sleep and most Fn keys (except mute/search/airplane mode).
- Working touchpad gestures and touchscreen.

## ⚙️ BIOS Settings
- Disable Intel SGX.
- Set disk mode to AHCI.
- Disable Secure Boot.

### 🔧 BIOS Modification
-  CFG Lock: `setup_var 0x6ED 0x00`
-  DVMT 64MB: `setup_var 0xA10 0x02`

> [!IMPORTANT]
> BIOS modification must be done prior first boot. Use either `RU.efi` or `modGRUBShell.efi`

## 🪄 Enhancements
- [macOS HiDPI](https://github.com/xzhih/one-key-hidpi) - enables Retina display scaling.
- [ComboJack](https://github.com/hackintosh-stuff/ComboJack/tree/master/ComboJack_Installer) - enables headphone jack pop-up dialog.
- [Secure Boot](https://github.com/perez987/OpenCore-and-UEFI-Secure-Boot) - allows Secure Boot to be enabled for additional security.

## 🐻 Bear in mind
- `ShowPicker` is enabled for multiboot. Disable if desired.
- `NVMeFix.kext` is disabled as per hardware. Enable if required.
- This build uses `AirportItlwm.kext` which doesn't support AirDrop/Sidecar/Handoff.
- Power button requires SSDT patching. To bring up power dialog, hold `ctrl` and press power.
- `ACPI` > `Quirks ` > `EnableForAll` boolean is specific to OpenCore-Mod. Allows multiboot without injecting SSDT patches in other OS's. Safe to remove if using OpenCore official.

<sub>🌟 Special thanks to @silvercreeper356 for their help!</sub>
