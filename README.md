# Supernote APK Installation Tool

![Version](https://img.shields.io/badge/version-1.0-blue.svg)
![Platform](https://img.shields.io/badge/platform-Supernote-green.svg)

English | [简体中文](./README_ZH-CN.md) | [繁體中文](./README_ZH-TW.md) | [日本語](./README_JA.md) | [한국어](./README_KO.md)

## 📖 Introduction

This is an APK installation toolkit specifically designed for **Supernote** devices. Supernote cannot directly install APK files and requires sideloading via ADB (Android Debug Bridge) tool.

This project provides ready-to-use ADB tools for **Windows**, **Linux**, and **Mac** systems, no additional configuration needed!

---

## 🚀 Install APK in 3 Steps

### Step 1: Enable Sideload on Supernote

1. Open **Settings** on your Supernote
2. Navigate to **Security and Privacy**
3. Enable **Sideload** option

### Step 2: Connect Supernote to Computer

1. Use a USB data cable to connect Supernote to your computer
2. If Supernote shows a prompt, tap **OK** to allow the connection
---

### Step 3: Install APK Using ADB

#### For Windows:

1. Download `platform-tools-latest-windows.zip` from this project and extract to `C:\adb`
2. Press `Win + R`, type `cmd`, press Enter to open Command Prompt
3. Enter the following command to navigate to ADB directory:
   ```cmd
   cd C:\adb\platform-tools
   ```
4. Verify Supernote is connected:
   ```cmd
   adb devices
   ```
   If it shows the device serial number, connection is successful.

5. Install APK (replace the path with your APK file location):
   ```cmd
   adb install "D:\Downloads\AppName.apk"
   ```

**Quick Method**: Type `adb install ` then drag the APK file into the command window and press Enter.

#### For Mac:

1. Download `platform-tools-latest-darwin.zip` and extract
2. Open Terminal and navigate to the extracted directory:
   ```bash
   cd ~/Downloads/platform-tools
   ```
3. Grant execute permission (first time only):
   ```bash
   chmod +x adb
   ```
4. Verify connection:
   ```bash
   ./adb devices
   ```
5. Install APK:
   ```bash
   ./adb install ~/Downloads/AppName.apk
   ```

#### For Linux:

1. Download `platform-tools-latest-linux.zip` and extract
2. Open Terminal and navigate to the extracted directory
3. Grant execute permission:
   ```bash
   chmod +x adb
   ```
4. Verify connection:
   ```bash
   ./adb devices
   ```
5. Install APK:
   ```bash
   ./adb install ~/Downloads/AppName.apk
   ```

> ✅ **Installation Complete!** You can find the newly installed app in Supernote's app list.

> 💡 **APK Download**: Recommended sources are [APKMirror](https://www.apkmirror.com/) or [APKPure](https://apkpure.com/).

---

## 📚 Common Commands

```bash
# View connected devices
adb devices

# Install APK
adb install app.apk

# Reinstall (keep app data)
adb install -r app.apk

# Uninstall app (requires package name)
adb uninstall com.example.app

# Transfer file to Supernote
adb push file.pdf /sdcard/

# Pull file from Supernote
adb pull /sdcard/file.pdf
```

---

## ❓ FAQ

### Q1: `adb devices` shows no devices
**Solution**:
1. Confirm Supernote has "Sideload" enabled
2. Check if USB cable is a data cable (not charge-only)
3. Try a different USB port on your computer
4. Windows users may need to install drivers (usually automatic)

### Q2: Installation fails with "INSTALL_FAILED_ALREADY_EXISTS"
**Solution**:
Use the `-r` parameter to reinstall:
```bash
adb install -r app.apk
```

### Q3: App installed successfully but can't find it
**Solution**:
1. Check Supernote's app list
2. Wait a few seconds, some apps need time to appear
3. Try restarting Supernote

### Q4: App looks strange on Supernote
**Solution**:
1. E-ink has limited animation support, this is normal
2. Apps designed for reading/note-taking work better
3. Turn off animations in app settings

### Q5: Mac/Linux shows "Permission denied"
**Solution**:
```bash
chmod +x adb
```

---

## 📝 Notes

- ADB tools are from Google's official Android Platform Tools
- This project is organized for the convenience of Supernote users
- Official download: https://developer.android.google.cn/tools/releases/platform-tools

## ⭐ Find This Useful?

If this project helped you, please give it a Star to show your support!


