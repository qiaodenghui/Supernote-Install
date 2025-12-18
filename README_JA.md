# Supernote APK インストールツール

![Version](https://img.shields.io/badge/version-1.0-blue.svg)
![Platform](https://img.shields.io/badge/platform-Supernote-green.svg)

[English](./README.md) | [简体中文](./README_ZH-CN.md) | [繁體中文](./README_ZH-TW.md) | 日本語 | [한국어](./README_KO.md)

## 📖 プロジェクト概要

これは **Supernote** デバイス専用の APK インストールツールキットです。Supernote は APK ファイルを直接インストールできないため、ADB (Android Debug Bridge) ツールを使用してサイドロードする必要があります。

本プロジェクトでは、**Windows**、**Linux**、**Mac** の3つのシステムに対応した ADB ツールを用意しており、追加設定不要ですぐに使用できます！

---

## 🚀 3ステップで APK をインストール

### ステップ1：Supernote でサイドロード機能を有効にする

1. Supernote で **設定** を開く
2. **セキュリティとプライバシー** に移動
3. **サイドロード** (Sideload) オプションを有効にする

### ステップ2：Supernote をコンピュータに接続

1. USB データケーブルで Supernote をコンピュータに接続
2. Supernote にプロンプトが表示されたら、**OK** をタップして接続を許可

---

### ステップ3：ADB を使用して APK をインストール

#### Windows の場合：

1. 本プロジェクトから `platform-tools-latest-windows.zip` をダウンロードし、`C:\adb` に解凍
2. `Win + R` を押し、`cmd` と入力して Enter を押し、コマンドプロンプトを開く
3. 次のコマンドを入力して ADB ディレクトリに移動：
   ```cmd
   cd C:\adb\platform-tools
   ```
4. Supernote が接続されていることを確認：
   ```cmd
   adb devices
   ```
   デバイスのシリアル番号が表示されれば、接続成功です。

5. APK をインストール（パスを実際の APK ファイルの場所に置き換えてください）：
   ```cmd
   adb install "D:\Downloads\アプリ名.apk"
   ```

**クイック方法**：`adb install ` と入力した後、APK ファイルをコマンドウィンドウにドラッグし、Enter を押すだけです。

#### Mac の場合：

1. `platform-tools-latest-darwin.zip` をダウンロードして解凍
2. ターミナルを開き、解凍したディレクトリに移動：
   ```bash
   cd ~/Downloads/platform-tools
   ```
3. 実行権限を付与（初回のみ）：
   ```bash
   chmod +x adb
   ```
4. 接続を確認：
   ```bash
   ./adb devices
   ```
5. APK をインストール：
   ```bash
   ./adb install ~/Downloads/アプリ名.apk
   ```

#### Linux の場合：

1. `platform-tools-latest-linux.zip` をダウンロードして解凍
2. ターミナルを開き、解凍したディレクトリに移動
3. 実行権限を付与：
   ```bash
   chmod +x adb
   ```
4. 接続を確認：
   ```bash
   ./adb devices
   ```
5. APK をインストール：
   ```bash
   ./adb install ~/Downloads/アプリ名.apk
   ```

> ✅ **インストール完了！** Supernote のアプリリストで新しくインストールしたアプリを見つけることができます。

> 💡 **APK ダウンロード**：[APKMirror](https://www.apkmirror.com/) または [APKPure](https://apkpure.com/) からのダウンロードをお勧めします。

---

## 📚 よく使うコマンド

```bash
# 接続されているデバイスを表示
adb devices

# APK をインストール
adb install アプリ.apk

# 上書きインストール（アプリデータを保持）
adb install -r アプリ.apk

# アプリをアンインストール（パッケージ名が必要）
adb uninstall com.example.app

# Supernote にファイルを転送
adb push ファイル.pdf /sdcard/

# Supernote からファイルを取得
adb pull /sdcard/ファイル.pdf
```

---

## ❓ よくある質問

### Q1: `adb devices` でデバイスが表示されない
**解決方法**：
1. Supernote で「サイドロード」機能が有効になっていることを確認
2. USB ケーブルがデータケーブルであることを確認（充電専用ケーブルではない）
3. コンピュータの別の USB ポートを試す
4. Windows ユーザーはドライバのインストールが必要な場合があります（通常は自動的にインストールされます）

### Q2: インストール時に "INSTALL_FAILED_ALREADY_EXISTS" と表示される
**解決方法**：
`-r` パラメータを使用して上書きインストール：
```bash
adb install -r アプリ.apk
```

### Q3: アプリのインストールは成功したが見つからない
**解決方法**：
1. Supernote のアプリリストで確認
2. 数秒待つ、一部のアプリは表示に時間がかかります
3. Supernote を再起動してみる

### Q4: アプリが Supernote で正常に表示されない
**解決方法**：
1. E-ink ディスプレイはアニメーションのサポートが限られており、これは正常です
2. 読書/ノート専用に設計されたアプリの方が効果的です
3. アプリの設定でアニメーションをオフにする

### Q5: Mac/Linux で "Permission denied" と表示される
**解決方法**：
```bash
chmod +x adb
```

---

## 📝 説明

- ADB ツールは Google 公式の Android Platform Tools から提供されています
- 本プロジェクトは Supernote ユーザーの利便性のために整理されたものです
- 公式ダウンロード：https://developer.android.google.cn/tools/releases/platform-tools

## ⭐ 役に立ちましたか？

このプロジェクトがお役に立ちましたら、Star をつけてサポートしてください！

