---
title: 빠른 시작 조인 - Visual Studio Live Share | Microsoft Docs
description: 첫 번째 Visual Studio Live Share 공동 작업 세션에 조인하는 방법에 대해 간략히 설명합니다.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: c5c86b158facfe1fe8fa7f5ae14a9511c55e0877
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58853549"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>빠른 시작: 첫 번째 공동 작업 세션에 조인

Visual Studio Live Share를 시작합니다. Live Share를 사용하면 사용 중인 프로그래밍 언어나 빌드 중인 앱 유형에 관계 없이 다른 사람과 공동으로 실시간 편집 및 디버깅이 가능합니다. 이를 통해 팀원의 현재 프로젝트에 즉시 안전하게 조인한 다음, 필요에 따라 디버깅 세션을 시작하고, 터미널 인스턴스를 보고 편집하고, 로컬 호스트 웹앱을 보고 음성 통화에 조인하는 등의 작업을 수행할 수 있습니다.

진행할 준비가 되셨나요? 팀 공동 작업은 매우 빠르고 자연스러워서 작업을 수행하기 쉽습니다. 이러한 이유로 Visual Studio Live Share를 사용하면 간편하게 시작할 수 있으므로 작업과 아이디어를 원활하게 공유할 수 있습니다.

> [!TIP]
> *사용자 고유의 공동 작업 세션에 가입*할 수 있다는 것을 알고 계셨나요? 그러면 직접 Live Share를 시도해 보거나 Visual Studio 또는 VS Code의 인스턴스를 전환하고 원격으로 연결할 수 있습니다. 두 인스턴스 모두에 동일한 ID를 사용할 수도 있습니다. 확인해 보세요.

공동 작업 세션에 조인하려면 다음 단계를 수행합니다.

## <a name="1-install-the-extension"></a>1. 확장 설치

확장을 설치하는 것은 쉽습니다. 다음 단계를 따르기만 하면 됩니다.

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code(1.22.0 이상)</strong><br />
        1. Windows(7, 8.1 또는 10), macOS<b>(Sierra+)</b>, 64비트 Linux용 <a href="https://code.visualstudio.com/">Visual Studio Code</a>를 설치합니다<b>(<a href="../use/vscode.md#installation">세부 정보</a>)</b>.<br />
        2. Marketplace에서 Visual Studio Live Share 확장을 다운로드하여 설치합니다. <br />
        3. 다시 로드하고 종속성이 다운로드되어 설치될 때까지 기다립니다(상태 표시줄 참조).<br />
        4. <strong>Linux</strong>: <a href="../reference/linux.md#install-linux-prerequisites">라이브러리를 설치</a>하라는 메시지가 표시되면 [설치]를 클릭하고 암호를 입력한 다음, 완료되면 VS Code를 다시 시작합니다.<br />
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>를 설치합니다.<br/>
        2. <a href="../reference/platform-support.md">지원되는 워크로드</a>를 설치합니다. (예: ASP.NET, .NET Core, C++ 및/또는 Node.js)<br />
        3. Visual Studio Live Share는 기본적으로 이러한 워크로드와 함께 설치됩니다. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 이상</strong><br />
        1. Windows(7, 8.1 또는 10)에 최신 버전의 <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a>(15.6 이상)을 설치합니다.<br/>
        2. <a href="../reference/platform-support.md">지원되는 워크로드</a>를 설치합니다. (예: ASP.NET, .NET Core, C++ 및/또는 Node.js)<br />
        3. Marketplace에서 Visual Studio Live Share 확장을 다운로드하여 설치합니다. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Visual Studio Live Share를 다운로드하여 사용하면 [사용 조건](https://aka.ms/vsls-license) 및 [개인정보처리방침](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)에 동의한 것입니다. 문제가 있는 경우 [문제 해결](../troubleshooting.md)을 참조하세요.

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [선택 사항] VS Code에서 읽기 전용 게스트로 조인

VS Code에서 Live Share 확장 설치, 다시 시작 및 종속성 설치가 완료될 때까지 기다린 후 로그인하여 읽기 전용 게스트로 공동 작업 세션에 조인할 수 있습니다.

> [!NOTE]
> 조인할 코드를 편집하려면 로그인해야 합니다.

브라우저에서 초대 링크를 열거나 다시 열면 브라우저에서 VS Code를 시작하려고 한다는 알림을 받게 됩니다. 시작하면 공동 작업 세션에 연결됩니다.

VS Code가 시작되면 로그인하라는 알림 메시지를 받게 됩니다. 세션에 조인하려면 "읽기 전용 게스트로 계속 진행"을 선택합니다.

![읽기 전용 게스트 알림으로 세션에 조인](../media/vscode-read-only-guest.png)

참가자가 세션에서 사용자를 식별할 수 있도록 표시 이름을 입력하라는 메시지가 표시됩니다.

![읽기 전용 게스트 이름](../media/vscode-read-only-guest-name.png)

그런 다음, 읽기 전용으로 세션에 조인하게 됩니다. 코드를 보면서 탐색하고, 공동 디버그하고, 공유 서버와 터미널(읽기 전용)을 볼 수 있습니다.

> [!NOTE]
> 나중에 코드에 대한 읽기/쓰기 액세스 권한을 가져오려는 경우 로그인할 수 있습니다. 상태, 표시줄에서 표시 이름을 클릭하고 "로그인" 옵션을 선택합니다.
![읽기 전용 게스트 로그인](../media/vscode-read-only-guest-signin.png) 이렇게 하면 브라우저가 시작되고 Microsoft 또는 GitHub 계정을 선택하여 로그인할 수 있습니다.

## <a name="3-sign-in"></a>3. 로그인

Live Share 확장을 설치하고, 다시 시작하고 종속성 설치(VS Code)가 완료될 때까지 기다린 후 로그인하여 다른 참가자에게 사용자가 누구인지 알릴 수 있습니다. 이 단계를 건너뛰면 조인 프로세스 중에 로그인하라는 메시지가 표시되거나 읽기 전용 게스트로 세션에 조인할 수 있습니다. 시작하려면 “Live Share” 상태 표시줄 항목(VS Code)/“로그인” 단추(VS)를 클릭합니다.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

**VS Code**에서 브라우저가 실행되는 동안 로그인하라는 알림이 표시됩니다. 브라우저에서 로그인 프로세스를 완료한 다음, 완료될 때 브라우저를 닫기만 하면 됩니다.

![웹 브라우저를 사용하여 로그인하라는 알림 메시지](../media/vscode-sign-in-toast.png)

> **Linux 사용자:** 이전 버전의 Live Share(v0.3.295 이하)를 사용하는 경우 사용자 코드를 입력하라는 메시지가 표시될 수 있습니다. 확장의 최신 버전으로 업데이트하거나 "문제가 있나요?"를 클릭합니다. 로그인한 후 링크를 클릭하여 코드를 확인합니다. [자세한 내용은 여기](../use/vscode.md#sign-in-using-a-user-code)를 참조하세요.

**Visual Studio**에서 Live Share는 [개인 설정 계정](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)을 자동으로 사용합니다. 그 결과 평소대로 간단하게 로그인할 수 있습니다. 그러나 Visual Studio 개인 설정 계정과 다른 로그인을 사용하려는 경우에는 **도구 &gt; 옵션 &gt; Live Share &gt; 사용자 계정**으로 이동하여 다른 자격 증명을 선택합니다.

여전히 문제가 발생하는 경우에는 [문제 해결](../troubleshooting.md#sign-in)을 참조하세요.

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4. 브라우저에서 초대 링크 열기/다시 열기

이제 브라우저에서 초대 링크를 열거나 다시 열면 됩니다.

> **참고**: Live Share 확장을 아직 설치하지 않은 경우 확장 마켓플레이스에 대한 링크가 표시됩니다. 확장을 설치하고, 도구를 다시 시작하고, 다시 시도합니다.

브라우저에서 Live Share 활성화 도구를 시작하려고 한다는 알림을 받게 됩니다. 선택한 도구를 실행하게 되면 시작한 후에 공동 작업 세션에 연결됩니다.

![참가 페이지](../media/join-page.png)

호스트가 오프라인 상태인 경우, 대신 이 시점에서 알림을 받게 됩니다. 그런 다음, 호스트에 연결하여 다시 공유하도록 요청할 수 있습니다.

> **문제 해결 팁:** VS Code를 사용하는 경우 확장 설치 후 **도구를 한 번 이상 시작**했는지 확인하고, 종속성 설치가 완료(상태 표시줄 참조)될 때까지 기다린 후 초대 페이지를 열거나 다시 엽니다. 그래도 문제가 있나요? 자세한 내용은 [수동으로 조인](../reference/manual-join.md)을 참조하세요.

## <a name="5-collaborate"></a>5. 공동 작업!

정말 간단하죠. 잠시 후 동료의 공동 작업 세션에 연결됩니다. 기본적으로 호스트는 조인하는 사람을 자동으로 수락하지만 호스트가 [게스트 승인 요청](../reference/security.md#requiring-guest-approval)을 설정한 경우, Live Share가 조인 요청을 승인하기 위해 호스트에서 대기 중이라는 상태 표시줄 / 조인 대화 상자가 나타납니다.

> **보안 팁:** 공동 작업 세션에 참가하는 게스트는 호스트가 특정 파일이나 기능에 대한 액세스를 제한할 수 있다는 것을 이해해야 합니다. Live Share의 일부 기능 및 설정이 보안에 미치는 영향을 알고 싶나요? [보안](../reference/security.md) 문서를 체크 아웃합니다.

다음과 같은 몇 가지 사항을 시도해 보세요.

1. 프로젝트를 독립적으로 이동하여 일부 편집
2. JavaScript, TypeScript 및/또는 C# 코드에 대한 작업 인텔리전스 체크 아웃
3. 호스트와 함께 항목 편집
4. 다른 파일을 탐색하고 편집할 때 호스트를 따라 이동
5. 호스트와 공동 디버깅 세션 시작
6. 호스트에서 서버를 공유하도록 해당 머신에서 실행 중인 웹앱과 같은 항목을 체크 아웃할 수 있습니다.
7. 호스트에 터미널을 공유하도록 요청하고 일부 명령 실행

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.

## <a name="next-steps"></a>다음 단계

자세한 내용은 이러한 추가 문서를 확인하세요.

- [빠른 시작: 첫 번째 프로젝트 공유](share.md)
- [방법: Visual Studio Code를 사용하여 공동 작업](../use/vscode.md)
- [방법: Visual Studio를 사용하여 공동 작업](../use/vs.md)

참조

- [Live Share 연결 요구 사항](../reference/connectivity.md)
- [Live Share의 보안 기능](../reference/security.md)
- [언어 및 플랫폼 지원](../reference/platform-support.md)
- [확장 지원](../reference/extensions.md)
