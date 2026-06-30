# woolim

## 프로젝트 소개

울림(woolim)은 구음장애인의 의사소통을 돕기 위한 AI 기반 음성 교정 앱입니다.

사용자가 발음이 부정확하거나 어눌한 음성을 녹음하면, 앱이 해당 음성을 서버로 전송하고 Whisper 기반 AI 모델이 이를 인식하여 더 명확한 문장으로 교정합니다. 이후 교정된 문장을 화면에 보여주고, 필요할 경우 TTS 기능을 통해 음성으로 출력할 수 있습니다.

본 프로젝트는 뇌졸중, 뇌병변 장애, 파킨슨병, 루게릭병, 청각 장애를 동반한 구음장애인 등 의사소통에 어려움을 겪는 사용자를 대상으로 하며, 자신의 의사를 보다 정확하게 전달할 수 있도록 돕는 것을 목표로 합니다.

## 시스템 흐름

```text
사용자 음성 녹음
        ↓
Flutter 앱에서 음성 데이터를 서버로 전송
        ↓
서버에서 Whisper 기반 AI 모델에 음성 전달
        ↓
AI 모델이 음성을 텍스트로 변환
        ↓
부정확한 발화를 더 명확한 문장으로 교정
        ↓
원문과 교정문을 앱 화면에 표시
        ↓
저장 / 검색 / 즐겨찾기 / TTS 기능 활용

## 폴더 구조

```text
woolim
├── android/                  # Android 앱 실행 및 빌드 관련 설정
├── ios/                      # iOS 앱 실행 및 빌드 관련 설정
├── lib/                      # Flutter 앱 주요 소스 코드
│   └── main.dart             # 앱 실행 진입점 및 주요 화면 구성
├── linux/                    # Linux 실행 환경 관련 파일
├── macos/                    # macOS 실행 환경 관련 파일
├── windows/                  # Windows 실행 환경 관련 파일
├── test/                     # 테스트 코드
├── pubspec.yaml              # Flutter 프로젝트 설정 및 패키지 의존성 관리
├── pubspec.lock              # 설치된 패키지 버전 정보
└── README.md                 # 프로젝트 설명 문서
```

## 실행 방법

본 프로젝트는 **Android Studio에서 Android 기기를 연결하여 실행**했습니다.

1. Android Studio에서 프로젝트를 엽니다.

2. Terminal에서 패키지를 설치합니다.

```bash
flutter pub get
```

3. Android 휴대폰의 **개발자 옵션**과 **USB 디버깅**을 켠 뒤, USB 케이블로 PC와 연결합니다.

4. 연결된 기기를 확인합니다.

```bash
flutter devices
```

5. Android 기기에서 앱을 실행합니다.

```bash
flutter run
```

또는 Android Studio 상단에서 Android 기기를 선택한 뒤 **Run ▶** 버튼을 눌러 실행합니다.

6. APK 파일이 필요한 경우 아래 명령어로 빌드합니다.

```bash
flutter build apk
```

APK 생성 경로는 다음과 같습니다.

```text
build/app/outputs/flutter-apk/app-release.apk
```
