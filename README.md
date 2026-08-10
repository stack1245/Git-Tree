# Git Tree

[![Release](https://img.shields.io/github/v/release/stack1245/Git-Tree?display_name=tag&sort=semver)](https://github.com/stack1245/Git-Tree/releases/latest)
![Windows](https://img.shields.io/badge/Windows-x86__64-0078D4?logo=windows11&logoColor=white)
![macOS](https://img.shields.io/badge/macOS-arm64%20%7C%20x86__64-000000?logo=apple&logoColor=white)
[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-red.svg)](LICENSE)

Git Tree는 원격 Git 저장소의 모든 브랜치를 브랜치 이름과 같은 로컬 폴더 계층에 각각 독립된 worktree로 구성하고 동기화하는 Windows·macOS 데스크톱 앱입니다.

이 저장소는 **공식 실행 파일 배포 전용**이며 소스 코드를 포함하지 않습니다.

## 다운로드

현재 정식 버전은 **1.1.0**입니다.

| 대상 | 다운로드 |
| --- | --- |
| Windows x86_64 | [`Git-Tree-v1.1.0-Windows-x86_64.exe`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-v1.1.0-Windows-x86_64.exe) |
| macOS Apple Silicon | [`Git-Tree-v1.1.0-macOS-arm64.dmg`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-v1.1.0-macOS-arm64.dmg) |
| macOS Intel | [`Git-Tree-v1.1.0-macOS-x86_64.dmg`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-v1.1.0-macOS-x86_64.dmg) |
| SHA-256 체크섬 | [`Git-Tree-v1.1.0-SHA256SUMS.txt`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-v1.1.0-SHA256SUMS.txt) |

앱을 실행할 컴퓨터에는 [Git](https://git-scm.com/downloads)이 설치되어 있어야 합니다.

## 안전한 동기화

1.1.0부터 로컬 수정·미추적·무시 파일은 기본적으로 보호됩니다. 로컬 변경이 발견되면 동기화를 중단하며, 사용자가 **ZIP 백업 후 삭제**에 명시적으로 동의한 경우에만 원격 상태로 정리합니다. 백업 ZIP의 무결성과 백업 직후 파일 상태가 확인되기 전에는 삭제 작업을 시작하지 않습니다.

중요한 작업은 동기화 전에 커밋하거나 별도 위치에도 보관하는 것을 권장합니다.

## macOS에서 처음 실행하기

DMG를 열고 `GitTree.app`을 `Applications`로 드래그합니다. 앱은 Apple 공증을 받지 않았으므로 처음 차단되면 Finder의 응용 프로그램 폴더에서 `GitTree.app`을 Control-클릭한 뒤 **열기**를 선택하세요.

## 라이선스

Git Tree는 공개 소프트웨어가 아닙니다. Copyright (c) 2026 stack1245. All rights reserved.

승인된 사용자는 [독점 소프트웨어 사용권 계약](LICENSE)의 범위 안에서 컴파일된 앱을 내부 용도로 사용할 수 있습니다. 소스 코드의 공개·복제·수정·재배포·재판매와 법이 허용하는 범위를 벗어난 역공학은 금지됩니다.
