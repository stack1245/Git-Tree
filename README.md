# Git Tree

[![Release](https://img.shields.io/github/v/release/stack1245/Git-Tree?display_name=tag&sort=semver)](https://github.com/stack1245/Git-Tree/releases/latest)
![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![PyQt6](https://img.shields.io/badge/PyQt6-6.7%2B-41CD52?logo=qt&logoColor=white)
![Git](https://img.shields.io/badge/Git-required-F05032?logo=git&logoColor=white)
![MCP](https://img.shields.io/badge/MCP-2.x-6C47FF)
![Ed25519](https://img.shields.io/badge/Updates-Ed25519%20signed-6A5ACD)
![Windows](https://img.shields.io/badge/Windows-x86__64-0078D4?logo=windows11&logoColor=white)
![macOS](https://img.shields.io/badge/macOS-arm64%20%7C%20x86__64-000000?logo=apple&logoColor=white)
[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-red.svg)](LICENSE)

Git Tree는 원격 Git 저장소의 모든 브랜치를 브랜치 이름과 같은 로컬 폴더 계층에 각각 독립된 worktree로 구성하고 동기화하는 Windows·macOS 데스크톱 앱입니다.

```text
main                → <로컬 루트>/main
develop             → <로컬 루트>/develop
feat/feature        → <로컬 루트>/feat/feature
fix/login/oauth     → <로컬 루트>/fix/login/oauth
```

이 저장소는 **공식 실행 파일 배포 전용**이며 소스 코드를 포함하지 않습니다. 제품 안내와 지원 정보는 [Git Tree 공식 홈페이지](https://git-tree.st4ck.kr)와 [Studio Sia 프로젝트 페이지](https://stu.harin.im/projects/004)에서 확인할 수 있습니다.

## 다운로드

현재 정식 버전은 **1.1.3**입니다. 파일명과 `releases/latest/download` 주소는 버전과 무관하게 고정됩니다.

| 대상 | 다운로드 |
| --- | --- |
| Windows 10 이상, x86_64 | [`Git-Tree-Windows-x86_64-Setup.exe`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-Windows-x86_64-Setup.exe) |
| macOS 12 이상, Apple Silicon | [`Git-Tree-macOS-arm64.pkg`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-macOS-arm64.pkg) |
| macOS 12 이상, Intel | [`Git-Tree-macOS-x86_64.pkg`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-macOS-x86_64.pkg) |
| 사용권 계약 | [`Git-Tree-EULA.txt`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-EULA.txt) |
| SHA-256 체크섬 | [`Git-Tree-SHA256SUMS.txt`](https://github.com/stack1245/Git-Tree/releases/latest/download/Git-Tree-SHA256SUMS.txt) |

Git Tree는 시스템에 설치된 Git을 사용합니다. 앱을 실행하기 전에 [Git](https://git-scm.com/downloads)을 설치해 주세요. 별도 Python 설치는 필요하지 않습니다.

Windows installer는 코드 서명 인증서로 서명되지 않았고 macOS 앱과 PKG는 Apple 공증을 받지 않았습니다. 운영체제 보안 안내가 표시되면 릴리스 주소·파일명과 SHA-256을 확인한 뒤 실행 여부를 선택하세요.

## 주요 기능

- 원격 `refs/heads/*` 전체를 조회해 브랜치마다 독립된 worktree 구성
- `main/.git`을 실제 주 저장소로 사용하고 나머지 브랜치는 표준 linked worktree로 연결
- 기존 일반 Git 저장소의 커밋·태그·stash·reflog와 작업 파일을 보존한 채 전환
- 구버전 `.git-tree/repository.git` 작업공간의 표준 Git 구조 자동 이전과 실패 시 원상 복구
- 로컬 수정·미추적·무시 파일과 빈 폴더 감지
- 명시적 삭제 동의 시에만 ZIP 백업·무결성 검사 후 원격 상태 적용
- Git 작업 잠금, 파일 잠금, 권한 오류, 동시 변경과 특수 파일의 fail-closed 처리
- 실행 시 자동 업데이트 확인과 Ed25519 서명·공식 주소·크기·SHA-256 검증
- Claude Desktop·Cursor·Codex 등이 계획을 구조화된 데이터로 읽는 로컬 MCP 서버
- Windows x86_64, macOS Apple Silicon, macOS Intel installer 제공

## 앱에서 업데이트

Git Tree는 실행 약 2초 뒤 새 버전을 확인합니다. 최신 버전이면 창을 띄우지 않고 계속 실행하며, 새 릴리스가 있을 때만 업데이트 안내를 표시합니다. 화면 오른쪽 위의 **업데이트 확인**으로 수동 확인할 수도 있습니다.

1.1.3부터 공식 홈페이지와 GitHub의 서명된 업데이트 정보를 동시에 확인합니다. 한쪽 서버가 응답하지 않거나 게시가 늦어도 다른 경로를 확인하고, 서명이 유효한 가장 최신 버전을 선택합니다. 이후 installer의 공식 GitHub 주소, 파일명, 크기와 SHA-256을 검증한 뒤에만 실행합니다.

1.1.1 이하 버전은 GitHub 한 경로만 사용합니다. 업데이트 서버 오류가 반복되면 [공식 홈페이지](https://git-tree.st4ck.kr)에서 최신 installer를 한 번 직접 설치해 주세요. 1.1.3부터는 이후 업데이트를 두 경로로 확인합니다.

## 안전한 동기화

Git Tree의 기본 동작은 로컬 작업물을 보존하는 것입니다.

- 로컬 수정·미추적·무시 파일이나 정리 대상 빈 폴더가 발견되면 동기화를 중단합니다.
- 변경이 없는 worktree만 비파괴 방식으로 원격 커밋에 맞춥니다.
- 사용자가 **로컬 변경을 ZIP 백업 후 삭제하고 원격 상태로 맞추기**에 명시적으로 동의한 경우에만 파괴적 동작을 허용합니다.
- 백업 전 읽기 가능 여부와 저장 공간을 확인하고, ZIP 무결성과 백업 직후 파일 상태가 확인된 뒤에만 원격 상태를 적용합니다.
- Next.js·Git 작업 잠금, 파일 교체·동시 변경, 심볼릭 링크, 정션, 파이프·소켓·장치와 권한 오류는 추측해서 건너뛰지 않습니다.

ZIP 백업은 안전망이지만 버전 관리의 대체 수단은 아닙니다. 중요한 작업은 동기화 전에 커밋하거나 별도 위치에도 보관하는 것을 권장합니다.

## v1.1.3 패치노트

- 공식 홈페이지와 GitHub의 서명된 업데이트 정보를 동시에 확인하도록 변경했습니다.
- 한쪽 경로에 연결하지 못하거나 잘못된 응답을 받아도 다른 경로로 확인을 계속합니다.
- 두 경로의 게시 시점이 달라도 유효한 서명 중 가장 최신 버전을 선택합니다.
- 시작 시 두 네트워크 요청을 순차 대기하지 않아 자동 업데이트 확인의 최악 대기 시간을 줄였습니다.
- 인터넷 연결 문제로 단정하던 오류 문구를 업데이트 서버 상태와 공식 수동 설치 경로가 드러나도록 수정했습니다.
- installer의 공식 주소, 파일 크기와 SHA-256 검증은 그대로 유지합니다.

## v1.1.2 주요 변경

- `main/.git` 실제 저장소와 Git이 등록한 linked worktree를 사용하는 표준 구조로 전환했습니다.
- 기존 일반 Git 저장소와 구버전 Git Tree 작업공간을 데이터 손실 없이 가져오는 이전 절차를 추가했습니다.
- 본문·입력·버튼·로그를 포함한 UI 글자를 최소 12px 이상으로 조정하고 사용 순서를 화면에 표시했습니다.
- 앱 실행 시 새 릴리스를 자동 확인하고 최신 버전일 때는 알림 없이 계속 실행하도록 변경했습니다.

## 라이선스

Git Tree는 공개 소프트웨어가 아닙니다. Copyright (c) 2026 stack1245. All rights reserved.

승인된 사용자는 [독점 소프트웨어 사용권 계약](LICENSE)의 범위 안에서 컴파일된 앱을 내부 용도로 사용할 수 있습니다. 소스 코드의 공개·복제·수정·재배포·재판매와 법이 허용하는 범위를 벗어난 역공학은 금지됩니다.
