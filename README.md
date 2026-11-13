# E3500 랜턴 안드로이드 앱

Capacitor 7 기반 Android 앱 프로젝트입니다. BLE 연결은 Android 네이티브 플러그인 `@capacitor-community/bluetooth-le`을 사용합니다.

## APK 빌드

GitHub 저장소의 **Actions** 탭에서 `Build APK` 워크플로를 실행하거나 `main` 브랜치에 push하면 APK 빌드가 시작됩니다. 완료 후 실행 결과의 **Artifacts → E3500-lantern-debug-apk**에서 APK를 받을 수 있습니다.

## PC에서 직접 빌드

필요 환경: Node.js 20 이상, JDK 21, Android SDK.

```bash
npm install
npm run android:init
cd android
./gradlew assembleDebug
```

APK 위치: `android/app/build/outputs/apk/debug/app-debug.apk`

## 앱 구성

- 앱 이름: E3500 랜턴
- 패키지 ID: `com.e3500.lantern`
- BLE: 랜턴 검색, 연결/해제, 전원, 밝기, 색온도, 장면, 호흡/점멸, 소등 타이머, 2대 동시 제어
- Android BLE 권한: AndroidManifest에 자동 추가

실제 랜턴과의 최종 호환성은 설치 후 기기 연결 및 각 기능을 직접 시험해야 합니다. Android SDK/Gradle 빌드와 실기기 BLE 통신은 아직 검증되지 않았습니다.
