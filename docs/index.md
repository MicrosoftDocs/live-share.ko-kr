---
title: 개요 - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share 및 해당 기능의 개요
ms.custom: ''
ms.date: 10/30/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: fubaduba
ms.author: fubaduba
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 3f6ad9fd00984abeca2b826addee54271eb1191a
ms.sourcegitcommit: 3a1b22eac528b0f6a241f9fec7ec20264db24cfe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74019755"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>Visual Studio Live Share란?

Visual Studio Live Share를 시작합니다. Live Share를 사용하면 사용 중인 프로그래밍 언어나 빌드 중인 앱 유형과 관계없이 다른 사람과 공동으로 실시간 편집 및 디버깅이 가능합니다. 현재 프로젝트를 즉시 안전하게 공유하고, 공동 디버그 세션을 시작하며, 터미널 인스턴스를 공유하고, localhost 웹앱을 전달하고, 음성 통화를 하는 등의 작업을 할 수 있습니다.

 기존의 페어 프로그래밍과 달리, Visual Studio Live Share에서는 개발자가 자신의 커서를 포함할 뿐만 아니라 해당 개인 편집기 기본 설정(예: 테마, 키 바인딩)을 유지하면서 함께 작업할 수 있습니다. 따라서 원활하게 환경을 서로 전환할 수 있으며 아이디어/작업을 직접 탐색할 수 있습니다. 협업하거나 독립적으로 작업할 수 있는 이 기능을 사용하면 _직접_ 공동 작업하는 것과 매우 유사한 공동 작업 환경을 이용할 수 있습니다.

진행할 준비가 되셨나요? 이 문서에서는 몇 가지 개념과 필요한 확장을 설치하는 방법을 살펴봅니다. 요약된 버전을 찾는 경우 [공유](quickstart/share.md) 및 [가입](quickstart/join.md) 빠른 시작을 확인하세요.

> [!TIP]
> *사용자 고유의 협업 세션에 가입*할 수 있다는 것을 알고 계셨나요? 그러면 직접 Live Share를 시도해 보거나 Visual Studio 또는 VS Code의 인스턴스를 전환하고 원격으로 연결할 수 있습니다. 두 인스턴스 모두에 동일한 ID를 사용할 수도 있습니다. 확인해 보세요.

## <a name="install-visual-studio-live-share"></a>Visual Studio Live Share 설치

시작하기 전에 Live Share의 핵심 요구 사항을 충족하는 Visual Studio 또는 Visual Studio Code 버전이 설치되어 있는지 확인해야 합니다.

- **Visual Studio Code 1.22.0 이상** - Windows 7, 8.1 또는 10, macOS *(Sierra 10.12 이상만)* , 64비트 Linux *(64비트 Ubuntu Desktop 16.04 이상, Fedora 27 이상 권장 - [자세히 보기](use/vscode.md#installation))*
- **Visual Studio 2019**(모든 버전) - Windows 7, 8.1 또는 10
- **Visual Studio 2017 15.6 이상**(모든 버전) - Windows 7, 8.1 또는 10

그 후에 Visual Studio Live Share 확장을 다운로드하여 설치하는 것은 쉽습니다.

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code(1.22.0 이상)</strong><br />
        1.Windows(7, 8.1 또는 10), macOS<b>(Sierra+)</b>, 64비트 Linux용 <a href="https://code.visualstudio.com/">Visual Studio Code</a>를 설치합니다<b>(<a href="use/vscode.md#installation">세부 정보</a>)</b>.<br />
        2. 마켓플레이스에서 Visual Studio Live Share 확장을 다운로드하여 설치합니다. <br />
        3. 다시 로드하고 종속성이 다운로드되어 설치될 때까지 기다립니다(상태 표시줄 참조).<br />
        4. <strong>Linux</strong>: <a href="reference/linux.md#install-linux-prerequisites">라이브러리를 설치</a>하라는 메시지가 표시되면 [설치]를 클릭하고 암호를 입력한 다음, 완료되면 VS Code를 다시 시작합니다.<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1.<a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>를 설치합니다.<br/>
        2. <a href="reference/platform-support.md">지원되는 워크로드</a>를 설치합니다. (예: ASP.NET, .NET Core, C++, Python 및/또는 Node.js)<br />
        3. Visual Studio Live Share는 기본적으로 이러한 워크로드와 함께 설치됩니다. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 이상</strong><br />
        1. Windows(7, 8.1 또는 10)에 최신 버전의 <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a>(15.6 이상)을 설치합니다.<br/>
        2. <a href="reference/platform-support.md">지원되는 워크로드</a>를 설치합니다. (예: ASP.NET, .NET Core, C++ 및/또는 Node.js)<br />
        3. 마켓플레이스에서 Visual Studio Live Share 확장을 다운로드하여 설치합니다. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Visual Studio Live Share를 다운로드하여 사용하면 [사용 조건](https://aka.ms/vsls-license) 및 [개인정보처리방침](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)에 동의한 것입니다. 문제가 있는 경우 [문제 해결](troubleshooting.md)을 참조하세요.

이것이 전부입니다! 이제 VS Code 왼쪽 하단에는 로그인 상태 표시줄이 표시되고 Visual Studio 오른쪽 상단에는 [공유] 단추가 표시됩니다. 다음으로 수행할 작업은 이 설명서의 나머지 부분에서 확인해 보세요.


## <a name="see-also"></a>참고 항목

빠른 시작

- [첫 번째 프로젝트 공유](quickstart/share.md)
- [첫 번째 세션 참가](quickstart/join.md)

방법

- [Visual Studio Code를 사용하여 공동 작업](use/vscode.md)
- [Visual Studio를 사용하여 공동 작업](use/vs.md)

참조

- [Live Share 연결 요구 사항](reference/connectivity.md)
- [Live Share의 보안 기능](reference/security.md)
- [언어 및 플랫폼 지원](reference/platform-support.md)
- [확장 지원](reference/extensions.md)
- [릴리스 정보](https://aka.ms/vsls-releases)

문제가 있으신가요? [문제 해결](troubleshooting.md)을 참조하거나 [피드백을 제공](support.md)해 주세요.
