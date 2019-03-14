---
title: Visual Studio Code-Visual Studio Live Share를 사용 하 여 공동 작업 | Microsoft Docs
description: Visual Studio Code 및 Live Share 대 한 공동 작업 방법 집합.
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 9285fef38fea9bb164892775521ed2a28fe9ef1b
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255962"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>방법: Visual Studio Code를 사용 하 여 공동 작업

VS Code에서 Live Share를 사용 하 여 공동 작업 가져올 준비가 되셨습니까?  그렇다면 올바른 위치에 완료 되었습니다! 이 문서에서는 안내 Visual Studio Code에 대 한 Visual Studio Live Share 확장에서 특정 기능 중 일부를 사용 하는 방법입니다.

여기에 설명 된 모든 공동 작업이 단일 한다는 메모 **공동 작업 세션 호스트** 와 하나 이상의 **게스트**합니다. 호스트는 공동 작업 세션을 시작한 사람이며 여기에 참가한 모든 사람은 게스트입니다.

*요약된 요약 정보를 찾으시나요? 체크 아웃 합니다 [공유할](../quickstart/share.md) 또는 [조인](../quickstart/join.md) 빠른 시작 대신 합니다.*

> [!TIP]
> *사용자 고유의 공동 작업 세션에 가입*할 수 있다는 것을 알고 계셨나요? 그러면 직접 Live Share를 시도해 보거나 Visual Studio 또는 VS Code의 인스턴스를 전환하고 원격으로 연결할 수 있습니다. 두 인스턴스 모두에 동일한 id를 사용할 수도 있습니다. 확인해 보세요.

## <a name="installation"></a>설치

시작 하기 전에 해야 Visual Studio Code 설치 Live Share의 핵심 요구 사항을 충족 하는 버전이 있다면 되도록 합니다. 해야 **Visual Studio Code (1.22.0 이상)** 실행:

- **Windows**: 7, 8.1 또는 10

- **macOS**: Sierra 10.12 이상에 해당 합니다.
    - _El Capitan 10.11는 현재 지원 되지 때문 [.NET Core 2.0 요구 사항](https://go.microsoft.com/fwlink/?linkid=872315)합니다._

- **Linux**: 64 비트 Ubuntu Desktop 16.04 +, Fedora 워크스테이션 27 이상, CentOS 7

    - 라이브 공유 수의 필요 [Linux 필수 구성 요소](#linux-install-steps) 를 설치 하 라는 메시지가 표시 될 수 있습니다.
    - _32 비트 Linux로 인해 지원 되지 않습니다 [.NET Core 2.0 요구 사항](https://go.microsoft.com/fwlink/?linkid=872314)합니다._
    - ARM도 현재 지원 되지 않습니다.
    - 참조 된 [Linux 설치 정보](../reference/linux.md) 다운스트림 및 기타 배포 사용에 대 한 문서.

그 후에 Visual Studio Live Share 확장을 다운로드하여 설치하는 것은 쉽습니다.

1. 설치 <a href="https://code.visualstudio.com/">Visual Studio Code</a>
2. [다운로드](https://aka.ms/vsls-dl/vscode) 및 marketplace에서 Visual Studio Live Share 확장을 설치 합니다.
3. Visual Studio Code를 다시 로드
4. 종속성을 다운로드 하 고 (상태 표시줄 참조)를 설치 될 때까지 기다립니다.<br/>
    ![설치를 완료합니다.](../media/vscode-finishing-install.png)
5. **Linux**: 누락 된 라이브러리를 설치 하는 방법에 대 한 알림을 표시 합니다.
    1. 알림 영역에서 "설치"를 클릭 합니다.
    2. 메시지가 표시 되 면 관리자 (sudo) 암호를 입력 합니다.
    3. 수행 하는 경우 VS Code를 다시 시작 합니다.

Visual Studio Live Share를 다운로드하여 사용하면 [사용 조건](https://aka.ms/vsls-license) 및 [개인정보처리방침](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)에 동의한 것입니다. 문제가 있는 경우 [문제 해결](../troubleshooting.md)을 참조하세요.

[![다운로드](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Linux 설치 단계

Linux는 가변적 환경 이며 데스크톱 환경 및 배포 수가 너무 많아 수 복잡해 서 작업할 수 없습니다. 지원 되는 버전을 포기 하는 경우 **Ubuntu Desktop** (16.04 이상) 또는 **Fedora 워크스테이션** (27 이상), **CentOS 7** 만 사용 하 여 **VS의 공식 배포 코드**, 프로세스를 간단 하 게 찾아야 합니다. 그러나는 비표준 구성 또는 다운스트림 배포를 사용 하는 수도 있습니다 일부 문제로에 실행 되지 않을 수 있습니다. 참조 [Linux 설치 정보](../reference/linux.md) 자세한 내용은 합니다.

#### <a name="install-linux-prerequisites"></a>Linux 필수 구성 요소 설치

일부 Linux 배포에는 Live Share 작동 해야 하는 경우 라이브러리 누락 되어 있습니다. 기본적으로 Live Share를 감지 하 여 Linux 필수 구성 요소를 설치 하려고 합니다. Live Share 누락 된 라이브러리를 설치 하는 데 필요한 권한 요청에서 발생할 수 있습니다 하는 문제를 발견 한 경우 알림 메시지를 표시 됩니다.

![알림 메시지는 Linux 필수 구성 요소를 보여 주는 누락 되었습니다.](../media/vscode-linux-prereq-missing.png)

"설치"를 클릭 하면 터미널 창을 계속 하려면 관리자 (sudo) 암호를 입력 해야 표시 됩니다. 수 모두 설정 해야 하는 Visual Studio Code를 다시 시작 작업이 완료 될 것으로 가정 합니다! 체크 아웃 하려고 **[배포 팁](../reference/linux.md#tips-by-distribution)** 다른 힌트 및 해결 방법이 있는 경우.

참조를 스크립트 배포를 지원 하지 않는 나타내는 메시지가 표시 되 면 **[커뮤니티 지원 배포에 대 한 팁](../reference/linux.md#tips-for-community-supported-distros)** 정보에 대 한 커뮤니티 우리와 공유 했습니다.

경우 있습니다 **하지 않는 명령을 실행 하는 VS Code 편을 선호**를 다시 실행 하려면이 스크립트의 최신 버전이 언제 든 지 수동으로 터미널 창에서 다음 명령을 실행 하 여 선택할 수도 있습니다.

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Linux 브라우저 통합

Visual Studio Live 공유 일반적 **추가 설치 단계가 필요 하지 않습니다** linux 브라우저 통합을 사용 하도록 합니다.

특정 배포에 종종 발생 하는 동안 있습니다 **필요한 관리자 (sudo) 암호를 알릴 수 있습니다** 설치 프로세스를 완료 합니다. 터미널 창 브라우저 시작 관리자를 설치할 위치를 알려주는 표시 됩니다. 단순히 메시지가 표시 되 면 암호를 입력 하 고 터미널 창을 닫으려면 설치가 완료 되 면 enter 키를 누릅니다.

이것이 필요한 이유에 및 라이브를 공유 하는 방법에 대 한 자세한 내용은 배치 파일을 읽을 수 있습니다  **[여기](../reference/linux.md#linux-browser-integration)** 합니다. 브라우저 통합 작업을 할 수를 가져올 수 없는 경우에  **[공동 작업 세션을 수동으로 조인](../use/vscode.md#join-manually)** 합니다.

## <a name="sign-in"></a>로그인

공동 작업을 수행 하기 위해 Visual Studio Live Share를 알게 사용자 로그인 해야 합니다. 보안을 위해 순수 하 게 이며 않습니다 **하지** 모든 마케팅 또는 기타 연구 작업 옵트인 있습니다. 개인 Microsoft 계정을 사용 하 여 로그인 할 수 있습니다 (예: @outlook.com), Microsoft 지원 회사 또는 학교 계정 (AAD) 또는 GitHub 계정. 로그인 하는 것은 쉽습니다.

**클릭** "공유" 상태 표시줄 항목 또는 키를 누릅니다 **Ctrl + Shift + P / Cmd + Shift + P** 선택한는 "라이브 공유: 브라우저를 로그인"명령입니다.

![VS 코드 로그인 단추](../media/vscode-sign-in-button.png)

웹 브라우저를 사용 하 여 로그인 하 라는 알림이 나타납니다. "시작 sign in"를 클릭 하면 브라우저를 사용 하 여 로그인 프로세스를 완료할 수 열립니다. 간단히 수행 하는 경우 브라우저를 닫습니다.

![웹 브라우저를 사용 하 여 로그인 하 라는 알림](../media/vscode-sign-in-toast.png)

> **Linux 사용자:** Live Share의 이전 버전을 사용 하는 경우 사용자 코드를 입력 하 라는 메시지가 표시 될 수 있습니다 (v0.3.295 이하로). 확장의 최신 버전으로 업데이트 하거나는 "문제가?"를 클릭 합니다. 에 연결할 로그인 한 후 코드를 참조 하세요. 참조 [아래 세부 정보에 대 한](#sign-in-using-a-user-code)합니다.

브라우저에서 로그인 프로세스를 완료 한 후 Visual Studio Code에 대 한 로그인을 가져오지 않은, 경우 참조 [사용자 코드를 사용 하 여 로그인](#sign-in-using-a-user-code)합니다. 그렇지 않으면 체크 아웃 [문제 해결](../troubleshooting.md#sign-in) 더 많은 팁입니다.

### <a name="sign-in-using-a-user-code"></a>사용자 코드를 사용 하 여 로그인

실행 하는 경우 VS Code를 사용 하 여 문제가 완료 된 로그인을 가져오지 못함, 대신 "사용자 코드"를 입력할 수 있습니다.

1. 키를 눌러 **Ctrl + Shift + P / Cmd + Shift + P** 실행 된 "Live 공유: 사용자 코드를 로그인"명령입니다.

2. 브라우저에서 로그인 프로세스를 완료 하는 데에 대 한 표시 됩니다.

    > [!NOTE]
    > 브라우저를 자동으로 표시 되지 않는 경우 열 [이 위치](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login) 브라우저에 로그인 합니다.

3. 완료 되 면 클릭 "문제가 있나요? 사용자 코드 지침 여기를 클릭"사용자 코드를 확인 합니다.

    ![브라우저에서 사용자 코드의 그림](../media/vscode-user-code-browser.png)

4. 사용자 코드를 복사 합니다.

5. 마지막으로, 로그인 프로세스를 완료 하려면 enter 키를 누릅니다 하 고 명령을 실행할 때 표시 되는 입력된 필드에 사용자 코드를 붙여넣습니다.

    ![사용자 코드에 대 한 입력된 필드의 그림](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>Live Share viewlet를 사용 하 여

Visual Studio Live Share를 설치한 후 VS Code 작업 표시줄을 사용자 지정 탭 추가 됩니다. 이 탭에서 공동 작업할 모든 Live Share 함수를 액세스할 수 있습니다. 또한을 공유 하거나 공동 작업 세션에 참가 하는 경우 뷰를 이러한 함수는 모두도 액세스 하기 위한 탐색기 탭에도 표시 됩니다.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

이러한 뷰를 사용 하 여 공유 코드에 대 한 참여자의 위치를 확인, 이러한 규칙에 따라, 참가자 집중, 공유 서버 및 터미널 액세스 참가자를 클릭할 수 있습니다.

## <a name="using-the-scoped-command-menu"></a>범위가 지정 된 명령 메뉴를 사용 하 여

또한 모든 Visual Studio Live Share 함수는 "명령 팔레트" Ctrl + Shift + P를 눌러 액세스할 수 있는 Visual Studio Code에서 사용할 수 있는 / Cmd + Shift + P 또는 f1 키입니다. "Live share"를 입력 하 여 명령의 전체 목록을 찾을 수 있습니다.

이 목록은 길어질 수 이므로 범위가 지정 된 명령 메뉴 상태 표시줄에서 사용할 수 있는 기능을 활용 하는 것이 쉽습니다 수 있습니다. 로그인에서 클릭 / 상태 표시줄에 세션 상태 아이콘에 사용 하 여 사용할 수 있는 명령 목록이 하면된 즉시 표시 됩니다.

![VS 코드 세션 상태 아이콘](../media/vscode-share-state.png)

## <a name="share-a-project"></a>프로젝트 공유

다운로드 하 여 Visual Studio Live Share를 설치, 공동 작업 세션을 시작 하 고 작업을 수행 동료를 초대 하려면 다음이 단계를 수행 합니다.

1. **서명하세요**

    Live Share 확장을 설치, 다시 로드 및 종속성 설치를 완료 될 때까지 기다리고, 후 당신이 누구 인지 알고 있어야 하는 기타 협력자 수 있도록 하려면 로그인 해야 합니다. 참조 [로그인](#sign-in) 대 한 자세한 내용은 합니다.

2. **폴더 열기**

    일반 워크플로 사용 하 여 폴더, 프로젝트 또는 게스트와 공유 하려는 솔루션을 엽니다.

3. **[선택 사항] 숨겨진 계층 또는 제외 된 파일 업데이트**

    기본적으로 Live Share **숨깁니다** 게스트에서 공유 폴더에.gitignore 파일에서 참조 하는 파일/폴더입니다. **숨기기** 파일 게스트의 파일 트리를 나타나지 않게 방지 합니다. **제외** 파일에서 디버깅 하거나 되 고 "다음" 하는 동안 파일로 실행할 경우 또는 정의로 이동 하는 같은 상황에서 게스트에 대 한 열기 Live Share를 방해 하는 보다 엄격한 규칙을 적용 합니다. 다른 파일 숨기기/제외 하려는 경우는 **. vsls.json** 이러한 설정 사용 하 여 프로젝트에 파일을 추가할 수 있습니다. 참조 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility) 세부 정보에 대 한 합니다.

4. **공동 작업 세션 시작**

    이제 단순히 **클릭** "공유" 상태 표시줄 항목 또는 적중 **Ctrl + Shift + P / Cmd + Shift + P** 선택한 "Live 공유: (공유) 공동 작업 세션을 시작 "합니다.

    ![공유 단추](../media/vscode-share-button.png)

    > [!NOTE]
    > Live Share 에이전트를 처음 공유 포트를 열 수 있도록 데스크톱 방화벽 소프트웨어에서 묻는 메시지가 될 수 있습니다. 이 완전히 선택적이 수락 하지만 보안된 "직접 모드를"를 사용 하도록 설정 된 동일한 네트워크에서 사용 하는 사용자는 성능을 향상 시키려면 합니다. 참조 [연결 모드를 변경](../reference/connectivity.md#changing-the-connection-mode) 세부 정보에 대 한 합니다.

    초대 링크를 클립보드에 자동으로 복사 됩니다. 브라우저에서 열리면이 링크 다른 사람과 이러한 폴더의 콘텐츠를 공유 하는 새 공동 작업 세션에 참가할 수 있습니다.

    세션 상태를 나타내는 "공유" 상태 표시줄 항목 전환도 표시 됩니다. 참조 [세션 상태](#session-states) 아래 모양에 대 한 정보입니다.

    Note 초대 링크를 준비 해야 하는 경우 다시 공유를 시작한 후 세션 상태 상태 표시줄 아이콘을 클릭 하 여 다시 액세스 하는 "초대 다른 (링크에 복사 하는 방법)"를 선택 합니다.

5. **[선택 사항] 읽기 전용 모드를 사용 하도록 설정**

    공동 작업 세션을 시작 하면 게스트 공유 되는 코드를 편집 하지 못하도록 방지 하기 위해 읽기 전용 세션을 설정할 수 있습니다.

    를 공유한 후 초대 링크를 클립보드에 복사 되는 알림을 받게 됩니다. 그런 다음 읽기 전용 세션을 설정 하는 옵션을 선택할 수 있습니다.

    ![VS 코드 읽기 전용 모드](../media/vscode-read-only-toast.png)

6. **링크 보내기**

    전자 메일, Slack 통해 링크를 보낼, 초대 하려는 하는 등 Skype. 참고의 수준에 액세스 하는 Live Share 세션 게스트를 제공할 수 있습니다 **신뢰 하는 사용자와 공유 해야** 공유 하는 항목의 의미를 검토 하 고 있습니다.

    > **보안 팁:** Live Share의 기능 중 일부의 보안 의미를 이해 하 시겠습니까? 체크 아웃 합니다 [보안](../reference/security.md) 문서.

    초대한 게스트에 질문을 하는 경우는 "[빠른 시작: 첫 번째 세션](../quickstart/join.md)"문서 시작 및 게스트로 실행 중에 몇 가지 자세한 정보를 제공 하는 데 사용 합니다.

7. **[선택 사항] 게스트를 승인 합니다.**

    기본적으로 게스트는 공동 작업 세션을 자동으로 조인 하 고 작업을 수행 준비가 되 면 알림을 받게 됩니다. 이 알림은 세션에서 제거 하는 옵션을 제공 하는 동안 대신 조인 모든 사용자에 대 한 명시적 "승인"을 요구 하도록 선택할 수 있습니다.

    이 기능을 사용 하는 다음 settings.json을 추가 하기만 하면 됩니다.

         "liveshare.guestApprovalRequired": true

    이 설정을 켜면를 만든 후 알림을 하 라는 메시지가 나타납니다에 참가 하려면 게스트를 승인 합니다.

    ![Visual Studio Code 조인 승인 요청](../media/vscode-join-approval.png)

    참조 [초대 및 조인 액세스](../reference/security.md#invitations-and-join-access) 초대 보안 고려 사항에 대 한 자세한 내용은 합니다.

그거에요!!

### <a name="stop-the-collaboration-session"></a>공동 작업 세션 중지

호스트로 완전히 공유를 중지 하 고 탐색기에서 또는 Live Share 사용자 지정 탭에서 Live Share 보기를 열고 "공동 작업 세션을 중지" 아이콘을 선택 하 여 언제 든 공동 작업 세션을 종료할 수 있습니다.

![공동 작업 세션 중지](../media/vscode-end-collaboration-viewlet.png)

모든 게스트는 세션이 종료 되었음을 알림을 받게 됩니다.  세션이 종료 되었음을 게스트는 더 이상 콘텐츠에 액세스할 수 후 모든 임시 파일이 자동으로 정리 됩니다.

공유 문제가 있습니까? 체크 아웃 [문제 해결](../troubleshooting.md#share-and-join)합니다.

## <a name="join-a-collaboration-session"></a>공동 작업 세션에 참가

다운로드 하 여 Visual Studio Live Share를 설치, 게스트만 몇 가지 호스팅되는 공동 작업 세션에 참가 하는 단계를 수행 해야 합니다. 두 가지 방법으로 조인할: [브라우저를 통해](#join-via-the-browser) 하 고 [수동으로](#join-manually)합니다.

> **보안 팁:** 가 공동 작업 세션에 참가 게스트로 호스트 특정 파일이 나 기능에 대 한 액세스를 제한할 수 있습니다는 이해 해야 합니다. Live Share의 기능 및 설정 중 일부의 보안 의미를 이해 하 시겠습니까? 체크 아웃 합니다 [보안](../reference/security.md) 문서.

### <a name="join-via-the-browser"></a>브라우저를 통해 조인

공동 작업 세션에 참가 하는 가장 쉬운 방법은 웹 브라우저에서 초대 링크를 열고 방법은입니다. 이 흐름을 수행할 때 얻을 수 있는 다음과 같습니다.

1. **서명하세요**

    Live Share 확장을 설치, 다시 로드 및 종속성 설치를 완료 될 때까지 기다리고, 후 당신이 누구 인지 알고 있어야 하는 기타 협력자 수 있도록 하려면 로그인 해야 합니다. 참조 [로그인](#sign-in) 대 한 자세한 내용은 합니다.

2. **브라우저에서 초대를 열고/초대 링크 클릭**

    이제 단순히 (열거나 다시) 브라우저의 초대 링크 합니다.

    > **참고**: Live Share 확장을 아직 설치 하지 않은 경우 확장 marketplace에 대 한 링크를 사용 하 여 표시 될 수 있습니다. 확장을 설치 하는 도구를 다시 시작 하 고 다시 시도 하십시오.

    사용자 브라우저가 사용 하도록 설정 하는 Live Share는 도구를 시작 하는 알림을 받게 됩니다. 선택한 도구를 시작 하는 경우, 시작 되 면 공동 작업 세션에 연결 될 수 있습니다.

    ![가입 페이지](../media/join-page.png)

    호스트가 오프 라인 상태인 경우 알려 주도록이 시점에서 대신 합니다. 그런 다음 호스트에 연결 하 고 요청을 다시 공유할 수 있습니다.

    > [!NOTE]
    > 설정한 해야 **도구를 한 번 이상 시작** 후 Visual Studio Live Share 확장을 설치 하 고 설치가 초대 페이지 열기/다시 opening 전에 완료를 허용 합니다. 그래도 문제가 있나요? 참조 [수동으로 조인](#join-manually)합니다.

3. **공동 작업**

    정말 간단하죠. 몇 분 내에 연결 됩니다 하 고 공동 작업을 시작할 수 있습니다.

    "세션 상태"를 전달 하기 위해 "공유" 단추 전환이 표시 됩니다. 참조 [세션 상태](#session-states) 아래 모양에 대 한 정보입니다.

    다음 자동으로 이동 됩니다 호스트 현재 편집 하는 조인이 완료 되 면 파일에 있습니다.

### <a name="join-manually"></a>수동 조인

수동으로 조인할 수 있습니다 사용 하려는 도구를 이미 실행 중인 경우에 유용할 수 있는 웹 브라우저를 사용 하지 않고 일반적으로 수행 하거나 가져오기 문제가 몇 가지 이유로 작업 링크를 초대 발생 하는 경우 보다 다양 한 도구를 사용 하려고 합니다. 과정은 쉽습니다.

1. **서명하세요**

    Live Share 확장을 설치, 다시 로드 및 종속성 설치를 완료 될 때까지 기다리고, 후 당신이 누구 인지 알고 있어야 하는 기타 협력자 수 있도록 하려면 로그인 해야 합니다. 참조 [로그인](#sign-in) 대 한 자세한 내용은 합니다.

2. **조인 명령을 사용 하 여**

    VS Code 작업 표시줄에서 Live Share 사용자 지정 탭을 열고 "조인 공동 작업 세션..."를 선택 합니다. 아이콘 또는 항목입니다.

    ![조인 viewlet 아이콘](../media/vscode-join-viewlet.png)

3. **초대 링크를 붙여 넣습니다.**

    전송 하 고 적중 초대 URL에 붙여넣기 확인에 입력 합니다.

4. **공동 작업.**

    정말 간단하죠. 하면 일시적으로 공동 작업 세션에 연결 되어야 합니다.

    "세션 상태"를 전달 하기 위해 "공유" 단추 전환이 표시 됩니다. 참조 [세션 상태](#session-states) 아래 모양에 대 한 정보입니다.

    다음 자동으로 이동 됩니다 호스트 현재 편집 하는 조인이 완료 되 면 파일에 있습니다.

### <a name="leave-the-collaboration-session"></a>공동 작업 세션

게스트 단순히 VS Code 창을 닫으면 다른 사용자가 끝내 지 않고 공동 작업 세션을 둘 수 있습니다. 창을 열린 상태로 유지 하려는 경우 라이브 공유 탐색기 뷰 또는 Live Share 사용자 지정 탭을 열고 하 수 "공동 작업 세션 유지" 아이콘을 선택 합니다.

![리프 세션 아이콘](../media/vscode-leave-session-viewlet.png)

모든 임시 파일은 자동으로 정리 되므로 추가 작업이 필요 하지 않습니다.

조인에 문제가 있는 경우 체크 아웃 [문제 해결](../troubleshooting.md#share-and-join)합니다.

## <a name="co-editing"></a>공동 편집

게스트의 공동 작업 세션 참여 되 면 모든 협력자 즉시 서로의 편집 및 실시간 선택 수 있게 됩니다. 파일 탐색기에서 파일을 선택 하 고 편집을 시작 해야 할 됩니다. 호스트와 게스트는 고 쉽게 반복 하 고 신속 하 게 솔루션을 아래쪽으로 해결 하므로 직접 기여할 수 같은 편집에 표시 됩니다.

> [!NOTE]
> 읽기 전용으로 공동 작업 세션에 참가 하면 게스트를 파일을 편집 해야 할 수 없습니다. 호스팅할 수 있습니다 [공유할 때 읽기 전용 모드를 사용 하도록 설정](#share-a-project)합니다. 게스트 알 수 있습니다 하는 경우 읽기 전용 세션을 확인 하 여 조인한 하 [세션 상태](#session-states)합니다.

![공동 편집을 보여 주는 스크린 샷](../media/vscode-coedit.png)

> [!NOTE]
> 특정 언어에 대 한 제한이 공동 편집 합니다. 언어별 기능 상태는 [플랫폼 지원](../reference/platform-support.md)을 참조하세요.

커서 및 편집을 선택 하는 항목 파일의 모든 참가자에 게 표시 됩니다. 이렇게 하면 쉽게 문제 수 없거나 아이디어를 전달 하는 위치를 강조 표시 합니다.

![강조 표시를 보여 주는 스크린 샷](../media/vscode-highlight.png)

더 나아가 다른 참가자 공유 프로젝트에서 모든 파일을 탐색할 수 있습니다. 함께 또는 독립적으로 즉 작은 조정 하 고 전체 공동 편집 조사를 원활 하 게 전환할 수 있습니다 하거나 편집할 수 있습니다.

결과 편집 없으므로 동기화, 푸시 또는 완료 되 면 파일을 보낼 필요가 없습니다 저장에서 호스트의 컴퓨터에서 유지 됩니다 편집 합니다. 편집 사항이 "뿐입니다."

> **보안 팁:** 모든 참가자가 지정 된 수 독립적으로 탐색 하 고 편집할 파일을 호스트로 게스트를 통해 프로젝트에 액세스할 수 없게 되는 파일을 제한 하려는. vsls.json 파일입니다. 게스트 이러한 설정으로 인해 특정 파일이 표시 되지 않을 수 있다는 것을 이기도 합니다. 참조 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility) 세부 정보에 대 한 합니다.

### <a name="changing-participant-flag-behaviors"></a>참가자 플래그 동작 변경

기본적으로 자동으로 Visual Studio Live Share 마우스로 가리키면 참가자의 커서 옆에 있는 "플래그"을 표시 하거나 강조 표시, 편집 하는 경우 또는 해당 커서를 이동 합니다. 일부 경우에이 동작을 변경 하는 것이 좋습니다.

단순히 **settings.json 편집** (파일 > 기본 설정 > 설정), 다음 줄 중 하나를 추가 하 고 다음 VS Code를 다시 시작:

| 설정 | 동작 |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | 커서를 마우스로 가리킬 때에 플래그를 표시 됩니다. |
| ``"liveshare.nameTagVisibility":"Activity"`` | 이 값이 기본값입니다. 플래그를 가리킬 때 표시 되는 또는 참가자를 편집 하는 경우를 강조 표시 하거나 커서를 이동 합니다. |
| ``"liveshare.nameTagVisibility":"Always"`` | 플래그를 항상 표시 됩니다. |

## <a name="following"></a>다음

경우에 따라 여러 파일 또는 코드의 위치에 걸쳐 있는 문제 또는 디자인을 설명해야 합니다. 이러한 상황에서는 프로젝트 전체에서 이동 하는 대로 동료를 일시적으로 수행 하는 것이 유용할 수 있습니다. 이 따라서가에 대 한 공동 작업 세션에 참가 하면 자동으로 "수행" 호스트. 누군가가 따를 경우 편집기가 현재 열려 있는 파일 및 스크롤 위치와 동기화 상태로 유지 됩니다.

> [!NOTE]
> 기본적으로 Live Share 공유에 파일 외부에 공유 폴더에도 열립니다. 이 기능을 사용 하지 않도록 설정 하려는 경우 업데이트할 `liveshare.shareExternalFiles` Live Share를 `false` settings.json에서.

다음 호스트 또는 게스트) (으로 참가자를 시작 하려면 Live 공유 탐색기 보기 또는 사용자 지정 탭에서 참가자의 목록에서 해당 이름을 클릭 합니다. 해당 이름 옆의 원을 로우 중인 나타내려면으로 채워집니다.

![VS Code에서 viewlet 수행](../media/vscode-follow-multiple-viewlet.png)

을 클릭할 수 있습니다를 누르거나 편집기 그룹의 오른쪽 위에 있는 핀 고정 아이콘 **Ctrl + Alt + F / Cmd + Alt + F**합니다.

![VS 코드 pin](../media/vscode-pin.png)

> [!NOTE]
> 공동 작업 세션의 다른 둘 이상의 사용자 인 경우 메시지가 표시 됩니다 하려는 참가자를 선택 합니다.
>
>![화면 협력자 목록을 표시 하는 스크린샷된](../media/vscode-list-collaborators.png)

다음 편집기 그룹에 연결 됩니다, 하므로 분할 뷰 (또는 모눈 레이아웃!)는 참가자를 팔 로우 하는 그룹 및 없는 그룹을 사용할 수 있습니다. 이렇게 하면 수 동적으로 독자적으 작업 항목 하는 동안 사용자가 수행할 수 있습니다. 선택한 편집기 그룹을 사용 하 여 이러한 규칙에 따라 해당 그룹이 참가자 목록에 참가자를 선택할 수 있습니다.

![분할 뷰에서 VS 코드 pin](../media/vscode-follow-split.png)

"모드"에서 외부 전환을 직접 편집을 시작을 쉽게 자동으로 이러한 중 하나가 발생할 경우 다음 중지 됩니다.

1. 현재 활성 파일 편집을 시작 하기
1. 다른 파일을 열면
1. 현재 활성 파일을 닫을

또한 명시적으로 중지할 수 있습니다 다음 사용자가 pin 아이콘을 다시 클릭 하거나 적중할 **Ctrl + Alt + F / Cmd + Alt + F**합니다.

## <a name="listing-participants"></a>참가자를 나열합니다.

공동 작업 세션에 있는 사용자를 확인 하는 빠른 방법을 라이브 공유 탐색기 보기 또는 사용자 지정 탭에 참가자 목록을 살펴보는 것입니다. 보기에는 세션의 모든 참가자가 표시 됩니다.

![스크린 샷을 보여 주는 사용자 상태 표시줄 아이콘](../media/vscode-explorer-view.png)

이 목록에 모든 참가자를 클릭할 활성 편집기 그룹에서 수행 됩니다.

적중할 수 있습니다 **Ctrl + Shift + P / Cmd + Shift + P** 선택 된 "Live 공유: 참가자 목록"명령 또는 **클릭** 세션에서 참가자의 수를 표시 하는 상태 표시줄 항목에 있습니다.

![스크린 샷을 보여 주는 사용자 상태 표시줄 아이콘](../media/vscode-user-status.png)

세션의 모든 참가자가 목록이 나타납니다. 고정 아이콘을 클릭 하는 달리이 목록에 경우에 다른 하나의 사용자와 세션에서 다른 사용자의 위치를 항상 신속 하 게 볼 수 있도록 표시 됩니다. 편의 위해서, 같은 고정 아이콘을 선택할 수 있습니다 다음 이러한 규칙에 따라 목록에서 참가자 중. 대신 종료 하려는 경우에 esc 키를 누릅니다.

## <a name="focusing"></a>집중

경우에 따라 수행 하는 것을 확인 하는 공동 작업 세션의 모든 사용자가 할 수 있습니다. 라이브 공유는 모든 사용자가 "초점" 하면 알림을 쉽게 다시 이동 하기 위해 사용 하 여 요청할 수 있습니다.

VS Code 작업 표시줄 또는 라이브 공유 탐색기 보기에서 Live Share 사용자 지정 탭을 열고 "참가자 집중" 아이콘을 선택 합니다.

![포커스 viewlet 아이콘](../media/vscode-focus-viewlet.png)

명령으로 실행 되 면 공동 작업 세션의 모든 사용자가 다음 알림을 받아볼 주의 받았습니다.

![포커스 알림](../media/vscode-focus-toast.png)

클릭할 수 있습니다 다음 방금 "팔 로우" 알림을부터 해당 포커스를 적용할 준비가 되 면.

## <a name="co-debugging"></a>공동 디버깅

Visual Studio Live Share의 공동 작업 디버깅 기능을 강력 하 고 고유한 방식으로 문제를 디버깅할 경우 문제를 해결 하는 공동 작업 환경을 사용 하도록 설정 하면, 초과 하 고 있는 문제를 조사 하는 기능이 세션의 다른 참가자 들 수 있습니다 환경 특정 호스트의 컴퓨터에서 공유 디버깅 세션을 제공 하 여.

> **보안 팁:** 모든 참가자가 지정 된 수 독립적으로 탐색 하 고 편집할 파일을 호스트로 게스트를 통해 프로젝트에 액세스할 수 없게 되는 파일을 제한 하려는. vsls.json 파일입니다. 또한 콘솔/REPL 액세스 신뢰 하는 사용자를 사용 하 여 공동 디버깅만 해야 하므로 참가자 컴퓨터에 들어 있는 명령을 실행할 수 있습니다 의미를 알아야 합니다. 게스트을 특정 제한 파일 이러한 설정을 단계별로 디버거 따르지 못할 점에 주의 해야 이기도 합니다. 참조 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility) 세부 정보에 대 한 합니다.

간단한 사용 합니다.

1. 호스트와 모든 게스트에 설치 하는 적절 한 디버깅 확장 해야 합니다. (기술적으로이 항상 필요는 없습니다, 있지만 일반적으로 것이 좋습니다.)

2. 호스트를 아직 하지 않은 경우 프로젝트를 설정 해야 합니다 [launch.json 구성](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations) 보통 때와 같이 VS Code에서 응용 프로그램을 디버그 합니다. 특수 설치가 필요 하지 않습니다.

3. 다음으로, 호스트는 정상적으로 디버그 탭에서 단추를 사용 하 여 디버깅을 시작할 수 있습니다.

    ![VS 코드 디버그 단추](../media/vscode-debug-button.png)

    > [!TIP]
    > Visual Studio 디버깅 세션 VS Code에서 그 반대로 참여할 수 있습니다. 체크 아웃 합니다 [Visual Studio 지침](vs.md#co-debugging) 공동 자세한 디버깅 합니다.

호스트 쪽에서 디버거 되 면 모든 게스트도 자동으로 연결 됩니다. 하나의 디버깅 "세션" 호스트의 컴퓨터에서 실행 중일 모든 참가자가 연결 하는 있고 고유한 보기입니다.

![VS Code 디버거 연결](../media/vscode-debugger.png)

컨트롤을 협상 하지 않고도 협력자를 원활 하 게 전환할 수 있도록 하는 디버깅 프로세스를 단계별로 실행할 수 누구나 합니다.

> [!NOTE]
> 언어별 또는 플랫폼별 디버깅 기능 상태는 [플랫폼 지원](../reference/platform-support.md)을 참조하세요.

각 협력자 다른 변수를 조사, 호출 스택에 있는 다른 파일을 이동할 변수를 검사 하 고도 추가 하거나 제거할 수 중단점. 공동 편집 기능에는 다음 각 참가자 orator 다른 위치한 고유 동시에 다른 형태의 문제를 조사 하 고 공동으로 디버깅 사이 매끄럽게 전환할 수 있도록 추적할 수 있습니다.

> [!NOTE]
> 읽기 전용으로 공동 작업 세션에서 작업 하는 동안 게스트를 디버깅 프로세스를 단계별로 실행할 되지 않습니다. 그러나 여전히 추가 및 수 있을 또는 중단점을 제거 합니다. 변수를 검사 합니다.

![동시 디버깅의 애니메이션](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>VS Code 조인 디버깅 세션을 변경할 때

기본적으로 게스트 있습니다 됩니다 수 자동으로 연결 디버깅 세션을 호스트에 의해 공유 되는 경우. 그러나 경우에 따라 이루어질이 동작은 중단입니다. 다행 스럽게도 변경할 수 있습니다 것 같습니다.

단순히 **settings.json 편집** (파일 > 기본 설정 > 설정), 다음 줄 중 하나를 추가 하 고 다음 VS Code를 다시 시작:

| 설정 | 동작 |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | 기본값입니다. 게스트로 호스트가 시작 공유 디버깅 세션을 자동으로 조인할 수 있습니다. |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | 게스트 호스트에서 시작 되 면 공유 디버깅 세션에 참가 것인지에 대 한 메시지가 표시 됩니다. |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | 게스트 모든 디버깅 세션을 수동으로 조인 해야 합니다. 참조 [분리 하 고 다시](#detaching-and-reattaching)입니다. |

### <a name="detaching-and-reattaching"></a>분리 및 다시 연결

게스트 일시적으로 디버깅을 중지 하려고 할 수 있습니다. 다행 스럽게도 호스트나 다른 게스트를 영향을 주지 않고 디버거를 분리 하려면 디버그 도구 모음에서 "중지" 아이콘을 클릭 하면 있습니다.

![VS 코드 디버거 중지 단추](../media/vscode-debug-stop.png)

하면 더 이상 자동으로 연결 하거나 나중에 다시 연결 하려는 경우 수 이렇게 하면 키를 눌러 설정을 업데이트 했으면 **Ctrl + Shift + P / Cmd + Shift + P** 또는 **클릭** 세션 상태 상태 표시줄 항목 및 "연결 하는 공유 디버깅 세션"을 선택합니다.

![VS Code 디버거](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>브라우저에서 실행 중인 응용 프로그램 공유

Visual Studio Code에 알려진 "웹 응용 프로그램 포트" Visual Studio와 같은 ASP.NET과 같은 프로젝트 형식에 대 한 개념이 없습니다. 그러나 Visual Studio 호스트에서 공동 작업 세션에 참가 하는 경우 디버깅을 호스트의 실행 중인 응용 프로그램에 연결 된 후 자동으로 시작할 때 표시 기본 브라우저가 자동으로 나타날 수 있습니다. 참조 [Visual Studio 기능](vs.md#automatic-web-app-sharing) 대 한 자세한 내용은 합니다.

호스트로 수동으로 응용 프로그램 또는 "로컬 서버 공유" 기능을 사용 하 여 RESTful 서비스와 같은 기타 끝점을 공유 하 여 비슷한 얻을 수 있습니다. Visual Studio 및 VS Code 게스트 보려면 응용 프로그램을 실행 중인 동일한 localhost 포트에서 브라우저를 열 수 있습니다.  참조 [서버를 공유](#share-a-server) 대 한 자세한 내용은 합니다.

## <a name="share-a-server"></a>서버 공유

때때로, 공동 작업 세션 호스트로, 웹 응용 프로그램 또는 게스트를 사용 하 여 서버 또는 서비스를 로컬로 실행 하는 다른 공유 하려는 경우가 있습니다. 데이터베이스 및 다른 서버에 다른 RESTful 끝점에서 지정할 수 있습니다. Visual Studio Live Share 로컬 포트 번호를 지정 하 고 필요에 따라 이름을 지정한 다음 모든 게스트와 공유할 수 있습니다.

게스트 정확히 동일한 포트에서 로컬 컴퓨터 자체에서 해당 포트에서 공유 하는 서버를 액세스할 수 없게 됩니다. 예를 들어 웹 서버를 공유 **포트 3000에서 실행 중인**, 게스트에는 동일한 실행 중인 웹 서버에 액세스할 수 해당 **자체 컴퓨터** 에서 http://localhost:3000! 호스트와 게스트 사이의 보안 SSH 또는 SSL 터널을 통해 이며 있는지 공동 작업 세션에 있는 항목만 액세스할 수 있도록 서비스를 통해 인증 합니다.

> **보안 팁:** 호스트와 게스트를 사용 하 여 공유 및 응용 프로그램 포트 (공유 하지 않고 시스템 포트)에 집중 하는 포트를 사용 하 여 매우 선택적인 해야 합니다. 게스트에 대 한 공유 포트는 서버/서비스를 자신의 컴퓨터에서 실행 된 것 처럼 정확 하 게 작동 합니다. 이 매우 유용 하지만 잘못 된 포트를 공유 하는 경우는 것은 위험할 수도 수 있습니다.

보안상의 이유로 지정 된 포트에서 실행 중인 서버만 다른 게스트 제공 됩니다. 다행 스럽게도 쉽습니다 공동 작업 세션으로 하나를 추가 하려면 **호스트**합니다. 방법은 다음과 같습니다.

1. VS Code 작업 표시줄 또는 라이브 공유 탐색기 보기에서 Live Share 사용자 지정 탭을 열고 "공유 서버..."를 선택 합니다. 입력 하거나 아이콘을 클릭 합니다.

    ![VS 코드 공유에 대 한 로컬 서버](../media/vscode-share-local-server-viewlet.png)<br />

1. 서버에서 실행 되 고 포트 번호 및 필요에 따라 이름을 입력 합니다.

    ![포트 번호 프롬프트의 스크린 샷](../media/vscode-enter-port.png)<br />

정말 간단하죠. 지정한 포트에서 서버 이제 매핑될 동일한 포트에서 각 게스트의 localhost (하지 않는 경우 해당 포트를 이미 사용 되었습니다)!

게스트 컴퓨터에서 사용 중인 포트가 이미 다른 자동으로 선택 됩니다. 다행 스럽게도 게스트 라이브 공유 탐색기 보기 또는 VS Code 작업 모음 및 공유 서버 목록 아래에서 사용자 지정 탭에서 이름을 사용 하 여 지정 된 경우 현재 공유 포트의 목록을 볼 수 있습니다. 항목을 선택 하면 브라우저에서 해당 서버를 엽니다. 또한 마우스 오른쪽 단추로 클릭 하 고 서버 클립보드에 링크를 복사 하는 옵션을 선택할 수 있습니다.

![VS 코드 액세스에 대 한 로컬 서버](../media/vscode-access-shared-server-viewlet.png)<br />

사실은 *게스트 없습니다* 보안상의 이유로 호스트의 컴퓨터에서 포트 공유를 제어 합니다.

하 **중지** 라이브 공유 탐색기 보기 또는 사용자 지정 탭에서 공유 서버 목록에서 서버 항목을 마우스로 로컬 호스트 서버 공유 및 "서버 공유 해제" 아이콘을 클릭 합니다.

![서버를 공유 하는 VS 코드 중지](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>공유 터미널

최신 개발 환경에서는 다양한 명령줄 도구를 자주 사용합니다. 다행 스럽게도 Live Share 하면, 필요에 따라 "공유 터미널" 게스트와 호스트로. 공유 터미널와 게스트 모두 명령을 실행 하 고 결과 볼 수 있도록 읽기 전용 또는 완벽 하 게 공동 작업을 수 있습니다. 터미널 출력에 대 한 게스트 가시성 또는 실습 하 고 실행할 테스트, 빌드 또는 컴퓨터에 발생 하는 심사 환경 관련 문제를 가져올 수 있도록 할 수 있습니다.

그러나는 터미널 **되지** 명령을 실행 하면 (없는 경우 직접 명령을 실행 하는 기능)의 출력에 게스트 최소한 읽기 전용 액세스 제공 되므로 기본적으로 공유 합니다. 실제로 자유롭게 위험 없이 로컬 터미널에서 명령을 실행 하 고만 시기를 공유할 수 있습니다 이러한 방식으로 작업을 수행 해야 합니다. 또한 호스트만 시작 하나에서 예기치 않거나 감시 하는 작업을 수행 하는 게스트를 방지 하기 위해 공유 터미널을 시작할 수 있습니다.

호스트로, VS Code 작업 표시줄 또는 라이브 공유 탐색기 보기에서 Live Share 사용자 지정 탭을 열고 "공유 서버..."를 선택 하 여 터미널을 공유할 수 있습니다. 항목 또는 아이콘을 클릭 합니다.

![VS Code 공유 터미널](../media/vscode-share-terminal-viewlet.png)<br />

이 시점에서 있습니다 수 선택 읽기 전용 또는 읽기/쓰기 터미널 메뉴에서. 터미널 읽기/쓰기 인 경우에 쉽게 게스트 마음에 들지 않으면 작업을 수행 하는 경우 사용자가 개입할 수 있도록 하는 호스트를 포함 하 여 터미널에서 입력할 수 모든 사용자. 그러나 안전 하 게 하려면 수행 해야 합니다 **만 귀하에 게 읽기/쓰기 액세스 게스트 실제로 필요한 것을 알고 있는 경우** 계획 하 고 읽기 전용으로 터미널만 하려는 경우 게스트를 실행 하면 명령 출력을 참조 하세요.

> [!NOTE]
> 공동 작업 세션 읽기 전용 모드인 경우 호스트에서 읽기 전용만 터미널을 공유할 수 있습니다.

![읽기 전용 또는 읽기/쓰기 선택](../media/vscode-share-terminal-ro-rw.png)<br />

시작 하려는 공유 터미널의 종류를 선택한 후 새 공유 터미널 VS Code 터미널 탭 아래에 나타납니다.

![공유 터미널 실행](../media/vscode-share-terminal-up.png)<br />

여러 터미널 공유 되나요, 아니면 다른 탭에서 집중적으로, 경우에 공유 터미널 목록의 항목을 선택 하 여 특정 터미널에 포커스를 가져올 수 있습니다.

![공유 터미널 포커스](../media/vscode-shared-terminal-focus.png)<br />

터미널 세션을 종료, exit를 입력 하기만 하면, 터미널 창을 닫고, 또는 공유 폴더 라이브 보기 또는 사용자 지정 탭 및 모든 사용자가 "공유 해제 터미널" 아이콘을 클릭 끊어집니다.

## <a name="session-states"></a>세션 상태

시작 했거나, 공동 작업 세션을 조인 하 고 콘텐츠 공유에 대 한 액세스를 후 Visual Studio Live Share 상태 표시줄 항목 모양을 active 공동 작업 세션의 상태를 반영 하도록 업데이트 합니다.

다음은 일반적으로 보면 상태입니다.

| 상태 | 상태 표시줄 | 설명 |
|-------|--------------------|-------------|
| 비활성 | ![VS 코드 상태: 비활성](../media/vscode-status-share.png) | 없음 active 공동 작업 세션 및 아무 것도 공유 됩니다. |
| 호스트: 진행 중인 공유 | ![VS 코드 상태: 진행 중인 공유](../media/vscode-status-sharing.png)| 공동 작업 세션을 시작 하 고 콘텐츠 공유 곧 시작 됩니다. |
| 호스트: 공유 | ![VS 코드 상태: 활성 공유 ](../media/vscode-status-active.png)| 공동 작업 세션에는 활성 상태 이며 콘텐츠를 공유 합니다. |
| 호스트: 읽기 전용 공유 | ![VS 코드 상태: 읽기 전용 공유](../media/vscode-status-sharing-read-only.png)| 읽기 전용으로 공동 작업 세션을 공유 합니다. |
| 게스트: 세션에 참가 | ![VS 코드 상태: 조인](../media/vscode-status-joining.png)| 기존 공동 작업 세션을 조인합니다. |
| 게스트: 조인 | ![VS 코드 상태: 가입](../media/vscode-status-active.png) | 조인 되 고 활성 공동 작업 세션 및 수신 공유 콘텐츠를 연결 합니다. |
| 게스트: 읽기 전용 연결 | ![VS 코드 상태: 읽기 전용 연결](../media/vscode-status-joined-read-only.png) | 조인 되 고 현재 읽기 전용으로 공동 작업 세션에 연결 합니다. |

## <a name="guest-limitations"></a>게스트 제한 사항

가 현재 게스트 위에서 설명한 기능을 사용 하는 동안 경험할 일부 단점을 보완 하는 동안 공동 작업 세션 호스트는 선택한 해당 도구의 전체 기능을 유지 합니다. 자세한 내용은 다음을 참조하세요.

- [언어 및 플랫폼 지원](../reference/platform-support.md)
- [확장 지원](../reference/extensions.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)
- [문제 해결](../troubleshooting.md)

## <a name="next-steps"></a>다음 단계

자세한 내용은 이러한 추가 문서를 확인 합니다.

- [빠른 시작: 첫 번째 프로젝트를 공유 합니다.](../quickstart/share.md)
- [빠른 시작: 첫 번째 세션](../quickstart/share.md)
- [방법: Visual Studio를 사용 하 여 공동 작업](vs.md)
- [Live Share 연결 요구 사항](../reference/connectivity.md)
- [Live Share의 보안 기능](../reference/security.md)
- [Linux 설치 세부 정보](../reference/linux.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
