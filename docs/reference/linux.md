---
title: Linux 설치 정보-Visual Studio Live Share | Microsoft Docs
description: Linux에서 Visual Studio Live Share의 설치에 대 한 자세한 정보입니다.
ms.custom: ''
ms.date: 10/6/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 9ac16b0e598fb07446c2b682397684b7e2e4709a
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640135"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Linux 설치 세부 정보

Linux는 가변성이 큰 환경이며 데스크톱 환경 및 배포 수가 너무 많아 작업하는 데 복잡할 수 있습니다. 지원 되는 버전을 포기 하는 경우 **Ubuntu Desktop** (16.04 이상) **CentOS 7**, 또는 **Fedora 워크스테이션** (27 이상)만 사용 하 여 **VS의 공식 배포 코드**, 상당히 직관적으로 프로세스를 찾아야 합니다. 그러나 비표준 구성 또는 다운스트림 배포를 사용하는 경우 일부 문제가 발생할 수도 발생하지 않을 수도 있습니다. 이 문서에서는 요구 사항에 일부 정보를 제공 하 고 도움이 될 수 있는 몇 가지 문제 해결 세부 정보 시작 지원 되는 경우에 구성만 커뮤니티를 실행 합니다. Live Share만 지원 합니다. 이때 **64 비트 Linux**합니다.

## <a name="install-linux-prerequisites"></a>Linux 필수 구성 요소 설치

일부 Linux 배포에는 Live Share가 작동하는 데 필요한 라이브러리가 누락되어 있습니다. 기본적으로 Live Share는 Linux 필수 구성 요소를 탐지하여 설치하려고 합니다. Live Share에서 누락된 라이브러리로 인해 문제가 발생하는 경우 해당 라이브러리를 설치하는 데 필요한 권한을 요청하는 알림 메시지가 표시됩니다.

![Linux 필수 구성 요소는 누락 된 토스트 알림 보여 주는 메시지](../media/vscode-linux-prereq-missing.png)

"설치"를 클릭 하면 터미널 창에는 OS에서 묻는 입력 관리자 / 루트 (sudo) 암호를 계속 메시지가 표시 됩니다. 를 가정 하 고 스크립트를 성공적으로 완료 하 여 다시 로드 하면 메시지가 표시 되 면 Visual Studio Code 모든 집합 이어야 합니다. 다른 힌트 및 해결 방법이 있는 경우 **[배포별 팁](#tips-by-distribution)** 을 확인하려 할 수도 있습니다.

스크립트에서 배포를 지원하지 않는다는 메시지가 표시되면 커뮤니티가 공유한 **[커뮤니티 지원 배포 팁](#tips-for-unsupported-distros)** 을 참조하세요.

경우 있습니다 **하지 않는 명령을 실행 하는 VS Code 편을 선호**를 다시 실행 하려면이 스크립트의 최신 버전이 언제 든 지 수동으로 터미널 창에서 다음 명령을 사용 하 여 선택할 수도 있습니다.

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>배포에 따라 팁

필수 구성 요소를 설치 하는 동안 위의 스크립트에서는 다양 한 배포, 무엇이 일반적으로 바닐라 설치에서 궁금할 수 있습니다. 다음 목록에 지정 된 배포의 새 설치에 누락 된 핵심 라이브러리를 보여 줍니다. 목록 도움이 될 수 있는 몇 가지 팁 받고 실행 문제가 발생 하면도 제공 합니다.

| 분포 | 바닐라 누락 된 라이브러리를 설치 합니다. | 추가 단계 |
|--------|-------------------|----|
| Ubuntu Desktop 18.04 (64 비트) | &lt;none&gt;  | &lt;none&gt; |
| Ubuntu Desktop 16.04 (64 비트) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18.04 (64 비트) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16.04 (64 비트) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18.04 (64 비트) |&lt;none&gt;  | <ul><li>확인 "시작 GNOME 서비스 시작 시" 세션 및 "시작"의 "고급" 탭에서 확인 됩니다.</li><li>로그인 문제가 발생할 경우 설치 `seahorse`시작 "암호 및 키", "Login" 키 링 있고 해당 잠금을 해제할 수 있습니다를 확인 합니다.</li></ul> |
| Xubuntu 16.04 (64 비트) | &lt;none&gt; | <ul><li>확인 "시작 GNOME 서비스 시작 시" 세션 및 "시작"의 "고급" 탭에서 확인 됩니다.</li><li>로그인 문제가 발생할 경우 설치 `seahorse`시작 "암호 및 키", "Login" 키 링 있고 해당 잠금을 해제할 수 있습니다를 확인 합니다.</li></ul> |
| 19 mint Cinnamon (64 비트) | &lt;none&gt;  | &lt;none&gt; |
| Mint 18.3 Cinnamon (64 비트) | &lt;none&gt;  | &lt;none&gt; |
| Debian 10 (버스터) (64 비트)를 테스트 합니다. | 안정적이 고 따라서 알 수 없는 없습니다를 해제 합니다. | <ul><li>Debian 테스트 및 불안정 (Sid) 공식적으로 지원 되지 않습니다.</li><li>한 [알려진 문제](https://github.com/dotnet/corefx/issues/33179) Live Share를 영향을 주는.NET Core에서 합니다. </li><li>참조 [해결 방법은 여기](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249)합니다.</li></ul> |
| Debian 9 GNOME 데스크톱 (64 비트) | &lt;none&gt; | <ul><li>설치 해야 `sudo` 자동화 된 설치 스크립트를 사용 하는 sudo 그룹에 사용자를 추가 합니다.</li>  |
| Fedora 워크스테이션 29 (64 비트) | `openssl-compat10` | &lt;none&gt; |
| Fedora 워크스테이션 28 (64 비트) | &lt;none&gt; | &lt;none&gt; |
| Fedora 워크스테이션 27 (64 비트) | &lt;none&gt; | &lt;none&gt; |
| GNOME 데스크톱 centOS 7 (64 비트) | &lt;none&gt; | &lt;none&gt; |

참조 **[커뮤니티 지원 배포에 대 한 팁](#tips-for-community-supported-distros)** 다른 비-Debian에 대 한 내용은 Ubuntu 또는 RHL 기준 배포 합니다.

추가 세부 정보를 찾을 수도 있습니다 [아래](#detailed-library-requirements) Live Share 필요한 특정 라이브러리에 있습니다.

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>커뮤니티 지원 배포판에 대 한 팁

배포 외부의 Debian / Ubuntu 또는 RHL 트리 Visual Studio Code 또는.NET Core에서 공식적으로 지원 되지 않습니다. 따라서 확장을 통해 이러한 지원 되지 않습니다 공식적으로 Visual Studio Live Share 여 하거나. 그러나 커뮤니티에 기여한 Live Share를 시작 하 고 다양 한 추가 배포를 실행 하는 방법에 대 한 유용한 정보입니다.

> **Pr을 환영 합니다.** 즐겨 사용 하 여 배포를 사용 하 여이 정보를 업데이트 하려는 경우 PR을 제출 [이 파일](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md) docs GitHub 리포지토리에서에서. 게다가 즐겨 사용 하 여 배포를 지 원하는 종속성 설치 관리자 다운로드 하려는 경우 PR을 제출할 수 있습니다 [이 파일에 대 한](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh)합니다.

| 분포 | 작동 합니까? | 바닐라 누락 된 라이브러리를 설치 합니다. | 추가 단계 |
|--------------|----------|-------------------|------------------|
| Arch Linux (64 비트) | 예 | 달라 집니다. 가능한 라이브러리: `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>지원 합니다 [필수 구성 요소 설치 스크립트](#install-linux-prerequisites)합니다.</li><li>사용 된 [visual studio-코드 bin](https://aur.archlinux.org/packages/visual-studio-code-bin) for VS Code AUR 패키지.</li><li>`sudo` 사용 하려면 설치를 자동화 된 필수 구성 요소 설치 해야 스크립트 합니다.</li><li>`gnome-keyring` 추가 해야 할 수 있습니다 [설정 단계](https://wiki.archlinux.org/index.php/GNOME/Keyring) 데스크톱 환경의 일부입니다.</ul> |
| Manjaro 17.1 (64 비트) | 예 | `xorg-xprop liburcu` | <ul><li>지원 합니다 [필수 구성 요소 설치 스크립트](#install-linux-prerequisites)합니다.</li><li>사용 된 [visual studio-코드 bin](https://aur.archlinux.org/packages/visual-studio-code-bin) for VS Code AUR 패키지.</li></ul> |
| openSuSE LEAP 15 KDE (64 비트) | 예 | `libopenssl1_0_0 gnome-keyring` | <ul><li>필수 구성 요소 설치 스크립트를 지원 합니다.</li></ul> |
| Solus 3 (64 비트) | 예 | `xprop` | <ul><li>지원 합니다 [필수 구성 요소 설치 스크립트](#install-linux-prerequisites)합니다.</li><li>버전을 `vscode` 57 릴리스 전에 패키지 된 누락 된 필수 product.json 값 ([아래 참조](#vs-code-oss-issues)). 업그레이드는 `vscode` 이 문제를 해결 하려면 패키지 있습니다.</li></ul> |
| Gentoo (64 비트) | 예 | 매우 다양 합니다. 누락 된 패키지 수: `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>합니다 `visual-studio-code` 패키지를 **jorgicio** 오버레이 작동 하도록 라고 합니다.</li></ul>

## <a name="install-prerequisites-manually"></a>필수 구성 요소를 수동으로 설치 하십시오.

 Live Share를 사용 하는 것이 좋지만 **종속성 설치 스크립트**,이 섹션에서는 추가 세부 정보를 제공 라이브러리 요구 사항에 이러한 단계를 수행 하거나에서 지원 되지 않습니다 배포를 사용 하는 경우에 스크립트입니다.

바닐라 설치에 일반적인 누락 된 라이브러리에서 찾을 수 있습니다 합니다 [배포 팁](#tips-by-distribution) 하 고 [커뮤니티 지원 배포에 대 한 팁](#tips-for-unsupported-distros) 섹션입니다.

### <a name="detailed-library-requirements"></a>자세한 라이브러리 요구 사항

자격 증명 및 브라우저 통합 유지를 사용 하 여.NET Core 2.1을 libsecret visual Studio Live Share의 네이티브 라이브러리 요구 사항 제공 됩니다. 다음 표에서.NET Core에서 공식적으로 지원 되는 배포에 대 한 이러한 요구 사항을 보여 줍니다.

| 분포 | .NET Core Reqs | 자격 증명 저장소 요구 사항| 브라우저 통합 요구 사항 |
|--------------|-----------|--------------------|------------|
| Ubuntu 및 다운스트림 분포 | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (ubuntu 16.04의 경우 18.3 만들고) 또는 `libicu57` (Ubuntu 17.10)에 대 한 또는 `libicu60` (18.04 ubuntu의 경우 19 만들고) | `libsecret-1-0 gnome-keyring` (또는 libsecret 키 링 지원-Kwallet libsecret을 지원 하지 않습니다) | `desktop-file-utils x11-utils` |
| Debian 9 및 다운스트림 배포 | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (또는 libsecret 키 링 지원-Kwallet libsecret을 지원 하지 않습니다) | `desktop-file-utils x11-utils` |
| RHL / CentOS / Fedora | `openssl-libs krb5-libs zlib libicu` Fedora도 필요합니다. `compat-openssl10`| `libsecret gnome-keyring` (또는 libsecret 키 링 지원-Kwallet libsecret을 지원 하지 않습니다) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (또는 libsecret 키 링 지원-Kwallet libsecret을 지원 하지 않습니다) | `desktop-file-utils xprop`

다른 배포는 필요 하지만 동일한 라이브러리, 패키지 이름 달라질 수 있습니다. 이 중 일부를 찾을 수 있습니다 합니다 [커뮤니티 지원 배포에 대 한 팁](#tips-for-unsupported-distros) 섹션입니다.

### <a name="debian--ubuntu"></a>Debian / Ubuntu

실행 하 여 Debian/Ubuntu 기반 배포판에서 라이브러리를 설치할 수 있습니다 `sudo apt install <library-name>` 터미널에서.

Mint를 포함 하 여 Ubuntu 기반 배포판을 실행 합니다.

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Debian 9 및 비-Ubuntu 다운스트림 배포판의 경우 다음을 실행 합니다.

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora / CentOS / RHL

실행 하 여 Fedora/CentOS/RHL 기반 배포판에서 라이브러리를 설치할 수 있습니다 `sudo yum install <library-name>` 터미널에서. 예를 들어,이 모두 설치 됩니다.

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>VS 코드 OSS 문제

> **Linux/Manjaro 사용자 아키텍처:** 사용 된 [visual studio bin](https://aur.archlinux.org/packages/visual-studio-code-bin) 이 문제를 방지 하려면 AUR 패키지 합니다.

Visual Studio Code의 어느 바닐라 추가 되거나 수정 된 버전의 VS 코드 OSS 패키지의 중요 한 값을 누락 될 수 있으며 `product.json` Visual Studio Live Share를 활성화 하지 못하도록 하는 파일입니다.

이 문제를 적중 수를 확인 하는 빠른 방법을 도움말으로 이동 하는 것 > "개발자 도구 설정/해제" 하 고 Live Share 확장을 나타내는 스택 추적을 찾을 경우 참조 하는 "제안된 API." 사용 중 이어서 활성화 하지 않은

문제가 발생 하는이 확인 하려면 확인 내용의 `product.json`합니다. 파일의 위치를 패키지에서 다릅니다 이지만 일반적으로 다음 위치 중 하나:

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

경우는 `extensionAllowedProposedApi` 속성이 누락 또는 "ms-vsliveshare.vsliveshare" 참조 표시 되지 않으면,이 문제를이 해결 하는 OS 버전을 사용 하는 합니다.

로 **해결 방법**는 product.json에는 다음을 추가할 수 있습니다.

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

참조 [위에](#tips-for-community-supported-distros) 작동 하려면 사용 중인 배포판 알려져 있는지 여부에 대 한 자세한 내용은 합니다.

## <a name="linux-browser-integration"></a>Linux 브라우저 통합

Visual Studio Live Share에는 일반적으로 Linux에서 브라우저 통합을 사용하기 위한 **추가 설치 단계가 필요하지 않습니다**.

이를 위해 Live Share 자동으로 배치에서 데스크톱 파일로 `~/.local/share/applications` 및 자체 필요한 시작 관리자에서 `~/.local/share/vsliveshare` 확장을 처음으로 초기화 합니다. 이 작업이 성공 하면 사용자의 조치가 필요 합니다.

일부 경우에 배포 하거나 지원 하지이 위치 않거나 해당 바닐라 설치를 사용 하 여 작업을 조정 해야 합니다. 이러한 경우에 Live Share 대체 사용 하 여 `/usr/local/share` 대신 합니다. 따라서 **알려 관리자 (sudo) 암호 필요 하다** 설치 프로세스를 완료 합니다. 터미널 창이 표시돼 브라우저 시작 관리자를 설치할 위치를 알려줍니다. 메시지가 표시되면 단순히 암호를 입력하고 설치가 완료되면 Enter 키를 눌러 터미널 창을 닫습니다.

직접 명령을 실행할 대신 하려는 경우 "복사" 대신 터미널 명령을 클립보드로 대신 복사 됩니다는 클릭 수 있습니다.

마지막으로,이 단계를 완전히 건너뛸 경우 할 수 있습니다 [공동 작업 세션을 수동으로 조인](../use/vscode.md#join-manually), 있지만 초대 링크를 브라우저에서 열어 연결할 수 없습니다. 액세스할 수 있는지 항상 명령은 나중에 다시 눌러 참고 **Ctrl + Shift + P / Cmd + Shift + P** 하 고 선택 하는 "라이브 공유: 시작 관리자 Setup"명령입니다.

## <a name="see-also"></a>참고자료

- [방법: Visual Studio Code를 사용하여 공동 작업](../use/vscode.md)
- [Live Share 연결 요구 사항](connectivity.md)
- [Live Share의 보안 기능](security.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
