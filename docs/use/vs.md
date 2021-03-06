---
title: Visual Studio를 사용하여 협업 | Microsoft Docs
description: Visual Studio 및 Live Share에 대한 협업 방법 세트.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 190721006ea0d5a29c7b325c1dd26ef4293eb988
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98871002"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio"></a>방법: Visual Studio를 사용하여 공동 작업

Visual Studio에서 Live Share를 사용하여 공동 작업을 할 준비가 됐나요? 그렇다면, 잘 오셨습니다. 이 문서에서는 Visual Studio에 대한 Visual Studio Live Share 확장에서 특정 기능 중 일부를 사용하는 방법을 살펴보겠습니다.

여기에 설명된 모든 협업 활동은 한 명의 **협업 세션 호스트** 와 한 명 이상의 **게스트** 로 구성됩니다. 호스트는 협업 세션을 시작한 사람이며 여기에 참가한 모든 사람은 게스트입니다.

*요약 정보를 찾으시나요? 대신 [공유](../quickstart/share.md) 또는 [참가](../quickstart/join.md) 빠른 시작을 확인합니다.*

> [!TIP]
> *사용자 고유의 협업 세션에 가입* 할 수 있다는 것을 알고 계셨나요? 그러면 직접 Live Share를 시도해 보거나 Visual Studio 또는 VS Code의 인스턴스를 전환하고 원격으로 연결할 수 있습니다. 두 인스턴스 모두에 동일한 ID를 사용할 수도 있습니다. 확인해 보세요.

## <a name="installation"></a>설치

시작하기 전에 Windows 7, 8.1 또는 10에 **Visual Studio 2019** 또는 **Visual Studio 2017 15.6 이상** 을 설치해야 합니다. *그러나 이 버전은 로컬 실행 취소/다시 실행 지원을 사용하므로 Visual Studio 15.7 이상이 좋습니다.*

가져오기는 간단합니다.

Visual Studio 2019의 경우
1. 버전과 관계없이 [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)를 설치합니다.
2. [지원되는 워크로드](../reference/platform-support.md)를 설치합니다. (예: ASP.NET, .NET Core, C++, Python 및/또는 Node.js)
3. Visual Studio Live Share는 기본적으로 이러한 워크로드와 함께 설치됩니다.

Visual Studio 2017의 경우
1. 버전과 관계없이 [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/) 15.6 이상을 설치합니다.
2. [지원되는 워크로드](../reference/platform-support.md)를 설치합니다. (예: ASP.NET, .NET Core, C++ 및/또는 Node.js)
3. 마켓플레이스에서 Visual Studio Live Share 확장을 [다운로드](https://aka.ms/vsls-dl/vs)하여 설치합니다.

Visual Studio Live Share를 다운로드하여 사용하면 [사용 조건](https://aka.ms/vsls-license) 및 [개인정보처리방침](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)에 동의한 것입니다. 문제가 있는 경우 [문제 해결](../troubleshooting.md)을 참조하세요.

[![다운로드](../media/download.png)](https://aka.ms/vsls-dl/vs)

## <a name="sign-in"></a>로그인

공동 작업을 수행하려면 모든 사람이 사용자의 신원을 알도록 Visual Studio Live Share에 로그인해야 합니다. 이 작업은 단순한 보안 조치이며, 사용자를 마케팅 또는 기타 연구 작업에 참여하게 **하지** 않습니다. Microsoft 개인 계정(예: @outlook.com), Microsoft 지원 회사 또는 학교 계정(AAD) 또는 GitHub 계정을 사용하여 로그인할 수 있습니다. 로그인은 간단합니다.

Visual Studio는 기본적으로 [개인 설정 계정](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)을 사용하므로 이미 Visual Studio에 로그인한 경우 이 단계를 건너뛸 수 있습니다. 그렇지 않은 경우 정상적으로 로그인합니다.

![VS 로그인 단추](../media/vs-sign-in-button.png)


Visual Studio [맞춤형 계정](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)과 다른 로그인을 사용하려는 경우 **도구 &gt; 옵션 &gt; Live Share &gt; 사용자 계정** 으로 이동하여 자격 증명을 전환합니다.

![VS 도구 옵션 Live Share](../media/vs-tools-options-new.png)

**외부 계정** 을 선택하면 GitHub와 같은 Visual Studio 맞춤형 기능에서 지원하지 않는 계정을 선택할 수 있습니다. 처음으로 Live Share 기능을 사용할 때 브라우저가 자동으로 나타나므로 로그인을 완료할 수 있습니다.
>[!Tip]
>**도구 &gt; 옵션 &gt; Live Share &gt; 일반** 으로 이동하여 기본 Live Share 설정을 모두 볼 수 있다는 것을 알고 계셨나요? 필요에 맞게 협업 환경을 사용자 지정하세요! 일반 Live Share 설정에서 **고급 &gt; 기능 &gt; 참가자** 를 선택하여 새로운 Live Share 기능을 모두 사용해 볼 수 있습니다!  

문제가 발생한 경우 [문제 해결](../troubleshooting.md#sign-in)을 확인하여 더 많은 팁을 확인합니다.

## <a name="share-a-project"></a>프로젝트 공유

Visual Studio Live Share를 다운로드하여 설치한 뒤 이러한 단계를 따라 협업 세션을 시작하고 함께 작업할 동료를 초대합니다.

1. **로그인**

    로그인했다면 사용자 고유의 협업 세션을 시작할 준비가 된 것입니다.
    로그인하지 않았나요? 자세한 내용은 [로그인](#sign-in)을 확인하세요.

2. **솔루션, 프로젝트 또는 폴더 열기**

    일반 워크플로를 사용하여 게스트와 공유하려는 폴더, 프로젝트 또는 솔루션을 엽니다.

3. **[선택 사항] 숨겨진 파일 또는 제외된 파일 업데이트**

    기본적으로 Live Share는 게스트의 프로젝트에 있는 .gitignore 파일에서 참조하는 모든 파일/폴더를 **숨깁니다**. 파일을 **숨기면** 파일이 파일 트리에 표시되지 않게 하지만, 파일을 **제외하면** 디버깅과 같은 작업 중에도 파일이 전송되는 것을 중지합니다. 다른 파일을 숨기거나 제외하려는 경우, 이러한 설정으로 **.vsls.json** 파일을 프로젝트에 추가할 수 있습니다. 자세한 내용은 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility)를 참조하세요.

4. **협업 세션 시작**

    이제 오른쪽 위에 있는 “Live Share” 단추를 클릭하여 Live Share 세션을 시작합니다.     협업 세션에 대한 공유 가능한 링크가 자동으로 클립보드에 복사됩니다. 

    ![VS 공유 단추](../media/vs-share-button.png)

    협업 세션을 처음 시작하면 Live Share 도구 창이 표시됩니다. 다음에 Live Share 세션을 시작할 때 세션이 표시되도록 이 창을 고정합니다.

   ![VS Live Share 도구 창](../media/vs-live-share-tool-window.png)

    > [!NOTE]
    > 처음 공유할 때 데스크톱 방화벽 소프트웨어에서 Live Share 에이전트가 포트를 열 수 있도록 허용하라는 요청이 있을 수 있습니다. 이 요청을 수락하는 것은 전적으로 선택 사항이지만, 공동 작업하는 사람이 사용자와 동일한 네트워크에 있을 때 보안되는 "직접 모드"로 성능을 향상시킬 수 있습니다. 자세한 내용은 [연결 모드 변경](../reference/connectivity.md#changing-the-connection-mode)을 참조하세요.

5. **[선택 사항] 읽기 전용 모드 사용**

    협업 세션을 시작하면 공유 중인 코드를 게스트가 편집하지 못하도록 세션을 읽기 전용으로 설정할 수 있습니다.

    공유한 후에는 초대 링크가 클립보드에 복사되었다는 알림을 받게 됩니다. 그런 다음, 옵션을 선택하여 세션을 읽기 전용으로 만들 수 있습니다.

    ![VS 읽기 전용 모드](../media/vs-read-only-notification.png)

6. **다른 사용자에게 링크 보내기**

    초대할 사람에게 이메일, Slack, Skype 등을 통해 링크를 보냅니다. Live Share 세션이 게스트에게 제공할 수 있는 액세스 수준을 고려할 때 **신뢰하는 사용자와만 공유** 하고 공유하는 내용의 의미를 검토해야 합니다.

    > **보안 팁:** Live Share의 일부 기능이 보안에 미치는 영향을 알고 싶나요? [보안](../reference/security.md) 문서를 확인합니다.

    초대한 게스트가 질문이 있는 경우 "[빠른 시작: 첫 번째 세션에 참가](../quickstart/join.md)" 문서는 게스트로 시작하고 실행하는 방법에 대한 몇 가지 추가 정보를 제공합니다.

7. **[선택 사항] 게스트 승인**

    기본적으로 게스트는 자동으로 협업 세션에 참가하게 되고 협업을 수행할 준비가 되면 알림을 받습니다. 이 알림은 세션에서 사용자를 제거하는 옵션을 제공하는 반면, 대신 참가하는 모든 사용자에 대해 명시적 "승인"을 요구하도록 선택할 수 있습니다.

    **도구 > 옵션 > Live Share > 게스트 승인 요청** 을 True로 변경하여 기능을 사용합니다. 이 설정을 켜면 게스트가 참가할 수 있기 전에 승인하라는 메시지가 표시됩니다.

    ![Visual Studio 참가 승인 요청](../media/vs-join-approval.png)

    초대 보안 고려 사항에 대한 자세한 내용은 [초대 및 참가 액세스](../reference/security.md#invitations-and-join-access)를 참조하세요.

8. **Live Share 세션 관리**
    
    게스트가 VS Code 또는 Visual Studio에서 공유 세션에 대한 링크를 열면 Live Share 도구 창에서 참가자 아래에 표시됩니다. 이제 게스트가 현재 속해 있는 파일이 게스트 이름 옆에 표시됩니다.  
    
    ![VS Live Share 도구 창](../media/vs-live-share-tool-window-participant.png)

    Live Share 도구 창을 사용하면 모든 주요 기능에 액세스하여 세션을 한 곳에서 관리할 수 있습니다. 

    > [!TIP]
    > 세션 중에 Live Share 도구 창이 더 이상 보이지 않으세요? 언제든지 **보기 &gt; 다른 창 &gt; Live Share** 로 이동하여 찾을 수 있습니다!

### <a name="ending-the-collaboration-session"></a>협업 세션 종료

호스트는 공유/세션 상태 단추(오른쪽 위 모서리)를 클릭하고 &quot;협업 세션 종료&quot;를 선택하여 완전히 공유를 중지하고 협업 세션을 종료할 수 있습니다.

![공유 중지](../media/vs-stop-sharing.png)

모든 게스트에게 세션이 종료되었다는 알림이 표시됩니다. 세션이 종료되면 게스트는 더 이상 콘텐츠에 액세스할 수 없게 되고 모든 임시 파일이 자동으로 정리됩니다.

공유에 문제가 있나요? [문제 해결](../troubleshooting.md#share-and-join)을 확인합니다.

## <a name="join-a-collaboration-session"></a>협업 세션 참가

Visual Studio Live Share를 다운로드하여 설치한 경우 게스트는 호스팅되는 협업 세션에 참가하려면 몇 가지 단계를 수행해야 합니다. 참가 방법은 [브라우저를 통해](#join-via-the-browser) 및 [수동으로](#join-manually)의 두 가지가 있습니다.

> **보안 팁:** 협업 세션에 참가하는 게스트는 호스트가 특정 파일이나 기능에 대한 액세스를 제한할 수 있다는 것을 이해해야 합니다. Live Share의 일부 기능 및 설정이 보안에 미치는 영향을 알고 싶나요? [보안](../reference/security.md) 문서를 확인합니다.

### <a name="join-via-the-browser"></a>브라우저를 통해 참가

협업 세션에 참가하는 가장 쉬운 방법은 웹 브라우저에서 초대 링크를 열면 됩니다. 이 흐름을 추적하는 경우 예상할 수 있는 내용은 다음과 같습니다.

1. **로그인**

    Live Share 확장을 설치한 후 사용자의 신원을 다른 동료가 알 수 있도록 로그인하고자 합니다. 기본적으로 Visual Studio는 맞춤형 계정을 사용하므로 이 단계를 통째로 건너뛸 수 있습니다.

    자세한 내용은 [로그인](#sign-in)을 참조하세요.

2. **브라우저에서 초대 링크 클릭/초대 열기**

    이제 브라우저에서 초대 링크를 열거나 다시 열면 됩니다.

    > **참고**: Live Share 확장을 아직 설치하지 않은 경우 확장 마켓플레이스에 대한 링크가 표시됩니다. 확장을 설치하고, 도구를 다시 시작하고, 다시 시도합니다.

    브라우저에서 Live Share 활성화 도구를 시작하려고 한다는 알림을 받게 됩니다. 선택한 도구를 실행하게 되면 시작한 후에 협업 세션에 연결됩니다.

    ![참가 페이지](../media/join-page.png)

    호스트가 오프라인 상태인 경우, 대신 이 시점에서 알림을 받게 됩니다. 그런 다음, 호스트에 연결하여 다시 공유하도록 요청할 수 있습니다.

    > [!NOTE]
    > 그래도 문제가 있나요? [수동으로 참가](#join-manually)를 참조하세요.

3. **공동 작업**

    정말 간단하죠!! 몇 분 내에 연결되고 공동 작업을 시작할 수 있습니다.

    “세션 상태”를 전달하기 위해 “Live Share” 단추 전환이 표시됩니다. 어떤 상태인지 확인하려면 아래의 [세션 상태](#session-states) 정보를 참조하세요.

    그런 다음, 참가가 완료되면 호스트가 현재 편집 중인 파일로 자동으로 이동됩니다.

### <a name="join-manually"></a>수동 참가

사용하려는 도구가 이미 실행 중이고, 평소 사용하던 것과 다른 도구를 사용하려 하거나 여러 이유로 작업할 초대 링크를 준비하는 데 문제가 있는 경우에 유용할 수 있는 웹 브라우저를 사용하지 않고 수동으로 참가할 수도 있습니다. 프로세스는 간단합니다.

1. **로그인**

    Live Share 확장을 설치한 후 사용자의 신원을 다른 동료가 알 수 있도록 로그인하고자 합니다. 기본적으로 Visual Studio는 맞춤형 계정을 사용하므로 이 단계를 통째로 건너뛸 수 있습니다.

    자세한 내용은 [로그인](#sign-in)을 참조하세요.

2. **참가 명령 사용**

    **파일 > Live Share 세션 참가** 로 이동하기만 하면 됩니다.

    ![VS 참가 메뉴](../media/vs-join.png)

3. **초대 링크 붙여넣기**

    전송된 초대 URL에 붙여넣고 확인합니다.

4. **공동 작업!**

    정말 간단하죠. 일시적으로 협업 세션에 연결되어야 합니다.

    “세션 상태”를 전달하기 위해 “Live Share” 단추 전환이 표시됩니다. 어떤 상태인지 확인하려면 아래의 [세션 상태](#session-states) 정보를 참조하세요.

    그런 다음, 참가가 완료되면 호스트가 현재 편집 중인 위치로 자동으로 이동합니다.

### <a name="leave-the-collaboration-session"></a>협업 세션 나가기

게스트는 도구를 닫거나 공유 / 세션 상태 단추를 클릭하고 &quot;협업 세션 나가기&quot;를 선택하여 다른 사용자를 위해 협업 세션을 종료하지 않고 해당 세션을 나갈 수 있습니다.

![VS 참가 메뉴](../media/vs-leave-session.png)

모든 임시 파일은 자동으로 정리되므로 추가 작업이 필요없습니다.

참가에 문제가 있나요? [문제 해결](../troubleshooting.md#share-and-join)을 확인합니다.

## <a name="co-editing"></a>공동 편집

게스트가 협업 세션에 참가하면 모든 협력자는 즉시 실시간으로 서로의 편집 및 선택을 확인할 수 있습니다. 파일 탐색기에서 파일을 선택하고 편집을 시작해야 합니다. 호스트와 게스트 모두 사용자가 편집을 할 때 해당 편집을 확인하면서 솔루션을 쉽게 반복하고 신속하게 해결하도록 직접 기여할 수 있습니다.

> [!NOTE]
> 읽기 전용 협업 세션에 참가하면 게스트가 파일을 편집할 수 없게 됩니다. 호스트는 [공유할 때 읽기 전용 모드를 사용하도록 설정](#share-a-project)할 수 있습니다. 게스트는 [세션 상태](#session-states)를 살펴보아 읽기 전용 세션에 참가 여부를 확인할 수 있습니다.

![공동 편집을 보여주는 스크린샷](../media/vs-coedit.png)

> [!NOTE]
> 공동 편집은 특정 언어에 대해 제한적입니다. 언어별 기능 상태는 [플랫폼 지원](../reference/platform-support.md)을 참조하세요.

커서 및 편집 외에 사용자의 선택도 해당 동일 파일의 모든 참가자에게 표시됩니다. 이렇게 함으로써 문제가 있는 위치를 강조 표시하거나 아이디어를 전달하기 쉬워집니다.

![강조 표시를 보여주는 스크린샷](../media/vs-highlight.png)

더 나아가 사용자 및 기타 참가자는 공유 프로젝트에서 모든 파일을 탐색할 수 있습니다. 공동으로 또는 독립적으로 편집할 수 있습니다. 즉, 조사, 작은 조정 및 전체 공동 편집 간 전환을 원활하게 할 수 있습니다.

> [!NOTE]
> 기본적으로 Live Share는 공유 솔루션의 외부에 있는 열린 파일도 공유합니다. 이 기능을 사용하지 않도록 설정하려는 경우 도구 &gt; 옵션 &gt; Live Share의 외부 파일 공유를 False로 업데이트합니다.

결과적으로 편집 내용은 호스트의 머신에서 저장 상태로 유지되므로 편집이 완료되면 파일을 동기화, 푸시 또는 전송할 필요가 없습니다. 편집에는 "변화가 없습니다."

> **보안 팁:** 모든 참가자가 독립적으로 파일을 탐색하고 편집할 수 있는 경우 호스트는 .vsls.json 파일을 통해 게스트가 프로젝트에 액세스할 수 있는 파일을 제한하려 할 수 있습니다. 이러한 설정의 결과로 게스트는 특정 파일을 확인할 수 없다는 사실을 인식하는 것도 중요합니다. 자세한 내용은 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility)를 참조하세요.

### <a name="changing-participant-flag-behaviors"></a>참가자 플래그 동작 변경

기본적으로 Visual Studio Live Share는 마우스로 가리킬 때 또는 참가자의 커서를 편집하거나 강조 표시하거나 이동할 때 해당 커서 옆에 있는 "플래그"를 자동으로 표시합니다. 일부 경우에 이 동작을 변경하려 할 수 있습니다. 이를 수행하려면:

1. **도구 > 옵션 > Live Share** 로 이동
2. **플래그 표시 유형** 옵션을 다음 중 하나로 변경합니다.

| 옵션 | 동작 |
|--------|----------|
| OnHoverOnly | 커서를 마우스로 가리킬 때만 플래그가 표시됩니다. |
| OnHoverOrActivity | 기본값입니다. 플래그는 마우스로 가리킬 때 또는 참가자가 커서를 편집하거나 강조 표시하거나 이동할 때 표시됩니다. |
| 항상 | 플래그가 항상 표시됩니다.

## <a name="following"></a>팔로우

협업 세션에 있는 경우 매번 로그인 단추 옆에 있는 편집기의 오른쪽 위에서 각 참가자의 이니셜을 볼 수 있습니다. 이니셜을 마우스로 가리키면 해당 참가자의 전체 정보가 표시됩니다.

![사용자를 보여주는 스크린샷](../media/vs-person.png)

경우에 따라 여러 파일 또는 코드의 위치에 걸쳐 있는 문제 또는 디자인을 설명해야 할 수 있습니다. 이러한 상황에서는 동료가 프로젝트 전체를 이동하는 대로 동료를 일시적으로 팔로우하는 것이 유용할 수 있습니다. 이런 이유로 협업 세션에 참가하면 게스트는 자동으로 호스트를 &quot;팔로우&quot;하게 됩니다. 참가자를 팔로우할 경우 편집기는 현재 열려 있는 파일, 커서 및 스크롤 위치와 동기화 상태로 유지됩니다.

> [!NOTE]
> 기본적으로 Live Share는 공유 솔루션의 외부에 있는 열린 파일도 공유합니다. 이 기능을 사용하지 않도록 설정하려는 경우 도구 &gt; 옵션 &gt; Live Share의 외부 파일 공유를 False로 업데이트합니다.

"팔로우 모드"에서 전환하고 직접 편집하기 쉽게 하려면 이러한 문제 중 하나가 발생할 경우 팔로우하기를 중지합니다.

1. 편집, 커서 이동 또는 선택
2. 다른 파일 선택

오른쪽 위 모서리에서 팔로우 중인 사용자의 이니셜을 클릭하여 언제든 팔로우하기를 중지할 수 있습니다. 그러면 팔로우 중임을 나타내는 참가자의 이니셜 주변의 원이 사라집니다.

![팔로우 중인 Visual Studio 참가자](../media/vs-pinned.png) ![팔로우하지 않는 Visual Studio 참가자](../media/vs-pin-hover.png)

협업 세션의 모든 호스트 또는 게스트를 팔로우하려면 동일한 위치의 모든 이니셜을 클릭할 수 있습니다. 팔로우하기보다 다른 사용자의 위치로 이동하려는 경우 이니셜을 두 번 클릭하면 됩니다.

## <a name="focusing"></a>집중

경우에 따라 사용자는 수행하려는 것을 협업 세션의 모든 참가자가 와서 살펴보기를 원할 수 있습니다. Live Share를 사용하면 쉽게 주의를 끄는 알림을 통해 모든 참가자가 사용자에게 주의를 “집중”하도록 요청할 수 있습니다.

오른쪽 위 모서리에 있는 세션 상태 / 공유 단추를 클릭하고 "참가자 집중"을 선택합니다.

![메뉴 옵션 집중](../media/vs-focus.png)

협업 세션의 모든 참가자에게 주의를 집중하도록 요청하는 알림이 전달됩니다.

![알림 메시지 집중](../media/vs-focus-toast.png)

그런 다음, 참가자가 사용자에게 집중할 준비가 된 경우 알림에서 "팔로우"를 클릭할 수 있습니다.

## <a name="co-debugging"></a>공동 디버깅

Visual Studio Live Share의 공동 작업 디버깅 기능은 문제를 디버깅하는 강력하고 고유한 방법입니다. 이 기능은 문제를 해결하기 위해 공동 작업 환경을 사용하도록 설정하는 것 외에 호스트 머신에 공유 디버깅 세션을 제공하여 사용자 및 세션의 다른 참가자가 환경에 특정적일 수 있는 문제를 조사하는 기능도 사용하도록 설정합니다.

> **보안 팁:** 모든 참가자가 독립적으로 파일을 탐색하고 편집할 수 있는 경우 호스트는 .vsls.json 파일을 통해 게스트가 프로젝트에 액세스할 수 있는 파일을 제한하려 할 수 있습니다. 또한 콘솔/REPL 액세스란 사용자가 신뢰하는 참가자와만 공동으로 디버깅하도록 참가자가 사용자 머신에서 명령을 실행할 수 있다는 의미임을 알아야 합니다. 이러한 설정의 결과로 특정 제한된 파일을 한 단계씩 코드를 실행하므로 게스트가 디버거를 따를 수 없다는 사실을 인식하는 것도 중요합니다. 자세한 내용은 [파일 액세스 및 표시 유형 제어](../reference/security.md#controlling-file-access-and-visibility)를 참조하세요.

간소하게 사용합니다. 협업 세션 호스트는 Visual Studio의 일반적인 수단을 통해서만 디버깅을 시작해야 합니다.

![VS 디버그 단추](../media/vs-debug-button.png)

디버거가 호스트 쪽에 연결되면 모든 게스트도 자동으로 연결됩니다. 호스트 머신에서 하나의 디버깅 "세션"이 실행되는 동안 모든 참가자는 해당 세션에 연결되고 각자 고유의 뷰를 보유하게 됩니다.

> [!TIP]
> 공동 디버깅을 수행하는 방법 및 시기를 변경하려는 경우 **도구 > 옵션 > Live Share** 에서 설정을 통해 기본 동작을 변경할 수 있습니다.

![VS 디버거 연결](../media/vs-debugger.png)

컨트롤에 대해 협상하지 않고도 협력자 간에 원활하게 전환하게 하는 디버깅 프로세스를 누구나 단계별로 실행할 수 있습니다.

> [!NOTE]
> 언어별 또는 플랫폼별 디버깅 기능 상태는 [플랫폼 지원](../reference/platform-support.md)을 참조하세요.

각 협력자는 다른 변수를 조사하고, 호출 스택에 있는 다른 파일로 이동하고, 변수를 검사하고, 중단점을 추가하거나 제거할 수도 있습니다. 공동 편집 기능은 각 참가자가 다른 참가자의 위치를 추적할 수 있으므로 동시에 문제의 다른 측면 조사 및 공동 디버깅 작업 간에 원활하게 전환할 수 있는 고유 기능을 제공합니다.

> [!NOTE]
> 읽기 전용 협업 세션에 있는 동안에 게스트는 디버깅 프로세스를 단계별로 실행할 수 없습니다. 그러나 게스트는 여전히 중단점을 추가 또는 제거하고, 변수를 검사할 수 있습니다.

> [!TIP]
> Visual Studio에서 VS Code 디버깅 세션에 참가할 수 있으며, 그 반대도 가능합니다. 자세한 내용은 공동 디버깅에서 [Visual Studio 지침](vscode.md#co-debugging)을 확인하세요.

### <a name="automatic-web-app-sharing"></a>자동 웹 앱 공유

게다가 ASP.NET 웹앱 프로젝트의 경우 기본적으로 디버깅할 때 실행 중인 웹 애플리케이션에 연결할 웹 브라우저를 자동으로 시작하도록 호스트의 프로젝트를 구성한 경우 Live Share는 자동으로 각 게스트의 머신에서 동일 작업을 수행합니다! 이 작업은 안전하게 수행되며, 원격 웹 애플리케이션은 기본적으로 디버깅 세션 중에만 게스트가 사용할 수 있습니다.

기타 프로젝트 형식 및/또는 세션 기간에 대해 서버 액세스를 공유하는 방법에 대한 내용은 [서버 공유](#share-a-server)를 참조하세요.

> [!TIP]
> 동작을 공유하는 자동화된 브라우저를 싫어하여 이를 변경하려는 경우 **도구 > 옵션 > Live Share** 에서 설정을 업데이트할 수 있습니다.

![동시 디버깅의 애니메이션](../media/co-debug.gif)

### <a name="change-when-visual-studio-joins-debugging-sessions"></a>Visual Studio가 디버깅 세션에 참가할 때 변경

기본적으로 디버깅 세션을 호스트에서 공유하는 경우 게스트는 자동으로 디버깅 세션에 연결됩니다. 그러나 경우에 따라 이 동작은 중단될 수 있습니다. 다행히 다음과 같이 변경할 수 있습니다.

1. **도구 > 옵션 > Live Share** 로 이동
2. **디버그 세션 참가 옵션** 을 다음 중 하나로 변경합니다.

| 옵션 | 동작 |
|--------|----------|
| 자동 | 기본값입니다. 게스트는 호스트가 시작하는 공유 디버깅 세션에 자동으로 참가하게 됩니다. |
| 메시지가 표시됨 | 호스트가 공유 디버깅 세션을 시작할 때 해당 세션에 참가 여부를 묻는 메시지가 게스트에게 표시됩니다. |
| 수동 | 게스트는 모든 디버깅 세션에 수동으로 참가해야 합니다. [분리 및 재연결](#detaching-and-reattaching)을 참조하세요.|

### <a name="detaching-and-reattaching"></a>분리 및 재연결

게스트는 일시적으로 디버깅을 중지하려 할 수 있습니다. 다행히 호스트나 다른 게스트에 영향을 주지 않고 디버거를 분리하려면 게스트는 디버그 도구 모음에서 "중지" 아이콘을 클릭하면 됩니다.

더 이상 자동 연결되지 않도록 설정을 업데이트하거나 나중에 다시 연결하려는 경우 "시작 항목 선택..." 드롭다운 목록에서 원하는 디버깅 실행 세션을 선택할 수 있습니다...

![VS 디버그 단추](../media/vs-select-reattach.png)

...그런 다음, 클릭하여 연결합니다.

![VS 디버그 단추](../media/vs-reattach.png)

## <a name="share-a-server"></a>서버 공유

때때로, 협업 세션 호스트는 추가 로컬 서버 또는 서비스를 게스트와 공유하려 할 수 있습니다. 공유 범위는 기타 RESTful 엔드포인트에서 데이터베이스 또는 기타 서버까지입니다. Visual Studio Live Share를 사용하면 로컬 포트 번호를 지정하고 필요에 따라 이름을 지정한 다음, 모든 게스트와 공유할 수 있습니다.

그런 다음, 게스트는 정확히 동일한 포트의 자신의 로컬 머신에서 해당 포트에서 공유된 서버에 액세스할 수 있습니다. 예를 들어 **포트 3000에서 실행 중인** 웹 서버를 공유한 경우 게스트는 http://localhost:3000 에 있는 **자신의 머신** 에서 실행 중인 동일한 웹 서버에 액세스할 수 있습니다! 이 작업은 호스트와 게스트 사이의 보안 SSH 또는 SSL 터널을 통해 완수되고 서비스를 통해 인증되므로 협업 세션에 있는 호스트 및 게스트만 액세스할 수 있어야 합니다.

> **보안 팁:** 호스트는 게스트와 공유하는 포트에 매우 민감하며, 시스템 포트를 공유하기보다 애플리케이션 포트에 집중합니다. 게스트의 경우 공유 포트는 서버/서비스를 자신의 머신에서 실행하는 것처럼 정확하게 작동합니다. 이 공유 포트는 매우 유용하지만 잘못된 포트를 공유하는 경우 위험할 수도 있습니다.

보안상 이유로 지정한 포트에서 실행되는 서버만 다른 게스트에게 제공됩니다. 다행스럽게도 협업 세션 **호스트** 로 하나의 포트는 쉽게 추가할 수 있습니다. 방법은 다음과 같습니다.

1. 오른쪽 위 모서리에서 공유 /세션 상태 단추를 클릭하고 "공유 로컬 서버 관리"를 선택합니다.

    ![공유 로컬 서버 관리](../media/vs-share-local-servers.png)

2. 나타나는 대화 상자에서 "추가"를 클릭하고, 서버가 로컬로 실행되는 포트 번호 및 이름을 입력하고, Enter 키를 누른 다음, 확인을 클릭합니다.

    ![공유 로컬 서버 관리](../media/vs-manage-local-shared-servers.png)

정말 간단하죠. 지정한 포트의 서버는 이제 동일한 포트에서 각 게스트의 localhost에 매핑됩니다(해당 포트가 이미 사용되지 않은 경우)!

포트가 이미 게스트 머신에서 사용 중인 경우 자동으로 다른 포트가 선택됩니다. 다행히도 게스트는 오른쪽 위 모퉁이에서 공유 / 세션 상태 단추를 클릭하고 "공유 로컬 서버 보기"를 선택하여 현재 공유 목록(지정된 경우 이름별로)을 볼 수 있습니다.

![공유 로컬 서버 보기](../media/vs-view-shared-servers.png)

*게스트* 는 보안상 이유로 호스트의 머신에서 공유되는 포트를 제어할 수 없습니다.

로컬 서버 공유를 **중지** 하려면 호스트는 위에서처럼 오른쪽 위 모서리에서 공유 / 세션 상태 단추를 클릭하고, "공유 로컬 서버 관리" 및 적절한 포트를 선택하고, "제거"를 클릭해야 합니다.

## <a name="share-a-terminal"></a>터미널 공유

최신 개발 환경에서는 다양한 명령줄 도구를 자주 사용합니다. 다행히도 Live Share를 사용하면 호스트가 필요에 따라 게스트와 "터미널을 공유"할 수 있습니다. 공유 터미널은 읽기 전용이거나 완전하게 공동 작업이 가능하므로 호스트와 게스트는 모두 명령을 실행하고 그 결과를 볼 수 있습니다. 호스트는 게스트에게 터미널 출력을 보여줄 수 있거나 게스트가 실습하고 테스트를 실행하고 호스트 머신에서만 발생하는 환경 관련 문제를 심사할 수 있도록 할 수 있습니다.

그러나 터미널은 호스트가 실행하는 명령의 출력에 대해 최소한 읽기 전용 액세스를 허용하므로 기본적으로 터미널을 공유하지는 **않습니다**. 이렇게 하면 호스트는 위험 없이 로컬 터미널에서 명령을 자유롭게 실행할 수 있으며, 실제로 그럴 필요가 있을 경우에만 터미널을 공유합니다. 또한, 호스트만 공유 터미널을 시작하여 게스트가 한 터미널을 시작하거나, 호스트가 예측 또는 감시하지 못하는 작업을 수행하지 못하게 할 수 있습니다.

호스트는 오른쪽 위 모서리에서 세션 상태 / 공유 단추를 클릭하고 "터미널 공유" 메뉴 항목 중 하나를 선택하여 터미널을 공유할 수 있습니다.

![터미널 메뉴](../media/vs-terminal-menu.png)

이 시점에 메뉴에서 읽기 전용 또는 읽기/쓰기 터미널을 선택할 수 있습니다. 터미널이 읽기/쓰기인 경우 호스트를 포함하여 누구나 터미널에 입력할 수 있습니다. 그러면 게스트가 호스트의 마음에 들지 않는 작업을 수행하는 경우 개입하기가 쉬워집니다. 그러나 안전하려면 호스트는 **게스트가 실제로 필요하다는 것을 아는 경우 게스트에게 읽기/쓰기 액세스 권한만 부여** 하고, 호스트가 실행하는 모든 명령의 출력을 게스트가 참조하기를 원하는 경우에 읽기 전용 터미널을 계속 사용해야 합니다.

> [!NOTE]
> 협업 세션이 읽기 전용 모드인 경우 호스트는 읽기 전용 터미널만 공유할 수 있습니다.

시작하려는 공유 터미널의 종류를 선택하면 새 공유 터미널이 올바른 사용 권한이 있는 모든 참가자에게 나타납니다.

![터미널 설치 알림 메시지](../media/vs-terminal-install.png)

터미널 세션을 종료하려면 Exit 키를 입력하거나 터미널 창을 닫으면 모든 사용자의 연결이 끊어집니다.

## <a name="session-states"></a>세션 상태

협업 세션을 시작하거나 참가하여 공유 콘텐츠에 대한 액세스 권한이 생기면 오른쪽 위 모서리의 “Live Share” 단추를 클릭하여 활성 협업 세션의 상태를 반영하도록 해당 환경을 업데이트합니다.

다음은 일반적으로 확인할 수 있는 상태입니다.

| 시스템 상태 | 단추 | 설명 |
|-------|--------|-------------|
| 비활성 | ![VS 상태: 비활성](../media/vs-status-share.png) | 활성 협업 세션을 포함한 모든 것이 공유되지 않습니다. |
| 호스트: 공유 진행 중 | ![VS 상태: 공유 진행 중](../media/vs-status-sharing.png) | 협업 세션을 시작하면 콘텐츠 공유가 바로 시작됩니다. |
| 호스트: 공유 | ![VS 상태: 공유 활성 상태 ](../media/vs-status-active.png) | 협업 세션이 활성 상태이고 콘텐츠를 공유합니다. |
| 호스트: 읽기 전용으로 공유 중 | ![VS 상태: 읽기 전용으로 공유 중](../media/vs-status-sharing-read-only.png)| 읽기 전용 협업 세션을 공유합니다. |
| 게스트: 세션 참가 | ![VS Code 상태: 참가](../media/vs-status-joining.png) | 기존 협업 세션에 참가합니다. |
| 게스트: 참가함 | ![VS 상태: 참가함](../media/vs-status-joined.png) | 활성 협업 세션 및 수신 공유 콘텐츠에 참가하고 연결합니다. |
| 게스트: 읽기 전용으로 참가함 | ![VS 상태: 읽기 전용으로 참가함](../media/vs-status-joined-read-only.png) | 활성 협업 세션에 읽기 전용으로 참가하고 연결합니다. |

## <a name="guest-limitations"></a>게스트 제한 사항

위에서 설명한 기능을 사용하는 동안 게스트가 일부 결함을 경험하는 경우 협업 세션 호스트는 선택한 해당 도구의 전체 기능을 그대로 유지합니다. 자세한 내용은 다음을 참조하세요.

- [언어 및 플랫폼 지원](../reference/platform-support.md)
- [확장 지원](../reference/extensions.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)

## <a name="next-steps"></a>다음 단계

자세한 내용은 이러한 추가 문서를 확인하세요.

- [빠른 시작: 첫 번째 프로젝트 공유](../quickstart/share.md)
- [빠른 시작: 첫 번째 세션 참가](../quickstart/join.md)
- [방법: Visual Studio Code를 사용하여 공동 작업](vscode.md)
- [Live Share 연결 요구 사항](../reference/connectivity.md)
- [Live Share의 보안 기능](../reference/security.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
