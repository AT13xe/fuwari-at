---
title: 什么是AOSP
published: 2025-11-15
description: 一个介绍AOSP的文档
tags:
  - Android
  - AOSP
draft: false
pinned: true
lang: ""
---
# AOSP（Android Open Source Project）介绍

## 定义

**AOSP（Android Open Source Project）是由 Google 主导维护的 Android 操作系统完整开源工程。**

它包含构建 Android 平台所需的全部基础组件，包括：

- 系统框架（Framework）
- Android Runtime（ART）
- 硬件抽象层（HAL）
- Native 系统服务
- 系统应用
- 构建工具链
- 测试与兼容性体系

AOSP 是所有商业 Android 系统（如 MIUI、ColorOS、OneUI 等）的基础参考实现。

---

## AOSP 的结构与关键组成

### Framework 层（Java/Kotlin）

Framework 是 Android 的高层系统框架，提供应用开发者使用的主要 API，包括：

- 四大组件模型（Activity / Service / BroadcastReceiver / ContentProvider）
- ActivityManager、WindowManager、PackageManager 等核心系统服务
- 权限模型与安全策略
- UI 渲染与视图系统
- 通知、资源管理、多任务调度

Framework 是 Android 上层应用与系统进行交互的主要入口。

---

### Native 层（C/C++ 系统组件）

Native 层负责性能关键的系统功能，包括：

- **Binder IPC**：Android 的核心进程间通信机制
- **SurfaceFlinger**：图形合成器，负责显示渲染
- **AudioFlinger**：音频混合与输出
- **Media Framework**：多媒体解码、编码、播放链路
- **ART（Android Runtime）**：Java 字节码执行（解释器 / JIT / AOT）

Native 层为 Framework 提供底层支持，负责系统运行效率。

---

### HAL（Hardware Abstraction Layer）

HAL 提供统一的硬件抽象接口，使 Android 能在不同硬件平台运行。

典型 HAL 模块包括：

- Camera HAL  
- GPS HAL  
- Sensor HAL  
- Bluetooth / Wi-Fi HAL  
- Audio HAL  

设备厂商必须基于这些接口开发对应硬件驱动实现。

---

### 系统应用（System Apps）

AOSP 提供默认的基础系统应用，例如：

- Launcher3（默认桌面）
- Settings（设置）
- SystemUI（通知栏、状态栏、导航栏）
- 电话、短信、联系人
- 时钟、输入法等基础组件

这些应用作为 Android 的最小可运行系统的标准实现。

---

### 构建系统（Build System）

AOSP 提供完整且跨平台的系统构建链，包括：

- **Soong + Ninja**：主构建系统
- **Make（遗留部分）**
- **Clang/LLVM**：官方编译器
- **镜像构建工具**：生成 boot.img、system.img、vendor.img 等

这些工具将整个 AOSP 源码编译为可刷入设备的系统镜像。

---

### 兼容性测试体系

AOSP 提供 Android 生态兼容性标准，包括：

- **CTS（Compatibility Test Suite）**
- **VTS（Vendor Test Suite）**
- **GTS（Google Test Suite）**

用于验证 ROM 与 Android 生态系统的兼容性与一致性。

---

## AOSP 的价值与定位

AOSP 的核心目标包括：

1. **提供 Android 的官方开源参考实现**
2. **支持设备厂商、ROM 开发者、研究人员构建和修改 Android 系统**
3. **维持 Android 生态的兼容性与开放性**
4. **支持手机、平板、车机、TV、可穿戴等多类设备的系统开发**
5. **推动 Android 持续演进、创新与安全升级**

---

## 为什么原生 AOSP 不能直接运行在普通手机上？

AOSP 并不包含以下内容：

- SoC 厂商专用内核（如 Qualcomm、MTK）
- 摄像头、GPU、基带等硬件驱动（闭源）
- 厂商专用 HAL 实现
- Google 服务框架（GMS）
- 性能、电池、系统级优化

因此，厂商必须提供：

- **Device Tree（设备描述信息）**
- **内核源码（Kernel Source）**
- **Vendor Blobs（驱动与固件）**
- **自定义系统优化与 UI**

才能构建出能够在真实设备运行的 Android 系统。

---

## 总结

**AOSP 是 Android 平台的核心开源基础架构，定义了 Android 的完整系统模型与标准实现，是所有商业 Android 版本的根源与技术基础。**

它不仅是一个操作系统源码库，更是整个 Android 生态运行的技术基石。


---

# 相关链接

[AOSP官网](https://source.android.com/?hl=zh-cn)