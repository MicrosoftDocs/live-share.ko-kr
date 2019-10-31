---
title: Linux 설치 세부 정보-Visual Studio Live Share | Microsoft Docs
description: Linux에 Visual Studio Live Share를 설치 하는 방법에 대 한 자세한 정보입니다.
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
ms.openlocfilehash: 27a3d76f14cd3c8df312abe7ab36185109ac7e89
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170126"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Linux 설치 정보

Linux는 가변성이 큰 환경이며 데스크톱 환경 및 배포 수가 너무 많아 작업하는 데 복잡할 수 있습니다. 지원 되는 버전의 **Ubuntu Desktop** (16.04 +), **CentOS 7**또는 **Fedora Workstation** (27 이상)을 사용 하 고 **VS Code의 공식 배포**만 사용 하는 경우 프로세스를 바로 찾아야 합니다. 그러나 비표준 구성 또는 다운스트림 배포를 사용하는 경우 일부 문제가 발생할 수도 발생하지 않을 수도 있습니다. 이 문서에서는 커뮤니티 에서만 지원 되는 경우에도 구성 하는 데 도움이 되는 요구 사항 및 몇 가지 문제 해결 세부 정보를 제공 합니다. Live Share는 **64 비트 Linux**만 지원 합니다.

## <a name="install-linux-prerequisites"></a>Linux 필수 구성 요소 설치

일부 Linux 배포에는 Live Share가 작동하는 데 필요한 라이브러리가 누락되어 있습니다. 기본적으로 Live Share는 Linux 필수 구성 요소를 탐지하여 설치하려고 합니다. Live Share에서 누락된 라이브러리로 인해 문제가 발생하는 경우 해당 라이브러리를 설치하는 데 필요한 권한을 요청하는 알림 메시지가 표시됩니다.

![Linux 필수 구성 요소가 없다는 메시지를 표시 하는 알림 메시지](../media/vscode-linux-prereq-missing.png)

"설치"를 클릭 하면 OS에서 sudo (admin/root) 암호를 입력 하도록 요청 하는 메시지가 표시 됩니다. 스크립트가 성공적으로 완료 되었다고 가정 하면 모두 설정 해야 한다는 메시지가 표시 되 면 Visual Studio Code를 다시 로드 합니다. 다른 힌트 및 해결 방법이 있는 경우 **[배포별 팁](#tips-by-distribution)** 을 확인하려 할 수도 있습니다.

스크립트에서 배포를 지원하지 않는다는 메시지가 표시되면 커뮤니티가 공유한 **[커뮤니티 지원 배포 팁](#tips-for-unsupported-distros)** 을 참조하세요.

**명령을 VS Code 실행 하지**않으려는 경우 터미널 창에서 다음 명령을 사용 하 여 언제 든 지이 스크립트의 최신 버전을 다시 실행 하도록 선택할 수도 있습니다.

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>배포용 팁

위의 필수 구성 요소 설치 스크립트는 다양 한 배포를 다루지만 일반적으로 바닐라 설치에서 누락 된 항목을 확인할 수 있습니다. 다음 목록에서는 지정 된 배포를 새로 설치 하는 동안 누락 된 키 라이브러리를 보여 줍니다. 이 목록에는 문제가 발생할 경우 시작 및 실행 하는 데 도움이 되는 몇 가지 팁도 제공 됩니다.

| 분포 | 누락 된 라이브러리 설치 바닐라 | 추가 단계 |
|--------|-------------------|----|
| Ubuntu Desktop 18.04 (64 비트) | &lt;none&gt;  | &lt;none&gt; |
| Ubuntu Desktop 16.04 (64 비트) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18.04 (64 비트) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16.04 (64 비트) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18.04 (64 비트) |&lt;none&gt;  | <ul><li>"세션 및 시작"의 "고급" 탭에서 "시작 시 GNOME 서비스 시작"이 선택 되어 있는지 확인 합니다.</li><li>로그인 문제가 발생 한 경우 `seahorse`를 설치 하 고 "암호 및 키"를 시작 하 고 "로그인" 인증 기능이 있는지 확인 하 고 잠금을 해제할 수 있는지 확인 합니다.</li></ul> |
| Xubuntu 16.04 (64 비트) | &lt;none&gt; | <ul><li>"세션 및 시작"의 "고급" 탭에서 "시작 시 GNOME 서비스 시작"이 선택 되어 있는지 확인 합니다.</li><li>로그인 문제가 발생 한 경우 `seahorse`를 설치 하 고 "암호 및 키"를 시작 하 고 "로그인" 인증 기능이 있는지 확인 하 고 잠금을 해제할 수 있는지 확인 합니다.</li></ul> |
| Mint 19 Cinnamon (64 비트) | &lt;none&gt;  | &lt;none&gt; |
| Mint 18.3 Cinnamon (64 비트) | &lt;none&gt;  | &lt;none&gt; |
| Debian 10 (Buster) 테스트 (64 비트) | 릴리스가 안정적이 지 않아 알 수 없습니다. | <ul><li>Debian 테스트 및 불안정 한 (Sid)는 공식적으로 지원 되지 않습니다.</li><li>.NET Core에는 Live Share 영향을 주는 [알려진 문제가](https://github.com/dotnet/corefx/issues/33179) 있습니다. </li><li>[해결 방법은 여기](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249)를 참조 하세요.</li></ul> |
| Debian 9 GNOME Desktop (64 비트) | &lt;none&gt; | <ul><li>자동 설치 스크립트를 사용 하려면 `sudo`를 설치 하 고 sudo 그룹에 사용자를 추가 해야 할 수 있습니다.</li>  |
| Fedora Workstation 29 (64 비트) | `openssl-compat10` | &lt;none&gt; |
| Fedora 워크스테이션 28 (64 비트) | &lt;none&gt; | &lt;none&gt; |
| Fedora 워크스테이션 27 (64 비트) | &lt;none&gt; | &lt;none&gt; |
| CentOS 7 GNOME Desktop (64 비트) | &lt;none&gt; | &lt;none&gt; |

다른 비 Debian/Ubuntu 또는 RHL 기반 배포에 대 한 정보는 **[커뮤니티 지원 배포판에 대 한 팁](#tips-for-community-supported-distros)** 을 참조 하세요.

추가 세부 정보는 필요한 Live Share 특정 [라이브러리에서 확인할](#detailed-library-requirements) 수도 있습니다.

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>커뮤니티 지원 배포판에 대 한 팁

Debian/Ubuntu 또는 RHL 트리 외부의 배포는 Visual Studio Code 또는 .NET Core에서 공식적으로 지원 되지 않습니다. 따라서 확장에 의해 Visual Studio Live Share는 공식적으로 지원 되지 않습니다. 그러나 커뮤니티는 여러 추가 배포에 대 한 Live Share 실행 및 실행에 대 한 몇 가지 유용한 정보를 제공 합니다.

> **Pr 시작:** 선호 하는 배포로이 정보를 업데이트 하는 데 관심이 있는 경우 문서 GitHub 리포지토리에서 [이 파일](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md) 에 대 한 PR을 제출 하세요. 선호 하는 배포를 지 원하는 종속성 설치 관리자를 가져오려는 경우에도 [이 파일에 대 한](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh)PR을 제출할 수 있습니다.

| 분포 | 작업? | 누락 된 라이브러리 설치 바닐라 | 추가 단계 |
|--------------|----------|-------------------|------------------|
| 아키텍처 Linux (64 비트) | 예 | 잠기기. 가능한 라이브러리: `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>[필수 구성 요소 설치 스크립트](#install-linux-prerequisites)에서 지원 됩니다.</li><li>VS Code에 [대해 AUR 패키지를 사용](https://aur.archlinux.org/packages/visual-studio-code-bin) 합니다.</li><li>자동화 된 필수 구성 요소 설치 스크립트를 사용 하려면 `sudo`가 설치 되어 있어야 합니다.</li><li>일부 데스크톱 환경에서는 `gnome-keyring`에 추가 [설치 단계가](https://wiki.archlinux.org/index.php/GNOME/Keyring) 필요할 수 있습니다.</ul> |
| Manjaro 17.1 (64 비트) | 예 | `xorg-xprop liburcu` | <ul><li>[필수 구성 요소 설치 스크립트](#install-linux-prerequisites)에서 지원 됩니다.</li><li>VS Code에 [대해 AUR 패키지를 사용](https://aur.archlinux.org/packages/visual-studio-code-bin) 합니다.</li></ul> |
| openSuSE LEAP 15 KDE (64 비트) | 예 | `libopenssl1_0_0 gnome-keyring` | <ul><li>필수 구성 요소 설치 스크립트에서 지원 됩니다.</li></ul> |
| Sus 3 (64 비트) | 예 | `xprop` | <ul><li>[필수 구성 요소 설치 스크립트](#install-linux-prerequisites)에서 지원 됩니다.</li><li>릴리스 57 이전의 `vscode` 패키지 버전에는 필요한 product. json 값이 없습니다 ([아래 참조](#vs-code-oss-issues)). 이 문제를 해결 하려면 `vscode` 패키지를 업그레이드 하십시오.</li></ul> |
| Gentoo (64 비트) | 예 | 변수가 매우 높습니다. 누락 된 패키지: `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>**Jorgicio** 오버레이의 `visual-studio-code` 패키지는 작동 하는 것으로 알려져 있습니다.</li></ul>

## <a name="install-prerequisites-manually"></a>필수 구성 요소 수동 설치

 Live Share의 **종속성 설치 스크립트**를 사용 하는 것이 좋지만이 섹션에서는 이러한 단계를 직접 수행 하거나 스크립트에서 지원 하지 않는 배포를 사용 하는 경우의 라이브러리 요구 사항에 대 한 자세한 정보를 제공 합니다.

바닐라 설치에서 일반적인 누락 된 라이브러리는 커뮤니티에서 지 원하는 배포 섹션에 [대 한](#tips-for-unsupported-distros) 배포 및 팁의 [팁](#tips-by-distribution) 에서 찾을 수 있습니다.

### <a name="detailed-library-requirements"></a>자세한 라이브러리 요구 사항

Visual Studio Live Share의 기본 라이브러리 요구 사항은 .NET Core 2.1를 사용 하 고, 자격 증명을 유지 하 고, 브라우저 통합을 위해 제공 됩니다. 다음 표에서는 .NET Core에서 공식적으로 지원 되는 배포에 대 한 이러한 요구 사항을 요약 합니다.

| 분포 | .NET Core 요구 사항 | 자격 증명 저장소 요구 사항| 브라우저 통합 요구 사항 |
|--------------|-----------|--------------------|------------|
| Ubuntu 및 다운스트림 배포 | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (Ubuntu 16.04, Mint 18.3) 또는 `libicu57` (Ubuntu 17.10의 경우) 또는 `libicu60` (Ubuntu 18.04, Mint 19의 경우) | `libsecret-1-0 gnome-keyring` (또는 기능 비밀 지원 되는 인증 키-Kwallet은 기능 비밀을 지원 하지 않음) | `desktop-file-utils x11-utils` |
| Debian 9 및 다운스트림 배포 | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (또는 기능 비밀 지원 되는 인증 키-Kwallet은 기능 비밀을 지원 하지 않음) | `desktop-file-utils x11-utils` |
| RHL/CentOS/Fedora | `openssl-libs krb5-libs zlib libicu` Fedora에는 `compat-openssl10`도 필요 합니다.| `libsecret gnome-keyring` (또는 기능 비밀 지원 되는 인증 키-Kwallet은 기능 비밀을 지원 하지 않음) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (또는 기능 비밀 지원 되는 인증 키-Kwallet은 기능 비밀을 지원 하지 않음) | `desktop-file-utils xprop`

다른 배포에는 동일한 라이브러리가 필요 하지만 패키지 이름은 다를 수 있습니다. [커뮤니티에서 지 원하는 배포에 대 한 팁](#tips-for-unsupported-distros) 섹션에서 다음 중 일부를 찾을 수 있습니다.

### <a name="debian--ubuntu"></a>Debian/Ubuntu

라이브러리는 터미널에서 `sudo apt install <library-name>`를 실행 하 여 Debian/Ubuntu 기반 배포에 설치할 수 있습니다.

Mint를 포함 하는 Ubuntu 기반 배포의 경우 다음을 실행 합니다.

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Debian 9 및 비 Ubuntu 다운스트림 배포의 경우 다음을 실행 합니다.

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora/CentOS/RHL

라이브러리는 터미널에서 `sudo yum install <library-name>`를 실행 하 여 Fedora/CentOS/RHL 기반 배포에 설치할 수 있습니다. 예를 들어, 다음과 같이 모든 항목을 설치 합니다.

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>OSS 문제 VS Code

> **아키텍처 Linux/Manjaro 사용자:** 이 문제를 방지 하려면 [visual studio-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) AUR 패키지를 사용 합니다.

바닐라 또는 수정 된 버전의 VS Code OSS 인 Visual Studio Code 패키지에는 `product.json` 파일의 중요 한 값이 누락 되어 Visual Studio Live Share를 활성화할 수 없습니다.

이 문제를 해결 하는 빠른 방법은 도움말 > "개발자 도구 전환"으로 이동 하 여 Live Share 확장이 "제안 된 API"를 사용 하 고 있기 때문에 활성화 되지 않았음을 나타내는 스택 추적을 확인 하는 것입니다.

이것이 문제 인지 확인 하려면 `product.json`의 내용을 확인 합니다. 파일의 위치는 패키지에 따라 다르지만 일반적으로 다음 위치 중 하나에 있습니다.

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

`extensionAllowedProposedApi` 속성이 없거나 "vsliveshare. vsliveshare"가 표시 되지 않는 경우이 문제가 발생 한 OSS 버전을 사용 하 고 있는 것입니다.

이 **문제를 해결**하려면 다음을 제품 json에 추가 하면 됩니다.

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

사용 중인 배포가 작동 하는지 여부에 대 한 자세한 내용은 [위의](#tips-for-community-supported-distros) 항목을 참조 하세요.

## <a name="linux-browser-integration"></a>Linux 브라우저 통합

Visual Studio Live Share에는 일반적으로 Linux에서 브라우저 통합을 사용하기 위한 **추가 설치 단계가 필요하지 않습니다**.

이를 위해 Live Share는 자동으로 데스크톱 파일을 `~/.local/share/applications`에 배치 하 고 확장이 처음 초기화 될 때 `~/.local/share/vsliveshare`에 필수 시작 관리자를 자동으로 배치 합니다. 이 작업이 성공 하면 사용자에 게 아무런 조치도 필요 하지 않습니다.

경우에 따라 배포는이 위치를 지원 하지 않거나 바닐라 설치 작업을 수행 하기 위해 조정 해야 합니다. 이 경우 Live Share는 대신 `/usr/local/share`를 사용 하는 것으로 대체 됩니다. 따라서 설치 프로세스를 완료 하려면 **sudo (관리자) 암호가 필요 하다는 알림이 표시 될 수** 있습니다. 터미널 창이 표시돼 브라우저 시작 관리자를 설치할 위치를 알려줍니다. 메시지가 표시되면 단순히 암호를 입력하고 설치가 완료되면 Enter 키를 눌러 터미널 창을 닫습니다.

대신 직접 명령을 실행 하려면 "복사"를 클릭 합니다. 그러면 터미널 명령이 클립보드에 복사 됩니다.

마지막으로이 단계를 완전히 건너뛰려면 [수동으로 공동 작업 세션을 조인할](../how-to-guides/vscode.md#join-manually)수 있지만 브라우저에서 초대 링크를 열어 조인할 수는 없습니다. **Ctrl + shift + p/Cmd + shift + P** 를 누르고 "Live Share: 시작 관리자 설정" 명령을 선택 하 여 나중에 언제 든 지 명령에 다시 액세스할 수 있습니다.

## <a name="see-also"></a>참조

- [방법: Visual Studio Code를 사용 하 여 공동 작업](../how-to-guides/vscode.md)
- [Live Share 연결 요구 사항](connectivity.md)
- [Live Share의 보안 기능](security.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
