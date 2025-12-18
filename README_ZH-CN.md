# Supernote APK 安装工具

![Version](https://img.shields.io/badge/version-1.0-blue.svg)
![Platform](https://img.shields.io/badge/platform-Supernote-green.svg)

[English](./README.md) | 简体中文 | [繁體中文](./README_ZH-TW.md) | [日本語](./README_JA.md) | [한국어](./README_KO.md)

## 📖 项目简介

这是一个专门为 **Supernote** 设备准备的 APK 安装工具包。Supernote 无法直接安装 APK 文件，需要通过 ADB (Android Debug Bridge) 工具进行侧载安装。

本项目已为您准备好适用于 **Windows**、**Linux**、**Mac** 三种系统的 ADB 工具，开箱即用，无需额外配置！

---

## � 三步安装 APK

### 第一步：Supernote 开启侧载功能

1. 在 Supernote 上打开 **设置**
2. 进入 **安全和隐私**
3. 开启 **侧载** (Sideload) 选项

### 第二步：连接 Supernote 到电脑

1. 使用 USB 数据线将 Supernote 连接到电脑
2. 如果 Supernote 弹出提示，点击 **确定** 允许连接

---

### 第三步：使用 ADB 安装 APK

#### Windows 系统：

1. 下载本项目中的 `platform-tools-latest-windows.zip` 并解压到 `C:\adb`
2. 按 `Win + R`，输入 `cmd`，按回车打开命令提示符
3. 输入以下命令进入 ADB 目录：
   ```cmd
   cd C:\adb\platform-tools
   ```
4. 验证 Supernote 已连接：
   ```cmd
   adb devices
   ```
   如果显示设备序列号，说明连接成功。

5. 安装 APK（将路径替换为您的 APK 文件位置）：
   ```cmd
   adb install "D:\Downloads\应用名称.apk"
   ```

**快捷方法**：输入 `adb install ` 后，直接将 APK 文件拖入命令窗口，按回车即可。

#### Mac 系统：

1. 下载 `platform-tools-latest-darwin.zip` 并解压
2. 打开终端，进入解压目录：
   ```bash
   cd ~/Downloads/platform-tools
   ```
3. 赋予执行权限（仅首次需要）：
   ```bash
   chmod +x adb
   ```
4. 验证连接：
   ```bash
   ./adb devices
   ```
5. 安装 APK：
   ```bash
   ./adb install ~/Downloads/应用名称.apk
   ```

#### Linux 系统：

1. 下载 `platform-tools-latest-linux.zip` 并解压
2. 打开终端，进入解压目录
3. 赋予执行权限：
   ```bash
   chmod +x adb
   ```
4. 验证连接：
   ```bash
   ./adb devices
   ```
5. 安装 APK：
   ```bash
   ./adb install ~/Downloads/应用名称.apk
   ```

> ✅ **安装成功！** 在 Supernote 的应用列表中即可找到新安装的应用。

> 💡 **APK 下载**：推荐从 [APKMirror](https://www.apkmirror.com/) 或 [APKPure](https://apkpure.com/) 下载。

---

## 📚 常用命令

```bash
# 查看已连接的设备
adb devices

# 安装 APK
adb install 应用.apk

# 覆盖安装（保留应用数据）
adb install -r 应用.apk

# 卸载应用（需要包名）
adb uninstall com.example.app

# 传文件到 Supernote
adb push 文件.pdf /sdcard/

# 从 Supernote 拉取文件
adb pull /sdcard/文件.pdf
```

---

## ❓ 常见问题

### Q1: `adb devices` 没有显示设备
**解决方法**：
1. 确认 Supernote 已开启"侧载"功能
2. 检查 USB 线是否为数据线（不是仅充电线）
3. 更换电脑的 USB 接口试试
4. Windows 用户可能需要安装驱动（通常会自动安装）

### Q2: 安装时提示 "INSTALL_FAILED_ALREADY_EXISTS"
**解决方法**：
使用 `-r` 参数覆盖安装：
```bash
adb install -r 应用.apk
```

### Q3: 应用安装成功但找不到
**解决方法**：
1. 在 Supernote 应用列表中查找
2. 等待几秒钟，有些应用需要时间显示
3. 尝试重启 Supernote

### Q4: 应用在 Supernote 上显示异常
**解决方法**：
1. 墨水屏对动画支持有限，这是正常现象
2. 选择专为阅读/笔记设计的应用效果更好
3. 在应用设置中关闭动画效果

### Q5: Mac/Linux 提示 "Permission denied"
**解决方法**：
```bash
chmod +x adb
```

---

## � 说明

- ADB 工具来自 Google 官方 Android Platform Tools
- 本项目仅为方便 Supernote 用户使用而整理
- 官方下载地址：https://developer.android.google.cn/tools/releases/platform-tools

## ⭐ 觉得有用？

如果这个项目帮助到了您，请给个 Star 支持一下！

