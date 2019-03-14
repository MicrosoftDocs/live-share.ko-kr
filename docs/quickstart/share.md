---
title: 빠른 시작-Visual Studio Live Share를 공유 합니다. | Microsoft Docs
description: Visual Studio Live Share 공동 작업 세션을 사용 하 여 첫 번째 프로젝트를 공유에 대 한 요약된 연습 합니다.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 3596b25dc0d08962d7813f52549dbe6fef4f00a0
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255849"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>빠른 시작: 첫 번째 프로젝트를 공유 합니다.

> **참고: Visual Studio Live Share는 현재 미리 보기 상태입니다. 사용자 환경과 기능은 최종 상태가 아닙니다.**

Visual Studio Live Share를 시작합니다. Live Share를 사용하면 사용 중인 프로그래밍 언어나 빌드 중인 앱 유형에 관계 없이 다른 사람과 공동으로 실시간 편집 및 디버깅이 가능합니다. 현재 프로젝트를 즉시 안전하게 공유한 다음, 필요에 따라 디버깅 세션, 터미널 인스턴스, 로컬 호스트 웹앱, 음성 통화 등을 공유할 수 있습니다.

진행할 준비가 되셨나요?  따라서 신속 하 고, 그럴 필요가 어려워집니다 팀 공동 작업 해야! 이러한 이유로 Visual Studio Live Share 손쉽게 시작 작업 및 아이디어 공유를 원활 하 게 시작할 수 있도록 합니다.

> [!TIP]
> *사용자 고유의 공동 작업 세션에 가입*할 수 있다는 것을 알고 계셨나요? 그러면 직접 Live Share를 시도해 보거나 Visual Studio 또는 VS Code의 인스턴스를 전환하고 원격으로 연결할 수 있습니다. 두 인스턴스 모두에 동일한 id를 사용할 수도 있습니다. 확인해 보세요.

공유를 시작 하려면 다음이 단계를 수행 합니다.

## <a name="1-install-the-extension"></a>1. 확장 설치

확장을 설치 하는 것은 쉽습니다. 다음이 단계를 수행 합니다.

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
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide.svg" width="128px" alt="Visual Studio logo" /></td>
    <td style="border:none;">
        <strong>Visual Studio 2017 15.6 이상</strong><br />
        1. Windows(7, 8.1 또는 10)에 최신 버전의 <a href="https://visualstudio.microsoft.com/vs/">Visual Studio 2017</a>(15.6 이상)을 설치합니다.<br/>
        2. <a href="../reference/platform-support.md">지원되는 워크로드</a>를 설치합니다. (예: ASP.NET, .NET Core, C++ 및/또는 Node.js)<br />
        3. 마켓플레이스에서 Visual Studio Live Share 확장을 다운로드하여 설치합니다. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button"></a><br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-preview.svg" width="128px" alt="Visual Studio Preview logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. <a href="https://aka.ms/vs-preview">Visual Studio 2019</a>의 최신 미리 보기 버전을 설치합니다.<br/>
        2. <a href="../reference/platform-support.md">지원되는 워크로드</a>를 설치합니다. (예: ASP.NET, .NET Core, C++ 및/또는 Node.js)<br />
        3. Visual Studio Live Share는 기본적으로 이러한 워크로드와 함께 설치됩니다. <br />
    </td>
</tr>
</table>

Visual Studio Live Share를 다운로드하여 사용하면 [사용 조건](https://aka.ms/vsls-license) 및 [개인정보처리방침](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)에 동의한 것입니다. 문제가 있는 경우 [문제 해결](../troubleshooting.md)을 참조하세요.

## <a name="2-sign-in"></a>2. 로그인

Live Share 확장을 설치 하 고 다시 시작 (VS Code) 설치를 완료 하는 종속성에 대 한 대기를 후 다른 참가자에 게 들을 수 있도록 하려면에 로그인 합니다. "Live Share" 상태 표시줄 항목 (VS Code)를 클릭 하면 됩니다 / "로그인" 단추 (VS)를 시작 합니다.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

**VS Code**, 알림을 시작에 로그인 하 라는 메시지가 표시 되는 동안 브라우저가 시작 됩니다. 로그인 한 브라우저에서 프로세스를 완료 한 다음 수행 하는 경우 브라우저를 닫기만 합니다.

![웹 브라우저를 사용 하 여 로그인 하 라는 알림](../media/vscode-sign-in-toast.png)

> **Linux 사용자:** Live Share의 이전 버전을 사용 하는 경우 사용자 코드를 입력 하 라는 메시지가 표시 될 수 있습니다 (v0.3.295 이하로). 확장의 최신 버전으로 업데이트 하거나는 "문제가?"를 클릭 합니다. 에 연결할 로그인 한 후 코드를 참조 하세요. 참조 [대 한 자세한 내용은 여기](../use/vscode.md#sign-in-using-a-user-code)합니다.

**Visual Studio**, Live Share를 자동으로 사용 하 [개인 설정 계정을](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)합니다. 결과적으로 로그인 할 수 있습니다 단순히 평소 대로 합니다. Visual Studio 개인 설정 계정을 보다 다른 로그인을 사용 하려는 경우으로 이동 하는 반면 **도구 &gt; 옵션 &gt; Live Share &gt; 사용자 계정** 다른 자격 증명을 선택 합니다.

참조 [문제 해결](../troubleshooting.md#sign-in) 문제가 발생 하는 경우.

## <a name="3-open-a-folder-project-or-solution"></a>3. 폴더, 프로젝트 또는 솔루션 열기

일반 워크플로 사용 하 여 폴더, 프로젝트 또는 Visual Studio 또는 Visual Studio Code에서 공유 하려는 솔루션을 엽니다.

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [선택 사항] 업데이트 숨기 거 나 파일 제외

기본적으로 Live Share **숨깁니다** 게스트에서 공유 폴더에.gitignore 파일에서 참조 하는 파일/폴더입니다. **숨기기** 파일 게스트의 파일 트리를 나타나지 않게 방지 합니다. **제외** 파일에서 정의 또는 파일에 디버깅 하거나 되 고 "다음" 하는 동안 단계 경우로 이동 하는 경우 게스트에 대 한 열기 Live Share를 방지 하는 보다 엄격한 규칙을 적용 합니다. 다른 파일 숨기기/제외 하려는 경우는 **. vsls.json** 이러한 설정 사용 하 여 프로젝트에 파일을 추가할 수 있습니다. 참조 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility) 세부 정보에 대 한 합니다.

## <a name="5-start-a-collaboration-session"></a>5. 공동 작업 세션 시작

다음으로 도구 내에서 "Live Share"를 간단히 클릭 하 고 초대 링크를 자동으로 클립보드에 복사 됩니다.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> Live Share 에이전트를 처음 공유 포트를 열 수 있도록 데스크톱 방화벽 소프트웨어에서 묻는 메시지가 될 수 있습니다. 이 완전히 선택적이 수락 하지만 보안된 "직접 모드를"를 사용 하도록 설정 된 동일한 네트워크에서 사용 하는 사용자는 성능을 향상 시키려면 합니다. 참조 [연결 모드를 변경](../reference/connectivity.md#changing-the-connection-mode) 세부 정보에 대 한 합니다.

## <a name="6-optional-enable-read-only-mode"></a>6. [선택 사항] 읽기 전용 모드 사용

공동 작업 세션을 시작 하면 게스트 공유 되는 코드를 편집 하지 못하도록 방지 하기 위해 읽기 전용 세션을 설정할 수 있습니다.

를 공유한 후 초대 링크를 클립보드에 복사 되는 알림을 받게 됩니다. 그런 다음 읽기 전용 세션을 설정 하는 옵션을 선택할 수 있습니다.

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

**VS Code**, Live Share viewlet 탭에서 읽기 전용 세션을 시작할 수도 있습니다.

![웹 브라우저를 사용 하 여 로그인 하 라는 알림](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7. 초대 링크 보내기

전자 메일, Slack 통해 링크를 보낼, 초대 하려는 하는 등 Skype. 브라우저에서 링크를 열면 폴더, 프로젝트 또는 열어 놓은 솔루션의 콘텐츠를 공유 하는 공동 작업 세션에 참가할 수 있습니다. 참고의 수준에 액세스 하는 Live Share 세션 게스트를 제공할 수 있습니다 **신뢰 하는 사용자와 공유 해야** 공유 하는 항목의 의미를 검토 하 고 있습니다.

> **보안 팁:** Live Share의 기능 중 일부의 보안 의미를 이해 하 시겠습니까? 체크 아웃 합니다 [보안](../reference/security.md) 문서.

초대한 게스트에 질문을 하는 경우는 [빠른 시작: 첫 번째 세션](join.md) 문서 시작 게스트로 실행 중에 몇 가지 자세한 정보를 제공 합니다.

## <a name="8-optional-approve-the-guest"></a>8. [선택 사항] 승인 게스트

기본적으로 게스트 공동 작업 세션을 자동으로 조인 하 고 작업을 수행 준비가 되 면 알림이 표시 됩니다.

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

조인 대신 사용자에 게 명시적 "승인"을 요구 하도록 선택할 수 있습니다. 이 설정을 켜면 경우 알림을 해당 세션에 참가 하려고 할 때 게스트를 승인 하 라는 메시지가 나타납니다.

참조 [게스트 승인이 필요한](../reference/security.md#requiring-guest-approval) 이 기능을 사용 하는 방법에 대 한 세부 정보에 대 한 합니다.

## <a name="9-collaborate"></a>9. 공동 작업.

정말 간단하죠. 게스트에 연결 하 되 면 사용해 몇 가지는 다음과 같습니다.

1. 일부 편집 하 고 이동 하지는 프로젝트의 다른 파일에 독립적으로
1. 게스트를 따르고 관찰 스크롤하여 고 편집을 수행 하 고 다른 파일로 이동
1. 사람과 함께 디버깅 세션을 시작 합니다.
1. 자신의 컴퓨터에서 실행 되는 웹 앱과 같은 코드를 확인할 수 있습니다 서버 공유
1. 터미널을 공유 하 고 몇 가지 명령을 실행 합니다.

체크 아웃 합니다 [Visual Studio Code](../use/vscode.md) 하 고 [Visual Studio](../use/vs.md) 등 이러한 작업을 수행 하는 방법에 대 한 정보에 대 한 확장 문서입니다.

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.

## <a name="next-steps"></a>다음 단계

자세한 내용은 이러한 추가 문서를 확인 합니다.

- [빠른 시작: 첫 번째 공동 작업 세션에 참가](join.md)
- [방법: Visual Studio Code를 사용 하 여 공동 작업](../use/vscode.md)
- [방법: Visual Studio를 사용 하 여 공동 작업](../use/vs.md)

참조

- [Live Share 연결 요구 사항](../reference/connectivity.md)
- [Live Share의 보안 기능](../reference/security.md)
- [언어 및 플랫폼 지원](../reference/platform-support.md)
- [확장 지원](../reference/extensions.md)
