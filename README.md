# acer-aspire-7-efi
EFI for booting MacOS Sonoma

This is pretty much a frankenstein monster made using things from the below two repo:
- https://github.com/AbhaySingh15/Acer-aspire-7-A715-75G-Opencore-EFI/tree/main
- https://github.com/brunoanc/AN515-54-Hackintosh
All credits to them for making things work.

**OpenCore Version: [1.0.1 Offical](https://github.com/acidanthera/OpenCorePkg)**
 MacOS Version: 14.6.1 Sonoma
 :-------------------------:
 ![alt text](https://raw.githubusercontent.com/captain-nemo1/acer-aspire-7-efi/main/images/Screenshot_2024-08-25_at_2.29.43_PM.webp)
 
## System Information

| Specifications | Detail                                                  |
| ------------------- | ------------------------------------------- |
| Computer model      | Acer Aspire 7 A715-75G-50SA                |
| Processor           | Intel Core i5-9300H ~2.4ghz turbo 4.1ghz   |
| Memory              | 16gb ddr4 2667mhz                           |
| Hard Disk           | 512gb SK Hynix BC501 HFM512GDJTNG-8310A    |
| Integrated Graphics | Intel UHD Graphics 630                     |
| Monitor             | FHD 1920x1080 (15.6 inch)                  |
| Sound Card          | Realtek ALC255                             |
| Wireless Card       | Intel Wi-Fi 6 AX200 160MHz                 |
| Touchpad            | I2C HID based                              |
| Keyboard            | PS2 Based

## Working
- [x] NVRAM
- [x] Integrated gpu 
- [x] Screen Brightness Control
- [x] Display at native resolution and at 60hz
- [x] All USB ports
- [x] Web Camera
- [x] Battery Percentage
- [x] Sleep & Wake
- [x] Sensors
- [x] Trackpad
- [x] Fn Keys
- [x] Onboard wifi
- [x] Bluetooth
- [x] Speakers 
- [x] Inbuilt microphone

## Special stuff done here:
 - Used AirportItlwm_v2.3.0_stable_Sonoma14.4.kext.zip for Somona 14.4+
 - Added -igfxblt -igfxbls to boot args since without it we were booting into a black screen.
 - SecureBoot is disbaled since Sonoma requires that.

## Not Working 
- Discrete nvidia gtx 1650 gpu
- HDMI port (since it's connected to the GTX 1650).

## Install
- Generate your own [smbios](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#using-gensmbios) and makes changes in the EFI/OC/config.plist based on that.
- Create your MacOs recovery [USB](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/)
- Put the EFI folder from here to your your USB.
- Boot into the USB and select Macbook Installer.

## Post Install

- Clone the [ComboJack repo](https://github.com/hackintosh-stuff/ComboJack) and run the installer inside the `ComboJack_Installer` folder to get the jack port working correctly.
- Run the following commands for sleep wake:
  ```
  sudo pmset -a hibernatemode 0
  sudo pmset -a autopoweroff 0
  sudo pmset -a standby 0
  sudo pmset -a proximitywake 0
  ```
