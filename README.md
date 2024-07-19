# GenericNVMeName
A codeless kext that patches the NVMe controller to rename it to Apple’s native one or something else

![GitHub Downloads (all assets, latest release)](https://img.shields.io/github/downloads/AppleOSX/GenericNVMeName/total)

## Features
- Renames `Generic SSD Controller` in System Information to `Apple SSD Controller` or another specified name.

<img src="Img/proof.png">

## Supported OS
- macOS Catalina (10.15) to macOS Sonoma (14)

## Usage
1. Download from releases.
2. Click on the `GenericNVMeName` kext and choose `Show Package Contents`.

<img src="Img/1.png">

3. Click on the `Contents` folder.

<img src="Img/2.png">

4. Edit `Info.plist`.

<img src="Img/3.png">

5. Locate `IOPCIPrimaryMatch` under `IOKitPersonalities\com.HorizonUnix.GenericNVMeName`.

<img src="Img/4.png">

6. To find your `IOPCIPrimaryMatch`, use Hackintool to obtain the NVMe `Vendor` and `Device` ID.

<img src="Img/5.png">

> **Warning**
> - For example, if your `Vendor` ID is `0xAAAA` and `Device` ID is `0xBBBB`, combine both as follows: `0xbbbbaaaa` (all in lowercase) and input it into `IOPCIPrimaryMatch`.
> - Supports multiple NVMe IDs by separating them with a space, e.g., `0xbbbbaaaa 0xddddcccc`.
> - In my case, with a `Vendor` ID of `0x8086` and a `Device` ID of `0xF1A8`, my `IOPCIPrimaryMatch` is `0xf1a88086`.

### [Optional]
- Change the NVMe controller name by modifying the `Vendor Name` and `Chipset Name` in `Info.plist`.
