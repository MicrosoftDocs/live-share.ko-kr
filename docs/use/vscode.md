---
title: Visual Studio Code를 사용하여 공동 작업 - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Code 및 Live Share에 대한 공동 작업 방법 세트.
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: ed96ba572a58b8d3bfda7b634f1052a1b4e73051
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58853640"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>방법: Visual Studio Code를 사용하여 공동 작업

VS Code에서 Live Share를 사용하여 공동 작업을 할 준비가 됐나요?  그렇다면, 잘 오셨습니다. 이 문서에서는 Visual Studio Code에 대한 Visual Studio Live Share 확장에서 특정 기능 중 일부를 사용하는 방법을 살펴보겠습니다.

여기에 설명된 모든 공동 작업 활동은 한 명의 **공동 작업 세션 호스트**와 한 명 이상의 **게스트**로 구성됩니다. 호스트는 공동 작업 세션을 시작한 사람이며 여기에 참가한 모든 사람은 게스트입니다.

*요약 정보를 찾으시나요? 대신 [공유](../quickstart/share.md) 또는 [참가](../quickstart/join.md) 빠른 시작을 확인합니다.*

> [!TIP]
> *사용자 고유의 공동 작업 세션에 가입*할 수 있다는 것을 알고 계셨나요? 그러면 직접 Live Share를 시도해 보거나 Visual Studio 또는 VS Code의 인스턴스를 전환하고 원격으로 연결할 수 있습니다. 두 인스턴스 모두에 동일한 ID를 사용할 수도 있습니다. 확인해 보세요.

## <a name="installation"></a>설치

시작하기 전에 Live Share의 핵심 요구 사항을 충족하는 Visual Studio Code 버전이 설치되어 있는지 확인해야 합니다. **Visual Studio Code(1.22.0 이상)** 가 다음에서 실행되어야 합니다.

- **Windows**: 7, 8.1 또는 10

- **macOS**: Sierra 10.12 이상만 해당합니다.
    - _El Capitan 10.11 이하는 현재 [.NET Core 2.0 요구 사항](https://go.microsoft.com/fwlink/?linkid=872315) 때문에 지원되지 않습니다._

- **Linux**: 64비트 Ubuntu Desktop 16.04 이상, Fedora 워크스테이션 27 이상, CentOS 7

    - Live Share에는 설치하라는 메시지가 표시될 수 있는 많은 [Linux 필수 구성 요소](#linux-install-steps)가 필요합니다.
    - _32비트 Linux는 [.NET Core 2.0 요구 사항](https://go.microsoft.com/fwlink/?linkid=872314) 때문에 지원되지 않습니다._
    - ARM은 현재 지원되지 않습니다.
    - 다운스트림 및 기타 배포 사용에 대한 자세한 내용은 [Linux 설치 세부 정보](../reference/linux.md)를 참조하세요.

그 후에 Visual Studio Live Share 확장을 다운로드하여 설치하는 것은 쉽습니다.

1. <a href="https://code.visualstudio.com/">Visual Studio Code</a> 설치
2. Marketplace에서 Visual Studio Live Share 확장을 [다운로드](https://aka.ms/vsls-dl/vscode)하여 설치합니다.
3. Visual Studio Code 다시 로드
4. 종속성이 다운로드되어 설치될 때까지 기다립니다(상태 표시줄 참조).<br/>
    ![설치 완료](../media/vscode-finishing-install.png)
5. **Linux**: 누락된 라이브러리 설치 방법에 대한 알림을 확인하려면:
    1. 알림에서 "설치"를 클릭합니다.
    2. 메시지가 표시되면 관리자(sudo) 암호를 입력합니다.
    3. 완료된 경우 VS Code를 다시 시작합니다.

Visual Studio Live Share를 다운로드하여 사용하면 [사용 조건](https://aka.ms/vsls-license) 및 [개인정보처리방침](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)에 동의한 것입니다. 문제가 있는 경우 [문제 해결](../troubleshooting.md)을 참조하세요.

[![D다운로드](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Linux 설치 단계

Linux는 가변성이 큰 환경이며 데스크톱 환경 및 배포 수가 너무 많아 작업하는 데 복잡할 수 있습니다. **Ubuntu Desktop**(16.04 이상) 또는 **Fedora 워크스테이션**(27 이상), **CentOS 7**의 지원되는 버전을 계속 사용하거나 **VS Code의 공식 배포 버전**만 사용하는 경우 프로세스가 간단해야 합니다. 그러나 비표준 구성 또는 다운스트림 배포를 사용하는 경우 일부 문제가 발생할 수도 발생하지 않을 수도 있습니다. 자세한 내용은 [Linux 설치 세부 정보](../reference/linux.md)를 참조하세요.

#### <a name="install-linux-prerequisites"></a>Linux 필수 구성 요소 설치

일부 Linux 배포에는 Live Share가 작동하는 데 필요한 라이브러리가 누락되어 있습니다. 기본적으로 Live Share는 Linux 필수 구성 요소를 탐지하여 설치하려고 합니다. Live Share에서 누락된 라이브러리로 인해 문제가 발생하는 경우 해당 라이브러리를 설치하는 데 필요한 권한을 요청하는 알림 메시지가 표시됩니다.

![Linux 필수 구성 요소의 누락을 표시하는 알림 메시지](../media/vscode-linux-prereq-missing.png)

"설치"를 클릭하여 터미널 창이 표시되는 경우 계속하려면 관리자(sudo) 암호를 입력해야 합니다. 성공적으로 완료됐다고 가정하고 모두 설정해야 하는 Visual Studio Code를 다시 시작합니다! 다른 힌트 및 해결 방법이 있는 경우 **[배포별 팁](../reference/linux.md#tips-by-distribution)** 을 확인하려 할 수도 있습니다.

스크립트에서 배포를 지원하지 않는다는 메시지가 표시되면 커뮤니티가 공유한 **[커뮤니티 지원 배포 팁](../reference/linux.md#tips-for-community-supported-distros)** 을 참조하세요.

**VS Code가 명령을 실행하기 않기를 원하는** 경우 터미널 창에서 다음 명령을 실행하여 언제든지 수동으로 이 스크립트의 최신 버전을 다시 실행하도록 선택할 수도 있습니다.

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Linux 브라우저 통합

Visual Studio Live Share에는 일반적으로 Linux에서 브라우저 통합을 사용하기 위한 **추가 설치 단계가 필요하지 않습니다**.

일반적이지 않지만 특정 배포의 경우 설치 프로세스를 완료하려면 **관리자(sudo) 암호가 필요하다는 알림을 받을 수 있습니다**. 터미널 창이 표시돼 브라우저 시작 관리자를 설치할 위치를 알려줍니다. 메시지가 표시되면 단순히 암호를 입력하고 설치가 완료되면 Enter 키를 눌러 터미널 창을 닫습니다.

이 프로세스가 필요한 이유에 대한 자세한 내용은 Live Share가 파일을 **[여기](../reference/linux.md#linux-browser-integration)** 에 저장하는 경우를 참조할 수 있습니다. 브라우저 통합 작업을 가져올 수 없는 경우에도 여전히 **[수동으로 공동 작업 세션에 참가](../use/vscode.md#join-manually)** 할 수 있습니다.

## <a name="sign-in"></a>로그인

공동 작업을 수행하려면 모든 사람이 사용자의 신원을 알도록 Visual Studio Live Share에 로그인해야 합니다. 이 작업은 단순한 보안 조치이며, 사용자를 마케팅 또는 기타 연구 작업에 참여하게 **하지** 않습니다. Microsoft 개인 계정(예: @outlook.com), Microsoft 지원 회사 또는 학교 계정(AAD) 또는 GitHub 계정을 사용하여 로그인할 수 있습니다. 로그인은 간단합니다.

“Live Share” 상태 표시줄 항목을 **클릭**하거나 **Ctrl+Shift+P/Cmd+Shift+P** 키를 눌러 “Live Share: 브라우저로 로그인” 명령을 선택합니다.

![VS Code 로그인 단추](../media/vscode-sign-in-button.png)

웹 브라우저를 사용하여 로그인하라는 알림이 나타납니다. "로그인 시작"을 클릭하면 로그인 프로세스를 완료하기 위해 사용할 브라우저가 열립니다. 완료되면 브라우저를 닫습니다.

![웹 브라우저를 사용하여 로그인하라는 알림 메시지](../media/vscode-sign-in-toast.png)

> **Linux 사용자:** 이전 버전의 Live Share(v0.3.295 이하)를 사용하는 경우 사용자 코드를 입력하라는 메시지가 표시될 수 있습니다. 확장의 최신 버전으로 업데이트하거나 "문제가 있나요?"를 클릭합니다. 로그인한 후 링크를 클릭하여 코드를 확인합니다. [자세한 내용은 다음](#sign-in-using-a-user-code)을 참조하세요.

브라우저에서 로그인 프로세스를 완료한 후 Visual Studio Code에서 사용자 로그인을 인식하지 못하는 경우 [사용자 코드를 사용하여 로그인](#sign-in-using-a-user-code)을 참조하세요. 그렇지 않으면 [문제 해결](../troubleshooting.md#sign-in)을 확인하여 더 많은 팁을 확인합니다.

### <a name="sign-in-using-a-user-code"></a>사용자 코드를 사용하여 로그인

VS Code에서 완료된 로그인을 인식하지 못하는 문제가 발생한 경우 대신 "사용자 코드"를 입력할 수 있습니다.

1. **Ctrl+Shift+P / Cmd+Shift+P** 키를 눌러 "Live Share: 사용자 코드로 로그인" 명령을 실행합니다.

2. 로그인 프로세스를 완료하는 데 사용할 브라우저가 표시되어야 합니다.

    > [!NOTE]
    > 브라우저가 자동으로 표시되지 않는 경우 브라우저에서 [이 위치](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)를 열고 로그인합니다.

3. 완료되면 "문제가 있나요? 사용자 코드 지침은 여기를 클릭하세요"를 클릭하여 사용자 코드를 확인합니다.

    ![브라우저의 사용자 코드 그림](../media/vscode-user-code-browser.png)

4. 사용자 코드를 복사합니다.

5. 마지막으로, 명령을 실행할 때 표시되는 입력 필드에 사용자 코드를 붙여넣고 Enter 키를 눌러 로그인 프로세스를 완료합니다.

    ![사용자 코드 입력 필드의 그림](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>Live Share viewlet 사용

Visual Studio Live Share를 설치한 후 VS Code 작업 표시줄에 사용자 지정 탭을 추가합니다. 이 탭에서 공동 작업할 모든 Live Share 기능에 액세스할 수 있습니다. 또한 공동 작업 세션을 공유하거나 참가하는 경우 Explorer 탭에 뷰가 표시되면 사용자는 이러한 모든 기능에 액세스할 수 있습니다.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

이러한 뷰를 사용하여 공유 코드에서 참가자의 위치를 확인하고, 참가자를 클릭하고, 참가자에 집중하고, 공유 서버 및 터미널 등에 액세스할 수 있습니다.

## <a name="using-the-scoped-command-menu"></a>범위가 지정된 명령 메뉴 사용

또한 모든 Visual Studio Live Share 기능은 Ctrl+Shift+P / Cmd+Shift+P 또는 F1 키를 눌러 액세스할 수 있는 Visual Studio Code "명령 팔레트"에서 사용할 수 있습니다. "Live share"를 입력하여 명령의 전체 목록을 확인할 수 있습니다.

이 목록은 길어질 수 있으므로 상태 표시줄에서 사용 가능한 범위가 지정된 명령 메뉴 기능을 활용하는 것이 간단합니다. 상태 표시줄의 로그인/세션 상태 아이콘을 클릭하면 사용할 수 있는 컨텍스트화된 명령 목록이 즉시 표시됩니다.

![VS Code 세션 상태 아이콘](../media/vscode-share-state.png)

## <a name="share-a-project"></a>프로젝트 공유

Visual Studio Live Share를 다운로드하여 설치한 뒤 이러한 단계를 따라 공동 작업 세션을 시작하고 함께 작업할 동료를 초대합니다.

1. **로그인**

    Live Share 확장을 설치하고 다시 로드하고 종속성 설치를 완료할 때까지 기다린 다음, 로그인하여 다른 협력자에게 사용자 신원을 알려줍니다. 자세한 내용은 [로그인](#sign-in)을 참조하세요.

2. **폴더 열기**

    일반 워크플로를 사용하여 게스트와 공유하려는 폴더, 프로젝트 또는 솔루션을 엽니다.

3. **[선택 사항] 숨겨진 파일 또는 제외된 파일 업데이트**

    기본적으로 Live Share는 게스트의 공유 폴더에 있는 .gitignore 파일에서 참조하는 모든 파일/폴더를 **숨깁니다**. 파일을 **숨기면** 게스트의 파일 트리에 나타나지 않습니다. 파일을 **제외하면** 정의로 이동하거나 디버깅 또는 "추적" 중에 해당 파일을 한 단계씩 코드 실행하는 등의 상황에서 Live Share가 게스트용 파일을 열 수 없도록 보다 엄격한 규칙을 적용합니다. 다른 파일을 숨기거나 제외하려는 경우, 이러한 설정으로 **.vsls.json** 파일을 프로젝트에 추가할 수 있습니다. 자세한 내용은 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility)를 참조하세요.

4. **공동 작업 세션 시작**

    이제 간단히 “Live Share” 상태 표시줄 항목을 **클릭**하거나 **Ctrl+Shift+P/Cmd+Shift+P** 키를 눌러 “Live Share: 공동 작업 세션 시작(공유)”을 선택합니다.

    ![공유 단추](../media/vscode-share-button.png)

    > [!NOTE]
    > 처음 공유할 때 데스크톱 방화벽 소프트웨어에서 Live Share 에이전트가 포트를 열 수 있도록 허용하라는 요청이 있을 수 있습니다. 이 요청을 수락하는 것은 전적으로 선택 사항이지만, 공동 작업하는 사람이 사용자와 동일한 네트워크에 있을 때 보안되는 "직접 모드"로 성능을 향상시킬 수 있습니다. 자세한 내용은 [연결 모드 변경](../reference/connectivity.md#changing-the-connection-mode)을 참조하세요.

    초대 링크를 클립보드에 자동으로 복사합니다. 초대 링크가 브라우저에서 열리면 이러한 폴더의 내용을 다른 사용자와 공유하는 새 공동 작업 세션에 해당 사용자를 참가하게 할 수 있습니다.

    세션 상태를 나타내는 “Live Share” 상태 표시줄 항목 전환도 표시됩니다. 어떤 상태인지 확인하려면 아래의 [세션 상태](#session-states) 정보를 참조하세요.

    공유를 시작한 후 다시 초대 링크를 준비해야 하는 경우 세션 상태 표시줄 아이콘을 클릭하여 다시 해당 링크에 액세스하고 "다른 사용자 초대(링크 복사)"를 선택합니다.

5. **[선택 사항] 읽기 전용 모드 사용**

    공동 작업 세션을 시작하면 공유 중인 코드를 게스트가 편집하지 못하도록 세션을 읽기 전용으로 설정할 수 있습니다.

    공유한 후에는 초대 링크가 클립보드에 복사되었다는 알림을 받게 됩니다. 그런 다음, 옵션을 선택하여 세션을 읽기 전용으로 만들 수 있습니다.

    ![VS Code 읽기 전용 모드](../media/vscode-read-only-toast.png)

6. **다른 사용자에게 링크 보내기**

    초대할 사람에게 이메일, Slack, Skype 등을 통해 링크를 보냅니다. Live Share 세션이 게스트에게 제공할 수 있는 액세스 수준을 고려할 때 **신뢰하는 사용자와만 공유**하고 공유하는 내용의 의미를 검토해야 합니다.

    > **보안 팁:** Live Share의 일부 기능이 보안에 미치는 영향을 알고 싶나요? [보안](../reference/security.md) 문서를 확인합니다.

    초대한 게스트가 질문이 있는 경우 "[빠른 시작: 첫 번째 세션에 참가](../quickstart/join.md)" 문서는 게스트로 시작하고 실행하는 방법에 대한 몇 가지 추가 정보를 제공합니다.

7. **[선택 사항] 게스트 승인**

    기본적으로 게스트는 자동으로 공동 작업 세션에 참가하게 되고 공동 작업을 수행할 준비가 되면 알림을 받게 됩니다. 이 알림은 세션에서 사용자를 제거하는 옵션을 제공하는 반면, 대신 참가하는 모든 사용자에 대해 명시적 "승인"을 요구하도록 선택할 수 있습니다.

    이 기능을 사용하려면 단지 다음을 settings.json에 추가합니다.

         "liveshare.guestApprovalRequired": true

    이 설정을 켜면 게스트가 참가할 수 있기 전에 승인하라는 메시지가 표시됩니다.

    ![Visual Studio Code 참가 승인 요청](../media/vscode-join-approval.png)

    초대 보안 고려 사항에 대한 자세한 내용은 [초대 및 참가 액세스](../reference/security.md#invitations-and-join-access)를 참조하세요.

정말 간단하죠!!

### <a name="stop-the-collaboration-session"></a>공동 작업 세션 중단

호스트로서 완전히 공유를 중지하고 Explorer 또는 Live Share 사용자 지정 탭에서 Live Share 뷰를 열고 "공동 작업 세션 중지" 아이콘을 선택하여 언제든 공동 작업 세션을 종료할 수 있습니다.

![공동 작업 세션 중지](../media/vscode-end-collaboration-viewlet.png)

모든 게스트에게 세션이 종료되었다는 알림이 표시됩니다.  세션이 종료되면 게스트는 더 이상 콘텐츠에 액세스할 수 없게 되고 모든 임시 파일이 자동으로 정리됩니다.

공유에 문제가 있나요? [문제 해결](../troubleshooting.md#share-and-join)을 확인합니다.

## <a name="join-a-collaboration-session"></a>공동 작업 세션 참가

Visual Studio Live Share를 다운로드하여 설치한 경우 게스트는 호스팅되는 공동 작업 세션에 참가하려면 몇 가지 단계를 수행해야 합니다. 참가 방법은 [브라우저를 통해](#join-via-the-browser) 및 [수동으로](#join-manually)의 두 가지가 있습니다.

> **보안 팁:** 공동 작업 세션에 참가하는 게스트는 호스트가 특정 파일이나 기능에 대한 액세스를 제한할 수 있다는 것을 이해해야 합니다. Live Share의 일부 기능 및 설정이 보안에 미치는 영향을 알고 싶나요? [보안](../reference/security.md) 문서를 확인합니다.

### <a name="join-via-the-browser"></a>브라우저를 통해 참가

공동 작업 세션에 참가하는 가장 쉬운 방법은 웹 브라우저에서 초대 링크를 열면 됩니다. 이 흐름을 추적하는 경우 예상할 수 있는 내용은 다음과 같습니다.

1. **로그인**

    Live Share 확장을 설치하고 다시 로드하고 종속성 설치를 완료할 때까지 기다린 다음, 로그인하여 다른 협력자에게 사용자 신원을 알려줍니다. 자세한 내용은 [로그인](#sign-in)을 참조하세요.

2. **브라우저에서 초대 링크 클릭/초대 열기**

    이제 브라우저에서 초대 링크를 열거나 다시 열면 됩니다.

    > **참고**: Live Share 확장을 아직 설치하지 않은 경우 확장 마켓플레이스에 대한 링크가 표시됩니다. 확장을 설치하고, 도구를 다시 시작하고, 다시 시도합니다.

    브라우저에서 Live Share 활성화 도구를 시작하려고 한다는 알림을 받게 됩니다. 선택한 도구를 실행하게 되면 시작한 후에 공동 작업 세션에 연결됩니다.

    ![참가 페이지](../media/join-page.png)

    호스트가 오프라인 상태인 경우, 대신 이 시점에서 알림을 받게 됩니다. 그런 다음, 호스트에 연결하여 다시 공유하도록 요청할 수 있습니다.

    > [!NOTE]
    > Visual Studio Live Share 확장을 설치한 후 **도구를 한 번 이상 시작**했는지 및 초대 페이지를 열기/다시 열기 전에 설치를 완료했는지 확인합니다. 그래도 문제가 있나요? [수동으로 참가](#join-manually)를 참조하세요.

3. **공동 작업**

    정말 간단하죠. 몇 분 내에 연결되고 공동 작업을 시작할 수 있습니다.

    “세션 상태”를 전달하기 위해 “Live Share” 단추 전환이 표시됩니다. 어떤 상태인지 확인하려면 아래의 [세션 상태](#session-states) 정보를 참조하세요.

    그런 다음, 참가가 완료되면 호스트가 현재 편집 중인 파일로 자동으로 이동됩니다.

### <a name="join-manually"></a>수동 참가

사용하려는 도구가 이미 실행 중이고, 평소 사용하던 것과 다른 도구를 사용하려 하거나 여러 이유로 작업할 초대 링크를 준비하는 데 문제가 있는 경우에 유용할 수 있는 웹 브라우저를 사용하지 않고 수동으로 참가할 수도 있습니다. 프로세스는 간단합니다.

1. **로그인**

    Live Share 확장을 설치하고 다시 로드하고 종속성 설치를 완료할 때까지 기다린 다음, 로그인하여 다른 협력자에게 사용자 신원을 알려줍니다. 자세한 내용은 [로그인](#sign-in)을 참조하세요.

2. **참가 명령 사용**

    VS Code 작업 표시줄에서 Live Share 사용자 지정 탭을 열고 "공동 작업 참가 세션..." 아이콘 또는 항목을 선택합니다.

    ![viewlet 참가 아이콘](../media/vscode-join-viewlet.png)

3. **초대 링크 붙여넣기**

    전송된 초대 URL에 붙여넣고 Enter 키를 눌러 확인합니다.

4. **공동 작업!**

    정말 간단하죠. 일시적으로 공동 작업 세션에 연결되어야 합니다.

    “세션 상태”를 전달하기 위해 “Live Share” 단추 전환이 표시됩니다. 어떤 상태인지 확인하려면 아래의 [세션 상태](#session-states) 정보를 참조하세요.

    그런 다음, 참가가 완료되면 호스트가 현재 편집 중인 파일로 자동으로 이동됩니다.

### <a name="leave-the-collaboration-session"></a>공동 작업 세션 나가기

게스트로서 단순히 VS Code 창을 닫아 다른 사용자를 위한 공동 작업 세션을 종료하지 않고 해당 세션을 나갈 수 있습니다. 창을 열린 상태로 두려는 경우, Live Share Explorer 뷰 또는 Live Share 사용자 지정 탭을 열고 "공동 작업 세션 나가기" 아이콘을 선택할 수 있습니다.

![세션 나가기 아이콘](../media/vscode-leave-session-viewlet.png)

모든 임시 파일은 자동으로 정리되므로 추가 작업이 필요없습니다.

참가에 문제가 있나요? [문제 해결](../troubleshooting.md#share-and-join)을 확인합니다.

## <a name="co-editing"></a>공동 편집

게스트가 공동 작업 세션에 참가하면 모든 협력자는 즉시 실시간으로 서로의 편집 및 선택을 확인할 수 있습니다. 파일 탐색기에서 파일을 선택하고 편집을 시작해야 합니다. 호스트와 게스트 모두 사용자가 편집을 할 때 해당 편집을 확인하면서 솔루션을 쉽게 반복하고 신속하게 해결하도록 직접 기여할 수 있습니다.

> [!NOTE]
> 읽기 전용 공동 작업 세션에 참가하면 게스트가 파일을 편집할 수 없게 됩니다. 호스트는 [공유할 때 읽기 전용 모드를 사용하도록 설정](#share-a-project)할 수 있습니다. 게스트는 [세션 상태](#session-states)를 살펴보아 읽기 전용 세션에 참가 여부를 확인할 수 있습니다.

![공동 편집을 보여주는 스크린샷](../media/vscode-coedit.png)

> [!NOTE]
> 공동 편집은 특정 언어에 대해 제한적입니다. 언어별 기능 상태는 [플랫폼 지원](../reference/platform-support.md)을 참조하세요.

커서 및 편집 외에 사용자의 선택도 해당 동일 파일의 모든 참가자에게 표시됩니다. 이렇게 함으로써 문제가 있는 위치를 강조 표시하거나 아이디어를 전달하기 쉬워집니다.

![강조 표시를 보여주는 스크린샷](../media/vscode-highlight.png)

더 나아가 사용자 및 기타 참가자는 공유 프로젝트에서 모든 파일을 탐색할 수 있습니다. 공동으로 또는 독립적으로 편집할 수 있습니다. 즉, 조사, 작은 조정 및 전체 공동 편집 간 전환을 원활하게 할 수 있습니다.

결과적으로 편집 내용은 호스트의 머신에서 저장 상태로 유지되므로 편집이 완료되면 파일을 동기화, 푸시 또는 전송할 필요가 없습니다. 편집에는 "변화가 없습니다."

> **보안 팁:** 모든 참가자가 독립적으로 파일을 탐색하고 편집할 수 있는 경우 호스트는 .vsls.json 파일을 통해 게스트가 프로젝트에 액세스할 수 있는 파일을 제한하려 할 수 있습니다. 이러한 설정의 결과로 게스트는 특정 파일을 확인할 수 없다는 사실을 인식하는 것도 중요합니다. 자세한 내용은 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility)를 참조하세요.

### <a name="changing-participant-flag-behaviors"></a>참가자 플래그 동작 변경

기본적으로 Visual Studio Live Share는 마우스로 가리킬 때 또는 참가자의 커서를 편집하거나 강조 표시하거나 이동할 때 해당 커서 옆에 있는 "플래그"를 자동으로 표시합니다. 일부 경우에 이 동작을 변경하려 할 수 있습니다.

단순히 **settings.json 파일을 편집하고**(파일 > 기본 설정 > 설정), 다음 줄 중 하나를 추가한 다음, VS Code를 다시 시작합니다.

| 설정 | 동작 |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | 커서를 마우스로 가리킬 때만 플래그가 표시됩니다. |
| ``"liveshare.nameTagVisibility":"Activity"`` | 이 값이 기본값입니다. 플래그는 마우스로 가리킬 때 또는 참가자가 커서를 편집하거나 강조 표시하거나 이동할 때 표시됩니다. |
| ``"liveshare.nameTagVisibility":"Always"`` | 플래그가 항상 표시됩니다. |

## <a name="following"></a>팔로우

경우에 따라 여러 파일 또는 코드의 위치에 걸쳐 있는 문제 또는 디자인을 설명해야 합니다. 이러한 상황에서는 동료가 프로젝트 전체를 이동하는 대로 동료를 일시적으로 팔로우하는 것이 유용할 수 있습니다. 따라서 공동 작업 세션에 참가하면 자동으로 호스트를 "팔로우"하게 됩니다. 누군가를 따를 경우 편집기는 현재 열려 있는 파일 및 스크롤 위치와 동기화 상태로 유지됩니다.

> [!NOTE]
> 기본적으로 Live Share는 공유 폴더의 외부에 있는 열린 파일도 공유합니다. 이 기능을 사용하지 않도록 설정하려는 경우 settings.json에서 `liveshare.shareExternalFiles` Live Share를 `false`로 업데이트합니다.

참가자를 팔로우하려면(호스트 또는 게스트로서) Live Share Explorer 뷰 또는 사용자 지정 탭의 참가자 목록에서 해당 이름을 클릭합니다. 해당 이름 옆의 원은 참가자를 팔로우하고 있다는 것을 나타내기 위해 채워집니다.

![VS Code가 viewlet에서 따르기](../media/vscode-follow-multiple-viewlet.png)

또는 편집기 그룹의 오른쪽 위에 있는 고정 아이콘을 클릭하거나 **Ctrl+Alt+F / Cmd+Alt+F** 키를 누를 수 있습니다.

![VS Code 고정](../media/vscode-pin.png)

> [!NOTE]
> 둘 이상의 참가자가 공동 작업 세션에 있는 경우 팔로우하려는 참가자를 선택하라는 메시지가 표시됩니다.
>
>![협력자 목록을 보여주는 스크린샷](../media/vscode-list-collaborators.png)

편집기 그룹에 팔로우하기가 연결되어 있으므로 분할 뷰(또는 그리드 레이아웃!)를 사용하여 참가자를 팔로우하는 그룹 및 팔로우하지 않는 그룹을 구분할 수 있습니다. 이렇게 하면 누군가를 수동적으로 팔로우하면서 독자적으로 작업도 할 수 있습니다. 선택한 편집기 그룹을 사용하여 참가자 목록에서 참가자를 선택하여 해당 그룹이 참가자를 팔로우하게 할 수 있습니다.

![분할 뷰의 VS Code pin](../media/vscode-follow-split.png)

"팔로우 모드"에서 전환하고 직접 편집하기 쉽게 하려면 이러한 문제 중 하나가 발생할 경우 자동으로 팔로우하기를 중지해야 합니다.

1. 현재 활성 파일 편집 시작하기
1. 다른 파일 열기
1. 현재 활성 파일 닫기

또한, 고정 아이콘을 다시 클릭하거나 **Ctrl+Alt+F / Cmd+Alt+F** 키를 눌러 누군가를 팔로우하기를 명시적으로 중지할 수 있습니다.

## <a name="listing-participants"></a>참가자 나열

공동 작업 세션에 있는 참가자를 확인하는 빠른 방법은 Live Share Explorer 뷰 또는 사용자 지정 탭에서 참가자 목록을 살펴보는 것입니다. 뷰에는 세션의 모든 참가자가 표시됩니다.

![사용자 상태 표시줄 아이콘을 보여주는 스크린샷](../media/vscode-explorer-view.png)

이 목록의 모든 참가자를 클릭하면 활성 편집기 그룹의 참가자를 팔로우하게 됩니다.

또한, **Ctrl+Shift+P / Cmd+Shift+P** 키를 누르고 "Live Share: 참가자 나열" 명령을 선택하거나 세션의 참가자 수를 보여주는 상태 표시줄 항목을 **클릭**합니다.

![사용자 상태 표시줄 아이콘을 보여주는 스크린샷](../media/vscode-user-status.png)

그런 다음, 세션의 모든 참가자 목록이 나타납니다. 고정 아이콘을 클릭하는 것과 달리, 다른 참가자의 위치를 신속하게 확인할 수 있도록 세션에 사용자와 함께 다른 참가자 한 명만 있는 경우에도 이 목록은 표시됩니다. 편의 상, 고정 아이콘과 같이 목록에서 참가자 중 한 명을 선택하여 팔로우할 수 있습니다. 대신 종료하려는 경우 Esc 키를 누릅니다.

## <a name="focusing"></a>집중

경우에 따라 사용자는 수행하려는 것을 공동 작업 세션의 모든 참가자가 와서 살펴보기를 원할 수 있습니다. Live Share를 사용하면 쉽게 주의를 끄는 알림을 통해 모든 참가자가 사용자에게 주의를 “집중”하도록 요청할 수 있습니다.

VS Code 작업 표시줄 또는 Live Share Explorer 뷰에서 Live Share 사용자 지정 탭을 열고 "참가자 집중" 아이콘을 선택합니다.

![viewlet 아이콘 집중](../media/vscode-focus-viewlet.png)

명령을 실행하면 공동 작업 세션의 모든 참가자에게 주의를 집중하도록 요청하는 알림이 전달됩니다.

![알림 메시지 집중](../media/vscode-focus-toast.png)

그런 다음, 참가자가 사용자에게 집중할 준비가 된 경우 알림에서 "팔로우"를 클릭할 수 있습니다.

## <a name="co-debugging"></a>공동 디버깅

Visual Studio Live Share의 공동 작업 디버깅 기능은 문제를 디버깅하는 강력하고 고유한 방법입니다. 이 기능은 문제를 해결하기 위해 공동 작업 환경을 사용하도록 설정하는 것 외에 호스트 머신에 공유 디버깅 세션을 제공하여 사용자 및 세션의 다른 참가자가 환경에 특정적일 수 있는 문제를 조사하는 기능도 지원합니다.

> **보안 팁:** 모든 참가자가 독립적으로 파일을 탐색하고 편집할 수 있는 경우 호스트는 .vsls.json 파일을 통해 게스트가 프로젝트에 액세스할 수 있는 파일을 제한하려 할 수 있습니다. 또한 콘솔/REPL 액세스란 사용자가 신뢰하는 참가자와만 공동으로 디버깅하도록 참가자가 사용자 머신에서 명령을 실행할 수 있다는 의미임을 알아야 합니다. 이러한 설정의 결과로 특정 제한된 파일을 한 단계씩 코드를 실행하므로 게스트가 디버거를 따를 수 없다는 사실을 인식하는 것도 중요합니다. 자세한 내용은 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility)를 참조하세요.

이 기능을 사용하는 방법은 간단합니다.

1. 호스트와 모든 게스트 모두 적절한 디버깅 확장을 설치하게 해야 합니다. (이는 기술적으로 항상 필요한 것은 아니지만 일반적으로는 좋은 생각입니다.)

2. 아직 프로젝트에 대해 설정되지 않은 경우 호스트는 [launch.json을 구성](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations)하여 정상적으로 VS Code에서 애플리케이션을 디버그해야 합니다. 특수 설정이 필요없습니다.

3. 다음으로, 호스트는 정상적으로 디버그 탭의 단추를 사용하여 디버깅을 시작할 수 있습니다.

    ![VS Code 디버그 단추](../media/vscode-debug-button.png)

    > [!TIP]
    > VS Code에서 Visual Studio 디버깅 세션에 참가할 수 있으며, 그 반대도 가능합니다. 자세한 내용은 공동 디버깅에서 [Visual Studio 지침](vs.md#co-debugging)을 확인하세요.

디버거가 호스트 쪽에 연결되면 모든 게스트도 자동으로 연결됩니다. 호스트 머신에서 하나의 디버깅 "세션"이 실행되는 동안 모든 참가자는 해당 세션에 연결되고 각자 고유의 뷰를 보유하게 됩니다.

![VS Code 디버거 연결](../media/vscode-debugger.png)

컨트롤에 대해 협상하지 않고도 협력자 간에 원활하게 전환하게 하는 디버깅 프로세스를 누구나 단계별로 실행할 수 있습니다.

> [!NOTE]
> 언어별 또는 플랫폼별 디버깅 기능 상태는 [플랫폼 지원](../reference/platform-support.md)을 참조하세요.

각 협력자는 다른 변수를 조사하고, 호출 스택에 있는 다른 파일로 이동하고, 변수를 검사하고, 중단점을 추가하거나 제거할 수도 있습니다. 공동 편집 기능은 각 참가자가 다른 참가자의 위치를 추적할 수 있으므로 동시에 문제의 다른 측면 조사 및 공동 디버깅 작업 간에 원활하게 전환할 수 있는 고유 기능을 제공합니다.

> [!NOTE]
> 읽기 전용 공동 작업 세션에 있는 동안에 게스트는 디버깅 프로세스를 단계별로 실행할 수 없습니다. 그러나 게스트는 여전히 중단점을 추가 또는 제거하고, 변수를 검사할 수 있습니다.

![동시 디버깅의 애니메이션](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>VS Code가 디버깅 세션에 참가할 때 변경

기본적으로 디버깅 세션을 호스트에서 공유하는 경우 게스트는 자동으로 디버깅 세션에 연결됩니다. 그러나 경우에 따라 이 동작은 중단될 수 있습니다. 다행히 다음과 같이 변경할 수 있습니다.

단순히 **settings.json 파일을 편집하고**(파일 > 기본 설정 > 설정), 다음 줄 중 하나를 추가한 다음, VS Code를 다시 시작합니다.

| 설정 | 동작 |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | 기본값입니다. 게스트는 호스트가 시작하는 공유 디버깅 세션에 자동으로 참가하게 됩니다. |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | 호스트가 공유 디버깅 세션을 시작할 때 해당 세션에 참가 여부를 묻는 메시지가 게스트에게 표시됩니다. |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | 게스트는 모든 디버깅 세션에 수동으로 참가해야 합니다. [분리 및 재연결](#detaching-and-reattaching)을 참조하세요. |

### <a name="detaching-and-reattaching"></a>분리 및 재연결

게스트는 일시적으로 디버깅을 중지하려 할 수 있습니다. 다행히 호스트나 다른 게스트에 영향을 주지 않고 디버거를 분리하려면 게스트는 디버그 도구 모음에서 "중지" 아이콘을 클릭하면 됩니다.

![VS Code 디버거 중지 단추](../media/vscode-debug-stop.png)

더 이상 자동으로 연결되지 않도록 설정을 업데이트하거나 나중에 다시 연결하려는 경우 **Ctrl+Shift+P / Cmd+Shift+P** 키를 누르거나 세션 상태 표시줄 항목을 **클릭**하고 "공유 디버깅 세션에 연결"을 선택하면 됩니다.

![VS Code의 디버거 연결](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>브라우저에서 실행 중인 애플리케이션 공유

Visual Studio Code에는 ASP.NET과 같은 프로젝트 형식에 대한 Visual Studio 같이 유명한 "웹 애플리케이션 포트" 개념이 없습니다. 그러나 Visual Studio 호스트에서 공동 작업 세션에 참가하는 경우 디버깅이 시작한 다음, 호스트의 실행 중인 애플리케이션에 자동으로 연결되는 기본 브라우저가 자동으로 표시될 수 있습니다. 자세한 내용은 [Visual Studio 기능](vs.md#automatic-web-app-sharing)을 참조하세요.

호스트는 "로컬 서버 공유" 기능을 사용하여 RESTful 서비스와 같은 애플리케이션 또는 기타 엔드포인트를 수동으로 공유함으로써 비슷한 결과를 얻을 수 있습니다. Visual Studio 및 VS Code 게스트는 동일한 localhost 포트에서 브라우저를 열고 실행 중인 애플리케이션을 확인할 수 있습니다.  자세한 내용은 [서버 공유](#share-a-server)를 참조하세요.

## <a name="share-a-server"></a>서버 공유

때때로, 공동 작업 세션 호스트는 웹 애플리케이션 또는 로컬로 실행되는 기타 서버 또는 서비스를 게스트와 공유하려 할 수 있습니다. 공유 범위는 기타 RESTful 엔드포인트에서 데이터베이스 및 기타 서버까지입니다. Visual Studio Live Share를 사용하면 로컬 포트 번호를 지정하고 필요에 따라 이름을 지정한 다음, 모든 게스트와 공유할 수 있습니다.

그런 다음, 게스트는 정확히 동일한 포트의 자신의 로컬 머신에서 해당 포트에서 공유된 서버에 액세스할 수 있습니다. 예를 들어 **포트 3000에서 실행 중인** 웹 서버를 공유한 경우 게스트는 http://localhost:3000에 있는 **자신의 머신**에서 실행 중인 동일한 웹 서버에 액세스할 수 있습니다! 이 작업은 호스트와 게스트 사이의 보안 SSH 또는 SSL 터널을 통해 완수되고 서비스를 통해 인증되므로 공동 작업 세션에 있는 호스트 및 게스트만 액세스할 수 있어야 합니다.

> **보안 팁:** 호스트는 게스트와 공유하는 포트에 매우 민감하며, 시스템 포트를 공유하기보다 애플리케이션 포트에 집중합니다. 게스트의 경우 공유 포트는 서버/서비스를 자신의 머신에서 실행하는 것처럼 정확하게 작동합니다. 이 공유 포트는 매우 유용하지만 잘못된 포트를 공유하는 경우 위험할 수도 있습니다.

보안상 이유로 지정한 포트에서 실행되는 서버만 다른 게스트에게 제공됩니다. 다행스럽게도 공동 작업 세션 **호스트**로 하나의 포트는 쉽게 추가할 수 있습니다. 방법은 다음과 같습니다.

1. VS Code 작업 표시줄 또는 Live Share Explorer 뷰에서 Live Share 사용자 지정 탭을 열고 "공유 서버..." 항목을 선택하거나 아이콘을 클릭합니다.

    ![VS Code의 로컬 서버 공유](../media/vscode-share-local-server-viewlet.png)<br />

1. 서버가 실행 중인 포트 번호를 입력하되, 이름은 필요에 따라 입력합니다.

    ![포트 번호 프롬프트의 스크린샷](../media/vscode-enter-port.png)<br />

정말 간단하죠. 지정한 포트의 서버는 이제 동일한 포트에서 각 게스트의 localhost에 매핑됩니다(해당 포트가 이미 사용되지 않은 경우)!

포트가 이미 게스트 머신에서 사용 중인 경우 자동으로 다른 포트가 선택됩니다. 다행스럽게도 게스트는 Live Share Explorer 뷰 또는 VS Code 작업 모음의 사용자 지정 탭에서 현재 공유된 포트 목록을 확인할 수 있으며, 공유 서버 목록을 살펴볼 수 있습니다. 항목을 선택하면 브라우저에서 해당 서버가 열립니다. 또한 서버에 대한 링크를 클립보드에 복사하는 옵션을 마우스 오른쪽 단추로 클릭하여 선택할 수 있습니다.

![VS Code의 로컬 서버 액세스](../media/vscode-access-shared-server-viewlet.png)<br />

*게스트*는 보안상 이유로 호스트의 머신에서 공유되는 포트를 제어할 수 없습니다.

호스트로서 로컬 서버 공유를 **중지**하려면 Live Share Explorer 뷰 또는 사용자 지정 탭에서 공유 서버 목록의 서버 항목을 마우스로 가리킨 다음, "서버 공유 해제" 아이콘을 클릭합니다.

![VS Code의 서버 공유 중지](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>터미널 공유

최신 개발 환경에서는 다양한 명령줄 도구를 자주 사용합니다. 다행히도 Live Share를 사용하면 호스트가 필요에 따라 게스트와 "터미널을 공유"할 수 있습니다. 공유 터미널은 읽기 전용이거나 완전하게 공동 작업이 가능하므로 호스트와 게스트는 모두 명령을 실행하고 그 결과를 볼 수 있습니다. 호스트는 게스트에게 터미널 출력을 보여줄 수 있거나 게스트가 실습하고 테스트를 실행하고 호스트 머신에서만 발생하는 환경 관련 문제를 심사할 수 있도록 할 수 있습니다.

그러나 터미널은 호스트가 실행하는 명령의 출력에 대해 최소한 읽기 전용 액세스를 허용하므로 기본적으로 터미널을 공유하지는 **않습니다**. 이렇게 하면 호스트는 위험 없이 로컬 터미널에서 명령을 자유롭게 실행할 수 있으며, 실제로 그럴 필요가 있을 경우에만 터미널을 공유합니다. 또한, 호스트만 공유 터미널을 시작하여 게스트가 한 터미널을 시작하거나, 호스트가 예측 또는 감시하지 못하는 작업을 수행하지 못하게 할 수 있습니다.

호스트는 VS Code 작업 표시줄 또는 Live Share Explorer 뷰에서 Live Share 사용자 지정 탭을 열고 "공유 서버..." 항목을 선택하거나 아이콘을 클릭하여 터미널을 공유할 수 있습니다.

![VS Code의 터미널 공유](../media/vscode-share-terminal-viewlet.png)<br />

이 시점에 메뉴에서 읽기 전용 또는 읽기/쓰기 터미널을 선택할 수 있습니다. 터미널이 읽기/쓰기인 경우 호스트를 포함하여 누구나 터미널에 입력할 수 있습니다. 그러면 게스트가 호스트의 마음에 들지 않는 작업을 수행하는 경우 개입하기가 쉬워집니다. 그러나 안전하려면 호스트는 **게스트가 실제로 필요하다는 것을 아는 경우 게스트에게 읽기/쓰기 액세스 권한만 부여**하고, 호스트가 실행하는 모든 명령의 출력을 게스트가 참조하기를 원하는 경우에 읽기 전용 터미널을 계속 사용해야 합니다.

> [!NOTE]
> 공동 작업 세션이 읽기 전용 모드인 경우 호스트는 읽기 전용 터미널만 공유할 수 있습니다.

![읽기 전용 또는 읽기/쓰기 선택](../media/vscode-share-terminal-ro-rw.png)<br />

시작하려는 공유 터미널의 종류를 선택하면 새 공유 터미널이 VS Code 터미널 탭 아래에 나타납니다.

![공유 터미널 실행](../media/vscode-share-terminal-up.png)<br />

여러 터미널을 공유하거나 다른 탭에 포커스가 있는 경우, 공유 터미널 목록의 항목을 선택하여 특정 터미널로 포커스를 이동할 수 있습니다.

![공유 터미널의 포커스](../media/vscode-shared-terminal-focus.png)<br />

터미널 세션을 종료하려면, Exit를 입력하고 터미널 창을 닫거나 Live Share Explorer 뷰 또는 사용자 지정 탭에서 "터미널 공유 해제" 아이콘을 클릭합니다. 그러면 모든 사용자의 연결이 끊어집니다.

## <a name="session-states"></a>세션 상태

공동 작업 세션을 시작하거나 참가하여 공유 콘텐츠에 대한 액세스 권한이 있으면 Visual Studio Live Share 상태 표시줄 항목은 활성 공동 작업 세션의 상태를 반영하도록 해당 환경을 업데이트합니다.

다음은 일반적으로 확인할 수 있는 상태입니다.

| 시스템 상태 | 상태 표시줄 | 설명 |
|-------|--------------------|-------------|
| 비활성 | ![VS Code 상태: 비활성](../media/vscode-status-share.png) | 활성 공동 작업 세션을 포함한 모든 것이 공유되지 않습니다. |
| 호스트: 공유 진행 중 | ![VS Code 상태: 공유 진행 중](../media/vscode-status-sharing.png)| 공동 작업 세션을 시작하면 콘텐츠 공유가 바로 시작됩니다. |
| 호스트: 공유 | ![VS Code 상태: 공유 활성 상태 ](../media/vscode-status-active.png)| 공동 작업 세션이 활성 상태이고 콘텐츠를 공유합니다. |
| 호스트: 읽기 전용으로 공유 중 | ![VS Code 상태: 읽기 전용으로 공유 중](../media/vscode-status-sharing-read-only.png)| 읽기 전용 공동 작업 세션을 공유합니다. |
| 게스트: 세션 참가 | ![VS Code 상태: 참가](../media/vscode-status-joining.png)| 기존 공동 작업 세션에 참가합니다. |
| 게스트: 참가함 | ![VS Code 상태: 참가함](../media/vscode-status-active.png) | 활성 공동 작업 세션 및 수신 공유 콘텐츠에 참가하고 연결합니다. |
| 게스트: 읽기 전용으로 참가함 | ![VS Code 상태: 읽기 전용으로 참가함](../media/vscode-status-joined-read-only.png) | 활성 공동 작업 세션에 읽기 전용으로 참가하고 연결합니다. |

## <a name="guest-limitations"></a>게스트 제한 사항

위에서 설명한 기능을 사용하는 동안 게스트가 일부 결함을 경험하는 경우 공동 작업 세션 호스트는 선택한 해당 도구의 전체 기능을 그대로 유지합니다. 자세한 내용은 다음을 참조하세요.

- [언어 및 플랫폼 지원](../reference/platform-support.md)
- [확장 지원](../reference/extensions.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)
- [문제 해결](../troubleshooting.md)

## <a name="next-steps"></a>다음 단계

자세한 내용은 이러한 추가 문서를 확인하세요.

- [빠른 시작: 첫 번째 프로젝트 공유](../quickstart/share.md)
- [빠른 시작: 첫 번째 세션 참가](../quickstart/share.md)
- [방법: Visual Studio를 사용하여 공동 작업](vs.md)
- [Live Share 연결 요구 사항](../reference/connectivity.md)
- [Live Share의 보안 기능](../reference/security.md)
- [Linux 설치 정보](../reference/linux.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
