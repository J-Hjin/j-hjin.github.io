---
layout: post
title: Windows 11 환경에서 WSL 2 사용하기 - Ubuntu 24.04 LTS
date: 2024-04-10 21:44 +0900
description: Windows 11 환경에서 Ubuntu 24.04 LTS 사용하기
category: [Linux, WSL]
tags: [WSL2, Ubuntu, Windows, TroubleShooting]
---
<hr>

> ## __WSL2를 위한 기능 사용 설정__

powershell을 관리자 권한으로 실행시킨 후 다음 명령줄을 수행하여 Windows 하위 시스템 및 Virtual Machine 기능을 Enable 상태로 변경합니다.

***명령을 수행한 후에는 재부팅을 꼭 해주셔야 합니다.***

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

<hr>

> ## __Ubuntu 24.04 LTS 설치__

WSL을 사용하기 위한 Windows 기능을 성공적으로 활성화 하였다면 WSL 기본 버전을 2로 설정한 후 *Microsoft Store*에서 *Ubuntu 24.04 LTS*를 검색하여 Ubuntu를 설치하거나 wsl 명령문을 통해 설치를 진행합니다.

저는 명령문을 통해 설치를 진행하였습니다.
설치 이후에는 Ubuntu를 실행하여 UNIX username 및 password를 설정하여 일반 사용자 계정을 생성합니다.

```powershell
wsl --list --online # 온라인으로 설치 가능한 list 조회
wsl --install -d Ubuntu-24.04 
```

<hr>

> ## __Trouble Shooting__

오류 발생 시 댓글 남겨주시면 향후 추가하도록 하겠습니다.

>> ### __error: 0x800701bc__ 

Ubuntu 실행 중에 *WslRegisterDistribution failed with error: 0x800701bc*에러가 발생한 경우 [windows/wsl/install-manual](https://learn.microsoft.com/ko-kr/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package) 에서 *x64 머신용 최신 WSL2 Linux 커널 업데이트 패키지*를 설치하여 커널 업데이트를 진행하면 해결할 수 있습니다.

<hr>

> 보완 할 부분이 있다면 댓글 남겨주시면 감사하겠습니다. 🙂
{: .prompt-tip }