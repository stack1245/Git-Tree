# Git Tree

[![Release](https://img.shields.io/github/v/release/stack1245/Git-Tree?display_name=tag&sort=semver)](https://github.com/stack1245/Git-Tree/releases/latest)
![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![PyQt6](https://img.shields.io/badge/PyQt6-6.7%2B-41CD52?logo=qt&logoColor=white)
![Git](https://img.shields.io/badge/Git-required-F05032?logo=git&logoColor=white)
![PyInstaller](https://img.shields.io/badge/PyInstaller-6.21%2B-FFDC80?logo=python&logoColor=black)
![Inno Setup](https://img.shields.io/badge/Inno%20Setup-6-264B99?logo=windows&logoColor=white)
![Ed25519](https://img.shields.io/badge/Updates-Ed25519%20signed-6A5ACD)
![Windows](https://img.shields.io/badge/Windows-x86__64-0078D4?logo=windows11&logoColor=white)
![macOS](https://img.shields.io/badge/macOS-arm64%20%7C%20x86__64-000000?logo=apple&logoColor=white)
[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-red.svg)](LICENSE)

Git Tree는 원격 Git 저장소의 모든 브랜치를 브랜치 이름과 같은 로컬 폴더 계층에 각각 독립된 worktree로 구성하고 동기화하는 Windows·macOS 데스크톱 앱입니다.

이 저장소는 **공식 실행 파일 배포 전용**이며 소스 코드를 포함하지 않습니다.

## 다운로드

현재 정식 버전은 **1.0.1**입니다.

다운로드 파일명은 버전과 무관하게 고정되므로 다음 릴리스에서도 같은 최신 다운로드 링크를 사용할 수 있습니다.

| 대상 | 다운로드 |
| --- | --- |
| Windows x86_64 installer | [`Git-Tree-Windows-x86_64-Setup.exe`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-Windows-x86_64-Setup.exe) |
| macOS Apple Silicon installer | [`Git-Tree-macOS-arm64.pkg`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-macOS-arm64.pkg) |
| macOS Intel installer | [`Git-Tree-macOS-x86_64.pkg`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-macOS-x86_64.pkg) |
| SHA-256 체크섬 | [`Git-Tree-SHA256SUMS.txt`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-SHA256SUMS.txt) |

앱을 실행할 컴퓨터에는 [Git](https://git-scm.com/downloads)이 설치되어 있어야 합니다.

## 안전한 동기화

로컬 수정·미추적·무시 파일은 기본적으로 보호됩니다. 로컬 변경이 발견되면 동기화를 중단하며, 사용자가 **ZIP 백업 후 삭제**에 명시적으로 동의한 경우에만 원격 상태로 정리합니다. 백업 ZIP의 무결성과 백업 직후 파일 상태가 확인되기 전에는 삭제 작업을 시작하지 않습니다.

1.0.1부터 백업 전 저장 공간과 파일 읽기 가능 여부를 확인하고, Next.js·Git 작업 잠금, 동시 변경, 심볼릭 링크·Windows 정션, 파이프·소켓·장치 같은 특수 파일을 안전하게 처리합니다. 알 수 없는 상태는 건너뛰지 않고 삭제 전에 중단합니다.

다시 만들 수 있는 웹·Python·Dart·Gradle·Terraform·CMake·Cargo·Maven·sbt·Swift·.NET·Xcode 생성물만 보수적으로 ZIP에서 제외합니다. `.env`, 미추적 소스, `dist`, `coverage`와 문맥이 불분명한 `build`·`target`·`bin`·`obj`는 계속 백업합니다.

중요한 작업은 동기화 전에 커밋하거나 별도 위치에도 보관하는 것을 권장합니다.

## v1.0.1 패치노트

- 여러 개발 생태계의 확실한 생성물을 분류해 대용량 캐시와 파일 잠금으로 인한 백업 실패를 줄였습니다.
- 사용자 파일·`.env`·미추적·무시 파일은 계속 ZIP에 보관하며, 심볼릭 링크는 외부 내용을 따라가지 않고 링크 자체로 저장합니다.
- 저장 공간 부족, 읽기 권한, 배타 잠금, 파일 교체·동시 변경, 특수 파일과 진행 중인 Git 작업을 삭제 전에 감지합니다.
- 원격 미러 적용이나 워크트리 제거가 실패하면 생성된 ZIP 위치와 원인을 안내합니다.
- Windows 실행 파일·installer·시작 메뉴·바탕 화면 바로 가기와 macOS 앱 번들에 동일한 다중 해상도 Git Tree 아이콘을 적용했습니다.

## 설치와 업데이트

Windows Setup은 기본적으로 `%LOCALAPPDATA%\Programs\Git Tree`에 설치되고 시작 메뉴와 **설정 → 앱 → 설치된 앱**에 등록됩니다. macOS PKG는 `/Applications/GitTree.app`에 설치되고 패키지 receipt를 등록합니다.

Git Tree 1.0.0부터 화면 오른쪽 위의 **업데이트 확인**으로 새 버전을 받을 수 있으며, 앱 실행 후 하루 한 번 자동 확인도 수행합니다. 업데이트 정보의 Ed25519 서명과 installer의 공식 GitHub 주소, 파일명, 크기, SHA-256을 모두 검증한 뒤 운영체제 installer를 엽니다.

1.0.0은 운영체제 installer와 앱 내 업데이트를 포함한 첫 정식 배포이며, 1.0.1은 기존 설치 앱에서 바로 확인하고 내려받을 수 있는 첫 패치입니다.

## macOS에서 처음 설치하기

PKG와 앱은 Apple Developer ID로 서명하거나 공증하지 않았습니다. 차단되면 먼저 PKG를 한 번 연 뒤 **시스템 설정 → 개인정보 보호 및 보안**에서 **확인 없이 열기**를 선택하세요. 설치 후 앱이 차단될 때도 같은 화면에서 허용할 수 있습니다. 공식 릴리스와 SHA-256을 확인한 파일에만 이 예외를 적용하세요.

## 라이선스

Git Tree는 공개 소프트웨어가 아닙니다. Copyright (c) 2026 stack1245. All rights reserved.

승인된 사용자는 [독점 소프트웨어 사용권 계약](LICENSE)의 범위 안에서 컴파일된 앱을 내부 용도로 사용할 수 있습니다. 소스 코드의 공개·복제·수정·재배포·재판매와 법이 허용하는 범위를 벗어난 역공학은 금지됩니다.
