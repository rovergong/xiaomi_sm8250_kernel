# 小米 SM8250 机型内核自动构建
利用GitHub Action自动构建带SukiSU-Ultra SUSFS KPM或KernelSU-Next SUSFS支持的内核

**[中文](README.md) [English](README_EN.md)**

> [!WARNING]
>刷入前请确认手机已经解锁Bootloader，已经备份原boot与手机基带等内容。请确保您的设备适合刷入此内核，并检查设备代号与系统版本均符合您所下载的内核卡刷包！

### 内核信息
- 适用于骁龙865/870的小米设备
- 适用于安卓11-15的MIUI/HyperOS (*AOSP即将支持*)
- 内核为AnyKernel3卡刷包
- 内核源码基于[n0kernel(仅小米10/Pro)](https://github.com/jhchong94/kernel_xiaomi_sm8250_n0kernel)和[liyafe1997(所有SM8250机型)](https://github.com/liyafe1997/kernel_xiaomi_sm8250_mod)

### 内核特性
- SukiSU-Ultra SUSFS KPM 支持 (可选)
- KernelSU-Next SUSFS 支持 (可选)
- 完整LTO构建
- 快充优化
- 支持HBM和DC调光
- KCAL色彩校准
- 支持USB串口驱动（CH340/FTDI/PL2303/OTI6858/TI/SPCP8X5/QT2/UPD78F0730/CP210X）
- 支持EROFS
- F2FS开启了realtime discard以更好的TRIM闪存
- 支持CANBus和USBCAN适配器
- zRAM支持LZ4、LZ4HC、ZSTD压缩算法
- 其它n0kernel的内核特性
- 其他liyafe1997的内核特性

### 刷入指南
1. 从[发布页](https://github.com/clcwpwqi/xiaomi_sm8250_kernel/releases)下载适用于您机型的内核卡刷包，或Fork后自行编译
2. 备份Boot分区
3. 使用第三方Recovery(如TWRP)或Kernel Flash App等方式刷入，刷入前会检查设备代号(n0kernel)和系统版本
> 如果提示没有适合您设备的内核，请检查设备代号、系统版本是否与内核相匹配
4. 若开机则正常使用，不开机刷回原boot即可
> 若开机后黑屏，请刷入基于liyafe1997源码构建的内核，或检查是否使用了不符合系统版本的内核
### 机型对照

- **n0kernel 支持**

| 机型名称    | 设备代号 |
| ------- | ---- |
| 小米10    | umi  |
| 小米10 Pro | cmi  |

- **liyafe1997 内核支持**

|          设备名称           |  设备代号  |
| :---------------------: | :----: |
|          小米平板6          |  pipa  |
|     小米平板5 Pro 12.4      |  dagu  |
|      小米平板5 Pro 5G       | enuma  |
|        小米平板5 Pro        | elish  |
|          小米12X          | psyche |
| 小米11X / POCO F3 / 红米K40 | alioth |
|  小米10T / 红米K30S Ultra   | apollo |
|          小米10S          | thyme  |
|       小米10 Ultra        |  cas   |
|        小米10 Pro         |  cmi   |
|          小米10           |  umi   |
|         红米K40S          | munch  |
|        红米K30 Pro        |  lmi   |
### 自行构建指南
1. [创建本仓库分支](https://github.com/clcwpwqi/xiaomi_sm8250_kernel/fork)到你自己的账号
2. 进入Action页面
3. 选择构建模板，按提示输入
4. 构建完成后下载刷入
### 名称解读
#### 附件名称
##### 设备代号+内核特性+文件类型.zip
umi-ksu-Anykernel3.zip
> 小米10内核，包含SukiSU-Ultra SUSFS KPM或KernelSU-Next SUSFS(取决于你的选择)，AnyKernel3卡刷包
#### 内核名称
##### 内核版本+构建时间+编译用户+随机编码
4.19.325-20250621-clcwpwqi-z9m7c3d3
> 小米10内核，由clcwpwqi于2025年2月27日编译
#### Action构建模板名称
- build_n0kernel.yml 基于n0kernel的内核源码构建
- build_liyafe1997.yml 基于liyafe1997的内核源码构建
> 没有基于官方代码构建的模板是因为官方内核源码老旧，难以在安卓高版本上运行，且功能少，bug多
#### 其他
- 此项目中提到的“ksu”指[KernelSU](https://github.com/tiann/KernelSU)的分支[SukiSU-Ultra](https://github.com/SukiSU-Ultra/SukiSU-Ultra)并添加[SUSFS](https://gitlab.com/simonpunk/susfs4ksu)与[适用于SukiSU-Ultra的KPM](https://github.com/SukiSU-Ultra/SukiSU_KernelPatch_patch)支持，或[KernelSU](https://github.com/tiann/KernelSU)的分支[KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next)并添加[SUSFS](https://gitlab.com/simonpunk/susfs4ksu)支持
