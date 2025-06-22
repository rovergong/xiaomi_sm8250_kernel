# Xiaomi SM8250 Kernel Auto Build  
Automatically build kernels with SukiSU-Ultra SUSFS KPM or KernelSU-Next SUSFS support using GitHub Actions  

**[中文](README.md) [English](README_EN.md)**  

> [!WARNING]  
> Before flashing, please ensure your phone has unlocked Bootloader and backed up original boot and modem. Verify your device is compatible with this kernel, and check both device codename and system version match the downloaded kernel package!  

### Kernel Information  
- For Xiaomi devices with Snapdragon 865/870  
- Supports MIUI/HyperOS on Android 11-15 (*AOSP support coming soon*)  
- Kernel packaged as AnyKernel3 flashable ZIP  
- Source code based on [n0kernel (Xiaomi 10/Pro only)](https://github.com/jhchong94/kernel_xiaomi_sm8250_n0kernel) and [liyafe1997 (all SM8250 devices)](https://github.com/liyafe1997/kernel_xiaomi_sm8250_mod)  

### Kernel Features  
- SukiSU-Ultra SUSFS KPM support (optional)  
- KernelSU-Next SUSFS support (optional)  
- Full LTO build  
- Fast charging optimization  
- HBM and DC dimming support  
- KCAL color calibration  
- USB serial driver support (CH340/FTDI/PL2303/OTI6858/TI/SPCP8X5/QT2/UPD78F0730/CP210X)  
- EROFS support  
- F2FS with realtime discard for better TRIM  
- CANBus and USBCAN adapter support  
- zRAM with LZ4, LZ4HC, ZSTD compression algorithms  
- Other n0kernel features  
- Other liyafe1997 kernel features

### Installation Guide  
1. Download the appropriate kernel package from [Releases](https://github.com/clcwpwqi/xiaomi_sm8250_kernel/releases) or fork and build yourself  
2. Backup Boot partition  
3. Flash via custom recovery (e.g. TWRP) or kernel flash app. Device codename (n0kernel) and system version will be verified before flashing  
> If prompted "no suitable kernel for your device", verify codename and system version match  
4. If device boots normally, enjoy. Otherwise, restore original boot  
> If black screen occurs after boot, try kernels built from liyafe1997 source or check system version compatibility  

### Device Codename Reference  

- **n0kernel Supported**  

| Device Name    | Codename |  
| ----------- | -------- |  
| Xiaomi 10    | umi      |  
| Xiaomi 10 Pro | cmi      |  

- **liyafe1997 Kernel Supported**  

| Device Name                     | Codename  |  
| ---------------------------- | --------- |  
| Xiaomi Pad 6                  | pipa      |  
| Xiaomi Pad 5 Pro 12.4         | dagu      |  
| Xiaomi Pad 5 Pro 5G           | enuma     |  
| Xiaomi Pad 5 Pro              | elish     |  
| Xiaomi 12X                    | psyche    |  
| Xiaomi 11X / POCO F3 / Redmi K40 | alioth    |  
| Xiaomi 10T / Redmi K30S Ultra   | apollo    |  
| Xiaomi 10S                    | thyme     |  
| Xiaomi 10 Ultra               | cas       |  
| Xiaomi 10 Pro                 | cmi       |  
| Xiaomi 10                     | umi       |  
| Redmi K40S                    | munch     |  
| Redmi K30 Pro                 | lmi       |  

### Build Guide  
1. [Fork this repository](https://github.com/clcwpwqi/xiaomi_sm8250_kernel/fork) to your account  
2. Go to Actions page  
3. Select build template and follow prompts  
4. Download and flash after build completes  

### Naming Convention  
#### Package Name  
##### Codename+KernelFeature+FileType.zip  
Example:  
`umi-ksu-Anykernel3.zip`  
> Xiaomi 10 kernel with SukiSU-Ultra SUSFS KPM or KernelSU-Next SUSFS (depending on selection), AnyKernel3 flashable ZIP  

#### Kernel Name  
##### KernelVersion-BuildDate-Compiler-RandomCode  
Example:  
`4.19.325-20250621-clcwpwqi-z9m7c3d3`  
> Xiaomi 10 kernel compiled by clcwpwqi on 2025-06-21  

#### Action Templates  
- `build_n0kernel.yml`: Builds using n0kernel source  
- `build_liyafe1997.yml`: Builds using liyafe1997 source  
> No official source template exists due to outdated code with poor high-version Android compatibility and limited features  

#### Notes  
- "ksu" in this project refers to:  
  - [SukiSU-Ultra](https://github.com/SukiSU-Ultra/SukiSU-Ultra) (a [KernelSU](https://github.com/tiann/KernelSU) fork) with [SUSFS](https://gitlab.com/simonpunk/susfs4ksu) and [KPM for SukiSU-Ultra](https://github.com/SukiSU-Ultra/SukiSU_KernelPatch_patch) support  
  - OR [KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next) (another KernelSU fork) with [SUSFS](https://gitlab.com/simonpunk/susfs4ksu) support  
