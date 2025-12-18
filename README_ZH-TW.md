# Supernote APK 安裝工具

![Version](https://img.shields.io/badge/version-1.0-blue.svg)
![Platform](https://img.shields.io/badge/platform-Supernote-green.svg)

[English](./README.md) | [简体中文](./README_ZH-CN.md) | 繁體中文 | [日本語](./README_JA.md) | [한국어](./README_KO.md)

## 📖 專案簡介

這是一個專門為 **Supernote** 裝置準備的 APK 安裝工具包。Supernote 無法直接安裝 APK 檔案，需要透過 ADB (Android Debug Bridge) 工具進行側載安裝。

本專案已為您準備好適用於 **Windows**、**Linux**、**Mac** 三種系統的 ADB 工具，開箱即用，無需額外設定！

---

## 🚀 三步安裝 APK

### 第一步：Supernote 開啟側載功能

1. 在 Supernote 上打開 **設定**
2. 進入 **安全和隱私**
3. 開啟 **側載** (Sideload) 選項

### 第二步：連接 Supernote 到電腦

1. 使用 USB 資料線將 Supernote 連接到電腦
2. 如果 Supernote 彈出提示，點擊 **確定** 允許連接

---

### 第三步：使用 ADB 安裝 APK

#### Windows 系統：

1. 下載本專案中的 `platform-tools-latest-windows.zip` 並解壓到 `C:\adb`
2. 按 `Win + R`，輸入 `cmd`，按 Enter 打開命令提示字元
3. 輸入以下命令進入 ADB 目錄：
   ```cmd
   cd C:\adb\platform-tools
   ```
4. 驗證 Supernote 已連接：
   ```cmd
   adb devices
   ```
   如果顯示裝置序號，說明連接成功。

5. 安裝 APK（將路徑替換為您的 APK 檔案位置）：
   ```cmd
   adb install "D:\Downloads\應用名稱.apk"
   ```

**快捷方法**：輸入 `adb install ` 後，直接將 APK 檔案拖入命令視窗，按 Enter 即可。

#### Mac 系統：

1. 下載 `platform-tools-latest-darwin.zip` 並解壓
2. 打開終端機，進入解壓目錄：
   ```bash
   cd ~/Downloads/platform-tools
   ```
3. 賦予執行權限（僅首次需要）：
   ```bash
   chmod +x adb
   ```
4. 驗證連接：
   ```bash
   ./adb devices
   ```
5. 安裝 APK：
   ```bash
   ./adb install ~/Downloads/應用名稱.apk
   ```

#### Linux 系統：

1. 下載 `platform-tools-latest-linux.zip` 並解壓
2. 打開終端機，進入解壓目錄
3. 賦予執行權限：
   ```bash
   chmod +x adb
   ```
4. 驗證連接：
   ```bash
   ./adb devices
   ```
5. 安裝 APK：
   ```bash
   ./adb install ~/Downloads/應用名稱.apk
   ```

> ✅ **安裝成功！** 在 Supernote 的應用程式清單中即可找到新安裝的應用程式。

> 💡 **APK 下載**：推薦從 [APKMirror](https://www.apkmirror.com/) 或 [APKPure](https://apkpure.com/) 下載。

---

## 📚 常用命令

```bash
# 查看已連接的裝置
adb devices

# 安裝 APK
adb install 應用.apk

# 覆蓋安裝（保留應用程式資料）
adb install -r 應用.apk

# 解除安裝應用程式（需要套件名稱）
adb uninstall com.example.app

# 傳檔案到 Supernote
adb push 檔案.pdf /sdcard/

# 從 Supernote 拉取檔案
adb pull /sdcard/檔案.pdf
```

---

## ❓ 常見問題

### Q1: `adb devices` 沒有顯示裝置
**解決方法**：
1. 確認 Supernote 已開啟「側載」功能
2. 檢查 USB 線是否為資料線（不是僅充電線）
3. 更換電腦的 USB 連接埠試試
4. Windows 使用者可能需要安裝驅動程式（通常會自動安裝）

### Q2: 安裝時提示 "INSTALL_FAILED_ALREADY_EXISTS"
**解決方法**：
使用 `-r` 參數覆蓋安裝：
```bash
adb install -r 應用.apk
```

### Q3: 應用程式安裝成功但找不到
**解決方法**：
1. 在 Supernote 應用程式清單中查找
2. 等待幾秒鐘，有些應用程式需要時間顯示
3. 嘗試重新啟動 Supernote

### Q4: 應用程式在 Supernote 上顯示異常
**解決方法**：
1. 墨水屏對動畫支援有限，這是正常現象
2. 選擇專為閱讀/筆記設計的應用程式效果更好
3. 在應用程式設定中關閉動畫效果

### Q5: Mac/Linux 提示 "Permission denied"
**解決方法**：
```bash
chmod +x adb
```

---

## 📝 說明

- ADB 工具來自 Google 官方 Android Platform Tools
- 本專案僅為方便 Supernote 使用者使用而整理
- 官方下載地址：https://developer.android.google.cn/tools/releases/platform-tools

## ⭐ 覺得有用？

如果這個專案幫助到了您，請給個 Star 支持一下！

