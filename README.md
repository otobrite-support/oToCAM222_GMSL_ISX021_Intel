# Welcome to oToBrite Official Support

[![DownLoad Center](https://img.shields.io/badge/Download-Center-blue?logo=googlechrome&logoColor=white)](https://www.otobrite.com/support/download-center)
[![Intel Platform](https://img.shields.io/badge/Intel-Platform-blue?logo=googlechrome&logoColor=white)](https://www.otobrite.com/support/gmsl-camera-driver-support-list-for-intel)

**oToBrite Electronics, Inc.** is a leading Tier-1 Vision-AI company specializing in automotive ADAS, autonomous driving (AD), and industrial robotics (AMR) perception systems. 

This organization provides official Linux kernel drivers, Device Tree Overlays (DTBO), and Board Support Packages (BSP) for our automotive-grade **GMSL / GMSL2 cameras** running on **NVIDIA Jetson** and **Intel** platforms.

---

## 📷 Camera Driver Matrix & Quick Navigation

Find the corresponding driver repository by matching your camera model, sensor, and target computing platform:

| Camera Model | Image Sensor | Optical Format / Res | Key Features | NVIDIA Jetson Driver | Intel Platform Driver |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **oToCAM222** | Sony ISX021 | 2.5MP (1920×1280) | Built-in ISP, 120dB HDR, LFM | [👉 NVIDIA Repo](https://github.com/otobrite-support/oToCAM222_GMSL_ISX021_NVIDIA) | [👉 Intel Repo](https://github.com/otobrite-support/oToCAM222_GMSL_ISX021_Intel) |
| **oToCAM223** | Sony ISX031 | 3MP (2048×1536) | Built-in ISP, 120dB HDR, LFM | [👉 NVIDIA Repo](https://github.com/otobrite-support/oToCAM223_GMSL_ISX031_NVIDIA) | [👉 Intel Repo](https://github.com/otobrite-support/oToCAM223_GMSL_ISX031_Intel) |
| **oToCAM260** | Sony IMX490 | 5.4MP (2880×1860) | High Dynamic Range, Automotive | [👉 NVIDIA Repo](https://github.com/otobrite-support/oToCAM260ISP_GMSL_IMX490_NVIDIA) | [👉 Intel Repo](https://github.com/otobrite-support/oToCAM260ISP_GMSL_IMX490_Intel) |
| **oToCAM264** | Sony IMX390 | 2MP (1920×1080) | High Sensitivity, Starlight ADAS | [👉 NVIDIA Repo](https://github.com/otobrite-support/oToCAM264ISP_GMSL_IMX390_NVIDIA) | [👉 Intel Repo](https://github.com/otobrite-support/oToCAM264ISP_GMSL_IMX390_Intel) |
| **oToCAM271** | Sony IMX728 | 8.3MP (3840×2160) | 4K Ultra-HD Long Range Sensing | [👉 NVIDIA Repo](https://github.com/otobrite-support/oToCAM271ISP_GMSL_IMX728_NVIDIA) | [👉 Intel Repo](https://github.com/otobrite-support/oToCAM271ISP_GMSL_IMX728_Intel) |
| **oToCAM274** | Sony IMX623 | 3MP (2048×1536) | Global Shutter / Machine Vision | [👉 NVIDIA Repo](https://github.com/otobrite-support/oToCAM274ISP_GMSL_IMX623_NVIDIA) | [👉 Intel Repo](https://github.com/otobrite-support/oToCAM274ISP_GMSL_IMX623_Intel) |
| **oToCAM276** | onsemi AR0823AT | 8.3MP (3840×2160) | 4K HDR, High-Performance ADAS | [👉 NVIDIA Repo](https://github.com/otobrite-support/oToCAM276ISP_GMSL_AR0823AT_NVIDIA) | [👉 Intel Repo](https://github.com/otobrite-support/oToCAM276ISP_GMSL_AR0823_Intel) |
| **oToCAM278** | Sony IMX900 | 3.2MP (2048×1536) | Ultra-compact Automotive/AMR | *(Coming Soon)* | [👉 Intel Repo](https://github.com/otobrite-support/oToCAM278ISP_GMSL_IMX900_Intel) |

---

## 🛠️ Supported Compute Platforms

### NVIDIA Jetson
* **SoC Modules**: AGX Orin™, Orin™ NX, Orin™ Nano, AGX Xavier™
* **Supported JetPack**: JetPack 5.1.x (L4T R35.x) & JetPack 6.x (L4T R36.x)
* **Frameworks**: V4L2 kernel drivers, GStreamer, NVIDIA Argus / SIPL (on selected models)
* **Meta Repository**: [oToCAM_GMSL_nVidia](https://github.com/otobrite-support/oToCAM_GMSL_nVidia)

### Intel Architecture
* **Platforms**: Intel Core™ Processors (12th/13th/14th Gen), Intel Atom® x6000E Series
* **Interfaces**: PCIe / USB-to-GMSL Deserializers

---

## 🚀 Quick Verification Pipeline (NVIDIA Jetson)

Once drivers are installed according to the model's repository, you can quickly test live streaming using standard GStreamer pipelines:

```bash
# Example: 1920x1280 @ 30fps YUV preview on Jetson display
gst-launch-1.0 v4l2src device=/dev/video0 ! \
    "video/x-raw, width=1920, height=1280, format=UYVY, framerate=30/1" ! \
    nvvidconv ! "video/x-raw(memory:NVMM), format=NV12" ! \
    nv3dsink
```

---

## 📬 Technical Support & Sales

Need support for custom deserializer board integration, ISP tuning, or ROS/ROS2 nodes?

* 🌐 **Company Website**: [https://www.otobrite.com](https://www.otobrite.com)
* 📧 **Technical Support**: [support@otobrite.com](mailto:support@otobrite.com)
* 💼 **Sales & Commercial Inquiries**: [sales@otobrite.com](mailto:sales@otobrite.com)
