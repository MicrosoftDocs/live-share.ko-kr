---
title: 빠른 시작 공유 - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share 공동 작업 세션을 사용하여 첫 번째 프로젝트를 공유하는 방법에 대해 간략히 설명합니다.
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
ms.openlocfilehash: e65656c604a9dbc479a03a503fe01d7e2d938072
ms.sourcegitcommit: c702aafb65b0fc43cb210e1bb7340cef48b57f35
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2019
ms.locfileid: "67322785"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>빠른 시작: 첫 번째 프로젝트 공유

Visual Studio Live Share를 시작합니다. Live Share를 사용하면 사용 중인 프로그래밍 언어나 빌드 중인 앱 유형에 관계 없이 다른 사람과 공동으로 실시간 편집 및 디버깅이 가능합니다. 현재 프로젝트를 즉시 안전하게 공유한 다음, 필요에 따라 디버깅 세션, 터미널 인스턴스, 로컬 호스트 웹앱, 음성 통화 등을 공유할 수 있습니다.

진행할 준비가 되셨나요?  팀 공동 작업은 매우 빠르고 자연스러워서 작업을 수행하기 쉽습니다. 이러한 이유로 Visual Studio Live Share를 사용하면 간편하게 시작할 수 있으므로 작업과 아이디어를 원활하게 공유할 수 있습니다.

> [!TIP]
> *사용자 고유의 공동 작업 세션에 가입*할 수 있다는 것을 알고 계셨나요? 그러면 직접 Live Share를 시도해 보거나 Visual Studio 또는 VS Code의 인스턴스를 전환하고 원격으로 연결할 수 있습니다. 두 인스턴스 모두에 동일한 ID를 사용할 수도 있습니다. 확인해 보세요.

공유를 시작하려면 다음 단계를 수행합니다.
<!--
Change the instructions to Install extension for VS Code and in-tool for VS?
-->
## <a name="1-install-the-extension"></a>1. 확장 설치

확장을 설치하는 것은 쉽습니다. 다음 단계를 따르기만 하면 됩니다.

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code(1.22.0 이상)</strong><br />
        1.Windows(7, 8.1 또는 10), macOS<b>(Sierra+)</b>, 64비트 Linux용 <a href="https://code.visualstudio.com/">Visual Studio Code</a>를 설치합니다<b>(<a href="../use/vscode.md#installation">세부 정보</a>)</b>.<br />
        2. 마켓플레이스에서 Visual Studio Live Share 확장을 다운로드하여 설치합니다. <br />
        3. 다시 로드하고 종속성이 다운로드되어 설치될 때까지 기다립니다(상태 표시줄 참조).<br />
        4. <strong>Linux</strong>: <a href="../reference/linux.md#install-linux-prerequisites">라이브러리를 설치</a>하라는 메시지가 표시되면 [설치]를 클릭하고 암호를 입력한 다음, 완료되면 VS Code를 다시 시작합니다.<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="../media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1.<a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>를 설치합니다.<br/>
        2. <a href="../reference/platform-support.md">지원되는 워크로드</a>를 설치합니다. (예: ASP.NET, .NET Core, C++, Python 및/또는 Node.js)<br />
        3. Visual Studio Live Share는 기본적으로 이러한 워크로드와 함께 설치됩니다. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 이상</strong><br />
        1. Windows(7, 8.1 또는 10)에 최신 버전의 <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a>(15.6 이상)을 설치합니다.<br/>
        2. <a href="../reference/platform-support.md">지원되는 워크로드</a>를 설치합니다. (예: ASP.NET, .NET Core, C++ 및/또는 Node.js)<br />
        3. 마켓플레이스에서 Visual Studio Live Share 확장을 다운로드하여 설치합니다. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Visual Studio Live Share를 다운로드하여 사용하면 [사용 조건](https://aka.ms/vsls-license) 및 [개인정보처리방침](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)에 동의한 것입니다. 문제가 있는 경우 [문제 해결](../troubleshooting.md)을 참조하세요.

## <a name="2-sign-in"></a>2. 로그인

<!--
Re-write the grammar here- run on sentence does not make sense. Change screen shots. There is another way of signing in as well- what if a user goes directly to the start collaboration. 
-->
Live Share 확장을 설치하고, 다시 시작하고 종속성 설치(VS Code)가 완료될 때까지 기다린 후 로그인하여 다른 참가자에게 사용자가 누구인지 알릴 수 있습니다. 시작하려면 "Live Share" 상태 표시줄 항목(VS Code) / "로그인" 단추(VS)를 클릭하기만 하면 됩니다.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button-new.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
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

## <a name="3-open-a-folder-project-or-solution"></a>3. 폴더, 프로젝트 또는 솔루션 열기

일반 워크플로를 사용하여 Visual Studio 또는 Visual Studio Code에서 공유하려는 폴더, 프로젝트 또는 솔루션을 엽니다.

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [선택 사항] 숨겨진 파일 또는 제외된 파일 업데이트

기본적으로 Live Share는 게스트의 공유 폴더에 있는 .gitignore 파일에서 참조하는 모든 파일/폴더를 **숨깁니다**. 파일을 **숨기면** 게스트의 파일 트리에 나타나지 않습니다. 파일을 **제외하면** 정의로 이동하거나 디버깅 또는 "추적" 중에 파일로 들어오는 등의 상황에서 Live Share가 게스트를 열 수 없도록 보다 엄격한 규칙을 적용합니다. 다른 파일을 숨기거나 제외하려는 경우, 이러한 설정으로 **.vsls.json** 파일을 프로젝트에 추가할 수 있습니다. 자세한 내용은 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility)를 참조하세요.

## <a name="5-start-a-collaboration-session"></a>5. 공동 작업 세션 시작

<!--
-->
그런 다음, 도구 내에서 "Live Share"를 클릭하기만 하면 초대 링크가 자동으로 클립보드에 복사됩니다.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button-new.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> 처음 공유할 때 데스크톱 방화벽 소프트웨어에서 Live Share 에이전트가 포트를 열 수 있도록 허용하라는 요청을 받을 수 있습니다. 이 옵션을 수락하는 것은 전적으로 선택 사항이지만, 작업하는 사람이 사용자와 동일한 네트워크에 있을 때 보안된 "직접 모드"로 성능을 향상시킬 수 있습니다. 자세한 내용은 [연결 모드 변경](../reference/connectivity.md#changing-the-connection-mode)을 참조하세요.

## <a name="6-optional-enable-read-only-mode"></a>6. [선택 사항] 읽기 전용 모드 사용

공동 작업 세션을 시작하면 공유 중인 코드를 게스트가 편집하지 못하도록 세션을 읽기 전용으로 설정할 수 있습니다.

공유한 후에는 초대 링크가 클립보드에 복사되었다는 알림을 받게 됩니다. 그런 다음, 옵션을 선택하여 세션을 읽기 전용으로 만들 수 있습니다.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-read-only-toast.png" width="100%" alt="Visual Studio Code read-only option" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-read-only-notification.png" width="100%" alt="Visual Studio read-only option"/>
    </td>
</tr>
</table>

**VS Code**에서 Live Share viewlet 탭에서 읽기 전용 세션을 시작할 수도 있습니다.

![웹 브라우저를 사용하여 로그인하라는 알림 메시지](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7. 다른 사용자에게 초대 링크 보내기

초대할 사람에게 이메일, Slack, Skype 등을 통해 링크를 보냅니다. 브라우저에서 링크를 열면 사용자가 연 폴더, 프로젝트 또는 솔루션의 콘텐츠를 공유하는 공동 작업 세션에 조인할 수 있습니다. Live Share 세션이 게스트에게 제공할 수 있는 액세스 수준을 고려할 때 **신뢰하는 사용자와만 공유**하고 공유하는 내용의 의미를 검토해야 합니다.

> **보안 팁:** Live Share의 일부 기능이 보안에 미치는 영향을 알고 싶나요? [보안](../reference/security.md) 문서를 체크 아웃합니다.

초대한 게스트에게 질문이 있는 경우 [빠른 시작: 첫 번째 세션에 조인](join.md) 문서는 게스트로 시작하고 실행하는 방법에 대한 몇 가지 추가 정보를 제공합니다.

## <a name="8-optional-approve-the-guest"></a>8. [선택 사항] 게스트 승인

기본적으로 게스트는 자동으로 공동 작업 세션에 조인하고 작업을 수행할 준비가 되면 알림을 받게 됩니다.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

대신 조인하는 모든 사용자에게 명시적인 "승인"을 요구하도록 선택할 수 있습니다. 이 설정을 사용하도록 설정한 경우 게스트가 세션에 조인하려고 할 때 승인하라는 알림이 표시됩니다.

이 기능을 설정하는 방법에 대한 자세한 내용은 [게스트 승인 필요](../reference/security.md#requiring-guest-approval)를 참조하세요.

## <a name="9-collaborate"></a>9. 공동 작업!

정말 간단하죠. 게스트가 조인하면 시도할 몇 가지 항목은 다음과 같습니다.

1. 프로젝트의 여러 파일로 독립적으로 이동하여 일부 편집
1. 게스트를 따라 스크롤, 편집 수행 및 다른 파일로 이동하는 과정 확인
1. 함께 공동 디버깅 세션 시작
1. 해당 머신에서 실행 중인 웹앱과 같은 항목을 체크 아웃할 수 있도록 서버 공유
1. 터미널을 공유하고 일부 명령 실행

이러한 작업을 수행하는 방법 등에 대한 정보는 [Visual Studio Code](../use/vscode.md) 및 [Visual Studio](../use/vs.md) 확장 문서를 체크 아웃하세요.

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.

## <a name="next-steps"></a>다음 단계

자세한 내용은 이러한 추가 문서를 확인하세요.

- [빠른 시작: 첫 번째 공동 작업 세션에 조인](join.md)
- [방법: Visual Studio Code를 사용하여 공동 작업](../use/vscode.md)
- [방법: Visual Studio를 사용하여 공동 작업](../use/vs.md)

참조

- [Live Share 연결 요구 사항](../reference/connectivity.md)
- [Live Share의 보안 기능](../reference/security.md)
- [언어 및 플랫폼 지원](../reference/platform-support.md)
- [확장 지원](../reference/extensions.md)
