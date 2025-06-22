# Xiaomi SM8250 Kernel Auto Build  
Automatically build kernels with SukiSU Ultra SUSFS KPM support using GitHub Action. Source code is based on [n0kernel](https://github.com/jhchong94/kernel_xiaomi_sm8250_n0kernel) and [liyafe1997](https://github.com/liyafe1997/kernel_xiaomi_sm8250_mod).  

**[中文](README.md) [English](README_EN.md)**  

> [!WARNING]  
> Before flashing, ensure your device's Bootloader is unlocked. Verify that this kernel is compatible with your device and that the device codename matches the downloaded flashable ZIP. Always back up your original boot!  

### Kernel Info  
- Compatible with Xiaomi devices powered by Snapdragon 865/870  
- Supports MIUI/HyperOS from Android 11 to 15 (*AOSP support coming soon*)  
- Kernel is packaged as an AnyKernel3 flashable ZIP  
- Source code based on:  
  - [n0kernel (Xiaomi 10/Pro only)](https://github.com/jhchong94/kernel_xiaomi_sm8250_n0kernel)  
  - [liyafe1997 (All SM8250 devices)](https://github.com/liyafe1997/kernel_xiaomi_sm8250_mod)  

### Features  
- SukiSU Ultra SUSFS KPM support  
- Full LTO build  
- Optimized fast charging  
- HBM and DC dimming support  
- KCAL color calibration  
- USB serial driver support (CH340/FTDI/PL2303/OTI6858/TI/SPCP8X5/QT2/UPD78F0730/CP210X)  
- EROFS support  
- F2FS with realtime discard for better TRIM performance  
- CANBus and USBCAN adapter support  
- zRAM with LZ4, LZ4HC, and ZSTD compression algorithms  
- All features from n0kernel  
- Additional features from [liyafe1997](https://github.com/liyafe1997/kernel_xiaomi_sm8250_mod)  

### Installation Guide  
1. Download the appropriate kernel flashable ZIP for your device from the [Releases page](https://github.com/clcwpwqi/xiaomi_sm8250_kernel/releases), or compile it yourself after forking.  
2. Back up your boot partition.  
3. Flash using TWRP or another custom recovery. The installer will verify your device codename and ROM info.  
> If the installer reports no compatible kernel for your device or fails the codename check, verify your device model, ROM, and the downloaded ZIP.  
4. If the device boots normally, you're good to go. If not, restore the original boot to boot again.  
> If the screen stays black after booting, try a kernel built from liyafe1997's source or check if you're using a kernel incompatible with your system version.  

### Device Codename Reference  

- **n0kernel Support**  

| Device Name    | Codename |  
| ----------- | -------- |  
| Xiaomi 10    | umi      |  
| Xiaomi 10 Pro | cmi      |  

- **liyafe1997 Kernel Support**  

| Device Name                     | Codename  |  
| ---------------------------- | --------- |  
| Xiaomi Pad 6                  | pipa      |  
| Xiaomi Pad 5 Pro 12.4         | dagu      |  
| Xiaomi Pad 5 Pro 5G           | enuma     |  
| Xiaomi Pad 5 Pro              | elish     |  
| Xiaomi 12X                    | psyche    |  
| Xiaomi 11X / POCO F3 / Redmi K40 | alioth    |  
| Xiaomi 10T / Redmi K30S Ultra | apollo    |  
| Xiaomi 10S                    | thyme     |  
| Xiaomi 10 Ultra               | cas       |  
| Xiaomi 10 Pro                 | cmi       |  
| Xiaomi 10                     | umi       |  
| Redmi K40S                    | munch     |  
| Redmi K30 Pro                 | lmi       |  

### Naming Convention  
#### Filename Format  
##### `Codename`-`Features`-`PackageType`.zip  
Example: `umi-ksu-Anykernel3.zip`  
> Xiaomi 10 kernel with SukiSU Ultra, KPM, and SUSFS support, packaged as an AnyKernel3 flashable ZIP.  

#### Kernel Version Format  
##### `KernelVersion`-`BuildDate`-`CompilerUser`-`RandomCode`  
Example: `4.19.325-20250621-clcwpwqi-z9m7c3d3`  
> Xiaomi 10 kernel compiled by clcwpwqi on June 21, 2025.  

#### Notes  
- In this project, "ksu" refers to the [SukiSU Ultra](https://github.com/SukiSU-Ultra/SukiSU-Ultra) branch of KernelSU, with added [SUSFS](https://gitlab.com/simonpunk/susfs4ksu) and [KPM for SukiSU Ultra](https://github.com/SukiSU-Ultra/SukiSU_KernelPatch_patch) support.  
