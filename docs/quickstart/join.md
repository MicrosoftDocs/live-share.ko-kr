---
title: 빠른 시작-Visual Studio Live Share 참여 | Microsoft Docs
description: 첫 번째 Visual Studio Live Share 공동 작업 세션에 참가 대 한 요약된 연습 합니다.
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
ms.openlocfilehash: d4280484aaa3fd4ac204588bf4aefc4e3ac51871
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256066"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>빠른 시작: 첫 번째 공동 작업 세션에 참가

> **참고: Visual Studio Live Share는 현재 미리 보기 상태입니다. 사용자 환경과 기능은 최종 상태가 아닙니다.**

Visual Studio Live Share를 시작합니다. Live Share를 사용하면 사용 중인 프로그래밍 언어나 빌드 중인 앱 유형에 관계 없이 다른 사람과 공동으로 실시간 편집 및 디버깅이 가능합니다. 안전 하 고 즉시 현재 프로젝트를 팀원과 연결 및 디버깅 세션을 체결할 필요에 따라 다음 터미널 인스턴스 편집을 보고 localhost 웹 앱, 조인 음성 통화 등 참조 할 수 있습니다.

진행할 준비가 되셨나요? 따라서 신속 하 고, 그럴 필요가 어려워집니다 팀 공동 작업 해야! 이러한 이유로 Visual Studio Live Share 손쉽게 시작 작업 및 아이디어 공유를 원활 하 게 시작할 수 있도록 합니다.

> [!TIP]
> *사용자 고유의 공동 작업 세션에 가입*할 수 있다는 것을 알고 계셨나요? 그러면 직접 Live Share를 시도해 보거나 Visual Studio 또는 VS Code의 인스턴스를 전환하고 원격으로 연결할 수 있습니다. 두 인스턴스 모두에 동일한 ID를 사용할 수도 있습니다. 확인해 보세요.

공동 작업 세션에 참가 하려면 다음이 단계를 수행 합니다.

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
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
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

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [VS Code에서 읽기 전용 게스트로 선택 사항] 조인

VS Code에서 이후 Live Share 확장을 설치, 다시 시작 및 종속성에 대 한 대기 중인 설치를 완료 하려면 이동할 수 있으며 읽기 전용 게스트로 공동 작업 세션에 참가 수 있습니다.

> [!NOTE]
> 조인 하는 코드를 편집 하려는 경우 할 [로그인](../quickstart/join.md#3-Sign-in)합니다.

브라우저에서 초대 링크를 엽니다 (또는 다시 열) 및 브라우저가 VS Code를 시작 하는 알림을 받게 됩니다. 를 시작할 수 있도록 하 고 공동 작업 세션과 연결할 시작 됩니다.

VS Code를 시작 하는 경우에 로그인 하 라는 알림 메시지를 받게 됩니다. "읽기 전용 게스트로 Continue"를 선택 합니다. 세션에 참가 하기.

![읽기 전용으로 게스트 알림 세션으로 조인](../media/vscode-read-only-guest.png)

참가자는 세션에서 사용자를 식별 하는 데 표시 이름을 입력 하 라는 메시지가 표시 됩니다.

![읽기 전용으로 게스트 이름](../media/vscode-read-only-guest-name.png)

그런 다음 읽기 전용으로 세션으로 있습니다 조인 됩니다. 보기 및 탐색 코드, 공동 디버그 하 고 서버 공유 보기 및 터미널 (읽기 전용) 하는 일을 할 수 있습니다.

> [!NOTE]
> 나중에 코드에 대 한 읽기/쓰기 액세스를 get 하려는 경우 로그인 할 수 있습니다. 상태 표시줄과 선택 옵션을 "로그인"의 표시 이름을 클릭 합니다.
![읽기 전용으로 게스트 로그인](../media/vscode-read-only-guest-signin.png) 브라우저 시작 됩니다 하 고 로그인 하는 데는 Microsoft 또는 GitHub 계정을 선택할 수 있습니다.

## <a name="3-sign-in"></a>3. 로그인

Live Share 확장을 설치 하 고 다시 시작 (VS Code) 설치를 완료 하는 종속성에 대 한 대기를 후 다른 참가자에 게 들을 수 있도록 하려면에 로그인 합니다. 이 단계를 건너뛰면 조인 프로세스 중에 로그인 하 라는 메시지가 표시 됩니다 또는 읽기 전용 게스트로 세션에 참가할 수 있습니다. "로그인" / "공유" 상태 표시줄 항목 (VS Code)를 클릭 합니다. 단추 (VS)를 시작 합니다.

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

**VS Code**, 알림을 시작에 로그인 하 라는 메시지가 표시 되는 동안 브라우저가 시작 됩니다. 로그인 한 브라우저에서 프로세스를 완료 한 다음 수행 하는 경우 브라우저를 닫기만 합니다.

![웹 브라우저를 사용 하 여 로그인 하 라는 알림](../media/vscode-sign-in-toast.png)

> **Linux 사용자:** Live Share의 이전 버전을 사용 하는 경우 사용자 코드를 입력 하 라는 메시지가 표시 될 수 있습니다 (v0.3.295 이하로). 확장의 최신 버전으로 업데이트 하거나는 "문제가?"를 클릭 합니다. 에 연결할 로그인 한 후 코드를 참조 하세요. 참조 [대 한 자세한 내용은 여기](../use/vscode.md#sign-in-using-a-user-code)합니다.

**Visual Studio**, Live Share를 자동으로 사용 하 [개인 설정 계정을](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)합니다. 결과적으로 로그인 할 수 있습니다 단순히 평소 대로 합니다. Visual Studio 개인 설정 계정을 보다 다른 로그인을 사용 하려는 경우으로 이동 하는 반면 **도구 &gt; 옵션 &gt; Live Share &gt; 사용자 계정** 다른 자격 증명을 선택 합니다.

참조 [문제 해결](../troubleshooting.md#sign-in) 문제가 발생 하는 경우.

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4. Open/다시-open 초대 브라우저 링크

이제 단순히 (열거나 다시) 브라우저의 초대 링크 합니다.

> **참고**: Live Share 확장을 아직 설치 하지 않은 경우 확장 marketplace에 대 한 링크를 사용 하 여 표시 될 수 있습니다. 확장을 설치 하는 도구를 다시 시작 하 고 다시 시도 하십시오.

사용자 브라우저가 사용 하도록 설정 하는 Live Share는 도구를 시작 하는 알림을 받게 됩니다. 선택한 도구를 시작 하는 경우, 시작 되 면 공동 작업 세션에 연결 될 수 있습니다.

![가입 페이지](../media/join-page.png)

호스트가 오프 라인 상태인 경우 알려 주도록이 시점에서 대신 합니다. 그런 다음 호스트에 연결 하 고 요청을 다시 공유할 수 있습니다.

> **문제 해결 팁:** VS Code를 사용 하는 경우 해야 하면 **도구를 한 번 이상 시작** 후 확장을 설치 하 고 설치를 완료 하려면 종속성을 기다리는 (상태 표시줄 참조) 열기/다시-opening 초대 페이지 전에 합니다. 그래도 문제가 있나요? 참조 [수동으로 조인](../reference/manual-join.md) 세부 정보에 대 한 합니다.

## <a name="5-collaborate"></a>5. 공동 작업.

정말 간단하죠. 몇 분에서 동료의 공동 작업 세션에 연결 될 수 있습니다. 기본적으로 호스트 자동 수락 하지만 호스트 하도록 설정 하는 경우 조인 하는 사람들이 [게스트 승인을](../reference/security.md#requiring-guest-approval) 상태 표시줄이 표시 / 참여 요청을 승인 하려면 호스트에서 Live Share를 기다리고 있는 대화 멘 션을 조인 합니다.

> **보안 팁:** 가 공동 작업 세션에 참가 게스트로 호스트 특정 파일이 나 기능에 대 한 액세스를 제한할 수 있습니다는 이해 해야 합니다. Live Share의 기능 및 설정 중 일부의 보안 의미를 이해 하 시겠습니까? 체크 아웃 합니다 [보안](../reference/security.md) 문서.

사용해 몇 가지는 다음과 같습니다.

1. 독립적으로 프로젝트 해결 하지 이동 하 여 일부 편집
2. Javascript, TypeScript, 체크 아웃 작업 intellisense 및/또는 C# 코드
3. 호스트와 함께 항목 편집
4. 호스트를 따르고 이동 하며 서로 다른 파일에서 편집할으로 이동
5. 호스트와 함께 디버깅 세션을 시작 합니다.
6. 자신의 컴퓨터에서 실행 되는 웹 앱과 같은 코드을 확인할 수 있도록 서버를 공유 하는 호스트를 요청 합니다.
7. 터미널을 공유 하 고 몇 가지 명령을 실행 하려면 호스트를 요청 합니다.

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.

## <a name="next-steps"></a>다음 단계

자세한 내용은 이러한 추가 문서를 확인 합니다.

- [빠른 시작: 첫 번째 프로젝트를 공유 합니다.](share.md)
- [방법: Visual Studio Code를 사용 하 여 공동 작업](../use/vscode.md)
- [방법: Visual Studio를 사용 하 여 공동 작업](../use/vs.md)

참조

- [Live Share 연결 요구 사항](../reference/connectivity.md)
- [Live Share의 보안 기능](../reference/security.md)
- [언어 및 플랫폼 지원](../reference/platform-support.md)
- [확장 지원](../reference/extensions.md)
