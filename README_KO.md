# Supernote APK 설치 도구

![Version](https://img.shields.io/badge/version-1.0-blue.svg)
![Platform](https://img.shields.io/badge/platform-Supernote-green.svg)

[English](./README.md) | [简体中文](./README_ZH-CN.md) | [繁體中文](./README_ZH-TW.md) | [日本語](./README_JA.md) | 한국어

## 📖 프로젝트 소개

이것은 **Supernote** 기기 전용 APK 설치 도구 키트입니다. Supernote는 APK 파일을 직접 설치할 수 없으므로 ADB (Android Debug Bridge) 도구를 사용하여 사이드로드해야 합니다.

본 프로젝트는 **Windows**, **Linux**, **Mac** 세 가지 시스템에 적합한 ADB 도구를 제공하며, 추가 설정 없이 바로 사용할 수 있습니다!

---

## 🚀 3단계로 APK 설치하기

### 1단계: Supernote에서 사이드로드 기능 활성화

1. Supernote에서 **설정** 열기
2. **보안 및 개인정보** 이동
3. **사이드로드** (Sideload) 옵션 활성화

### 2단계: Supernote를 컴퓨터에 연결

1. USB 데이터 케이블로 Supernote를 컴퓨터에 연결
2. Supernote에 프롬프트가 표시되면 **확인**을 눌러 연결 허용

---

### 3단계: ADB를 사용하여 APK 설치

#### Windows의 경우:

1. 본 프로젝트에서 `platform-tools-latest-windows.zip`을 다운로드하고 `C:\adb`에 압축 해제
2. `Win + R`을 누르고 `cmd`를 입력한 후 Enter를 눌러 명령 프롬프트 열기
3. 다음 명령을 입력하여 ADB 디렉토리로 이동:
   ```cmd
   cd C:\adb\platform-tools
   ```
4. Supernote가 연결되었는지 확인:
   ```cmd
   adb devices
   ```
   기기 일련번호가 표시되면 연결 성공입니다.

5. APK 설치 (경로를 실제 APK 파일 위치로 변경):
   ```cmd
   adb install "D:\Downloads\앱이름.apk"
   ```

**빠른 방법**: `adb install ` 입력 후 APK 파일을 명령 창으로 드래그하고 Enter를 누르면 됩니다.

#### Mac의 경우:

1. `platform-tools-latest-darwin.zip`을 다운로드하고 압축 해제
2. 터미널을 열고 압축 해제한 디렉토리로 이동:
   ```bash
   cd ~/Downloads/platform-tools
   ```
3. 실행 권한 부여 (처음만):
   ```bash
   chmod +x adb
   ```
4. 연결 확인:
   ```bash
   ./adb devices
   ```
5. APK 설치:
   ```bash
   ./adb install ~/Downloads/앱이름.apk
   ```

#### Linux의 경우:

1. `platform-tools-latest-linux.zip`을 다운로드하고 압축 해제
2. 터미널을 열고 압축 해제한 디렉토리로 이동
3. 실행 권한 부여:
   ```bash
   chmod +x adb
   ```
4. 연결 확인:
   ```bash
   ./adb devices
   ```
5. APK 설치:
   ```bash
   ./adb install ~/Downloads/앱이름.apk
   ```

> ✅ **설치 완료!** Supernote의 앱 목록에서 새로 설치한 앱을 찾을 수 있습니다.

> 💡 **APK 다운로드**: [APKMirror](https://www.apkmirror.com/) 또는 [APKPure](https://apkpure.com/)에서 다운로드하는 것을 권장합니다.

---

## 📚 자주 사용하는 명령어

```bash
# 연결된 기기 확인
adb devices

# APK 설치
adb install 앱.apk

# 덮어쓰기 설치 (앱 데이터 유지)
adb install -r 앱.apk

# 앱 제거 (패키지 이름 필요)
adb uninstall com.example.app

# Supernote로 파일 전송
adb push 파일.pdf /sdcard/

# Supernote에서 파일 가져오기
adb pull /sdcard/파일.pdf
```

---

## ❓ 자주 묻는 질문

### Q1: `adb devices`에 기기가 표시되지 않음
**해결 방법**:
1. Supernote에서 "사이드로드" 기능이 활성화되어 있는지 확인
2. USB 케이블이 데이터 케이블인지 확인 (충전 전용 케이블이 아님)
3. 컴퓨터의 다른 USB 포트 시도
4. Windows 사용자는 드라이버 설치가 필요할 수 있습니다 (일반적으로 자동 설치됨)

### Q2: 설치 시 "INSTALL_FAILED_ALREADY_EXISTS" 오류
**해결 방법**:
`-r` 매개변수를 사용하여 덮어쓰기 설치:
```bash
adb install -r 앱.apk
```

### Q3: 앱 설치는 성공했지만 찾을 수 없음
**해결 방법**:
1. Supernote 앱 목록에서 확인
2. 몇 초 기다리기, 일부 앱은 표시되는 데 시간이 걸림
3. Supernote 재시작 시도

### Q4: 앱이 Supernote에서 비정상적으로 표시됨
**해결 방법**:
1. E-ink 디스플레이는 애니메이션 지원이 제한적이며 이는 정상입니다
2. 독서/노트 전용으로 설계된 앱이 더 효과적입니다
3. 앱 설정에서 애니메이션 끄기

### Q5: Mac/Linux에서 "Permission denied" 오류
**해결 방법**:
```bash
chmod +x adb
```

---

## 📝 설명

- ADB 도구는 Google 공식 Android Platform Tools에서 제공됩니다
- 본 프로젝트는 Supernote 사용자의 편의를 위해 정리된 것입니다
- 공식 다운로드: https://developer.android.google.cn/tools/releases/platform-tools

## ⭐ 유용하셨나요?

이 프로젝트가 도움이 되셨다면 Star를 눌러 지원해 주세요!


