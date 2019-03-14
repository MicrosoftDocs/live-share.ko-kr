---
title: 보안-Visual Studio Live 공유 | Microsoft Docs
description: Visual Studio Live Share의 보안 기능 정보입니다.
ms.custom: ''
ms.date: 12/17/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 0bc97691ca7733f694190e86140b930e68657ade
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255953"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Live Share의 보안 기능

Visual Studio Live Share의 공동 작업 세션은 세션에 참여 하 고 공동으로 편집, 디버그 하 게 등 임의 개수의 수는 강력 합니다. 그러나이 수준의 액세스 권한 부여를 틀림 됩니다 Live Share는 제공 된 보안 기능입니다. 이 문서에서는 몇 가지 권장 사항 및 필요에 따라 사용자 환경 보호에 대 한 옵션이 제공 됩니다.

**모든 공동 작업 도구와 마찬가지로 해야만 코드, 콘텐츠 및 응용 프로그램 사용자와 공유를 신뢰 해야 합니다.**

## <a name="connectivity"></a>연결

모든 Visual Studio Live Share의 연결은 공동 작업 세션의 개체만 해당 내용에 대 한 액세스 권한을 획득할 수 있도록 SSH 또는 SSL 암호화 하 고 중앙 집중식 서비스를 인증 합니다. 기본적으로 Live Share 직접 연결을 시도 하 고 게스트와 호스트 간의 연결을 설정할 수 없는 경우 클라우드 릴레이 대체 합니다. Live Share 클라우드 릴레이 라우팅된 모든 트래픽을 유지 하지를 않습니다 하지 "스 눕" 어떤 방식으로 트래픽을 note 합니다. 그러나를 릴레이 사용 하지 않도록 하려는 경우에 항상 직접 연결 설정을 변경할 수 있습니다.

이러한 동작 및 Live Share의 연결 요구 사항을 변경 하는 방법에 대 한 자세한 내용을 참조 하세요  **[Live 공유에 대 한 연결 요구 사항을](connectivity.md)** 합니다.

## <a name="invitations-and-join-access"></a>초대 및 조인 액세스

때마다 새 공동 작업 세션을 시작, Live Share 생성을 **새 고유 식별자** 는 초대 링크에 배치 됩니다. 링크의 식별자는 "비 추측할" 하 고 신뢰 하는 초대를 강력 하 고 보안 기초를 제공 하는 이러한 링크 _단일 공동 작업 세션 기간에만 유효_합니다.

### <a name="removing-an-unexpected-guest"></a>예기치 않은 게스트는 제거

호스트와 게스트 공동 작업 세션에 연결 될 때마다 자동으로 알림을 받습니다.

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

그러나 아직도 알림을 하면 어떤 이유로 알 수 없는 해당 하는 경우에 조인 된 게스트를 제거 하는 기능이 있습니다. (예를 들어 실수로 전사적 채팅 시스템에서 링크를 게시 하 고 임의 직원을 조인 합니다.) 간단히 표시 되는 알림 영역에서 "제거" 단추를 클릭 하 고 공동 작업 세션에서 꺼낼 수 됩니다.

**VS Code**, 그 후 참가자를 제거 하는 기능이 수도 조인 알림을 해제 하는 경우에 합니다. 탐색기 또는 VS Code 작업 표시줄에서 사용자 지정 탭에서 Live Share 보기를 열어 마우스로 또는 참여자의 이름을 마우스 오른쪽 단추로 클릭 하 수 옵션을 "제거 참가자" 아이콘을 선택 합니다.

![VS Code에서 참가자를 제거 합니다.](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>게스트 승인 필요

일반적으로 공동 작업 세션에 참가 하는 참여자 됩니다 **Live Share 로그인** Microsoft 회사 또는 학교 계정 (AAD), 개인 Microsoft 계정 또는 GitHub 계정을 사용 하 여 합니다. "알림 + 제거" 하는 동안 제공 좋은 혼합을 사용자 로그인에 대 한 기본 속도 및 해당이 게스트에 대 한 제어 하려는 **항목을 잠그는** 중요 한 작업을 수행 하는 경우 조금 더 합니다.

또한 공동 작업을 조인할에 로그인 하는 모든 게스트를 강제 적용 하는 특정 상황에서 세션 문제가 될 수 있습니다. 예로 다른 사용자가 게스트 강의/학습 시나리오 조인할 Live Share를 요청 하거나 지원 되는 계정 유형 중 하나를 갖고 있지 않은 다른 사람과 공동 작업 합니다. 이러한 이유로, Live Share는 사용자 수 **에 로그인 하지** 으로 공동 작업 세션에 참여 하려면 **읽기 전용** 게스트입니다. 호스트 해야 하는 동안 **승인** 기본적으로 참가할 수 전에 이러한 게스트를 하려는 경우 항상 대신 승인 또는 "anonymous" 해당 게스트를 허용 하지 않습니다.

#### <a name="requiring-guest-approval-for-signed-in-users"></a>필요한 게스트 승인에 대 한 사용자 로그인

원하는 방지 하기 위해 세션을 승인 했습니다. "" 하 여 공동 작업 조인에서 게스트에 로그인 하는 경우 다음 설정을 변경 합니다.

* **VS Code**, 다음 settings.json을 추가 합니다 (파일 > 기본 설정 > 설정):

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* **Visual Studio**, 도구 설정 > 옵션 > Live Share > "승인을 게스트"로 합니다.

    ![게스트 승인 강조 표시 된 설정을 사용 하 여 visual Studio 설정 창](../media/vs-setting-guestapproval.png)

이 지점에서 조인 하는 각 게스트를 승인 하 라는 나타납니다.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-approval.png" width="100%" alt="Visual Studio Code join approval request" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-approval.png" width="100%" alt="Visual Studio join approval request"/>
    </td>
</tr>
</table>

게스트 호스트의 사용이 설정에 있는 세션에 참가 하는 경우 상태 표시줄에 알림이 표시 됩니다 하거나 가입 시킬 수 Live Share를 승인 하려면 호스트에서 대기 하는 대화 상자.

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>자동 거부 하거나 허용 사용자를 로그인 하지 않은 (익명)

위에서 설명한 대로, Live Share를 허용 하도록 구성할 수 있습니다 **에서 서명 되지 않은 사용자** 으로 공동 작업 세션에 참가할 **읽기 전용** 게스트입니다.  하지만 이러한 **"익명" 게스트에 이름을 입력 해야** 단순한 이름을 조인할 경우 동일한 실제 로그인으로 보증 수준을 제공 하지 않습니다. 따라서 **기본적으로 호스트를 승인 하 라는 메시지가 표시** "require 게스트 승인"에 관계 없이 모든 익명 게스트 위에서 설명한 설정 합니다.

할 수 있습니다 **항상 거부할** (익명 게스트 사용 안 함) 또는 **항상 수락** 익명 사용자 대신 다음과 같은:

* **VS Code**설정 `liveshare.anonymousGuestApproval` settings.json에서 (파일 > 기본 설정 > 설정) 하 `accept`, `reject`, 또는 `prompt` (기본값) 적절 하 게 합니다.

* **Visual Studio**, 도구 설정 > 옵션 > Live Share > "익명 게스트 승인" Accept, Reject 또는 메시지 표시 (기본값)으로 적절 한 합니다.

 **그럼에도 불구 하 고 Live Share만 보내야를 기억 하는 사람들과 초대 링크를 신뢰 합니다.**

## <a name="controlling-file-access-and-visibility"></a>파일 액세스를 제어 및 가시성

게스트 Live Share 원격 모델 액세스할 수 있습니다 빠른 읽기/쓰기 호스트 프로젝트의 전체 내용을 동기화 할 필요 없이 공유 된 파일 및 폴더에 있습니다. 따라서 독립적으로 이동 하 전체 공유 파일 트리에서 파일을 편집 합니다. **그러나이 자유롭게 호스트를 위험을 초래할지 않습니다.** 개념적으로 개발자 진행 및 사용자 모르게 소스 코드를 수정 하거나 중요 한 소스 코드 또는 공유 파일 트리에서 어딘가에 있는 "비밀"을 참조 하도록 선택할 수 있습니다. 결과적으로 호스트에 항상 싶지 않은 공유 하는 프로젝트의 전체에 액세스할 수 있도록 게스트입니다. 다행 스럽게도 추가 원격이 모델의 장점은 "제외" 라는 기능을 유지 하면서 다른 사람과 공유 하지 않을 파일을 선택할 수 있습니다. 게스트 그걸으로 자신의 하는 경우 이러한 파일에 액세스할 수 있어야 일반적으로 세션을 디버깅 하는 등에 참가할 수 있습니다.

추가 하 여이 수행할 수 있습니다는 **. vsls.json** 폴더 또는 공유 하는 프로젝트 파일입니다. 이 json 형식이 지정 된 파일에 추가한 모든 설정을 Live Share 파일을 처리 하는 방법을 변경 합니다. 직접 제어를 제공 하는 것 외에도 이러한 파일 또한 커밋할 수 있습니다 소스 제어에 있도록 프로젝트를 복제 하는 모든 사용자가 해당 부분에 추가 작업 없이 이러한 규칙을 활용할 수 있게 됩니다.

다음은 예제입니다. vsls.json 파일:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"none",
    "excludeFiles":[
        "*.p12",
        "*.cer",
        "token",
        ".gitignore"
    ],
    "hideFiles": [
        "bin",
        "obj"
    ]
}
```

> [!NOTE]
> 공유한 모든 파일/폴더를 만들 수도 있습니다 **읽기 전용** 공동 작업 세션을 시작 하는 경우. 참조 [아래](#read-only-mode) 세부 정보에 대 한 합니다.

게스트 수행할 수 있는 이러한 속성을 변경 하는 방법을 살펴보겠습니다.

### <a name="properties"></a>속성

합니다 **excludeFiles** 속성을 사용 하면 glob 파일 패턴 (매우.gitignore 파일을 찾을 것 처럼)의 목록을 지정할 수 있습니다 게스트에 대 한 특정 파일 또는 폴더를 열 수 없도록 Live Share를 금지 하는 합니다. 이 게스트와 같은 시나리오를 포함 하 여 주의 _모든 코드 탐색 기능이 정의 등으로 같은 다음 또는 공동 작업 디버깅 하는 동안 파일을 한 단계씩 사용자 편집 위치를 이동 합니다._ 암호, 인증서 또는 암호를 포함 하는 것과 같은 모든 상황에서 공유 하지 않으려는 파일에 대 한 것입니다. 예를 들어, 보안, 제어 하므로. vsls.json 파일은 항상 제외 됨.

합니다 **hideFiles** 속성이 유사 하지만 매우 만큼 엄격 하지 않습니다. 이러한 파일은 단순히 파일 트리에서 숨겨집니다. 예를 들어, 경우를 실행 하려면 이러한 파일 중 하나에 디버깅 하는 동안 편집기에서 열립니다 계속 됩니다. 이 속성이 없는.gitignore 파일 설정 (처럼 경우 다른 소스 제어 시스템을 사용 하는 경우) 또는 이미 있는 혼잡 함과 혼란을 방지 하려면 확장 하려는 경우에 주로 유용 합니다.

합니다 **gitignore** 설정은 Live Share 공유 폴더에.gitignore 파일의 콘텐츠를 처리 해야 하는 방법을 설정 합니다. 기본적으로 모든 glob.gitignore 파일에 있는 "hideFiles" 속성에 지정 된 것 처럼 처리 됩니다. 그러나 다음 값 중 하나를 사용 하 여 다른 동작을 선택할 수 있습니다.

| 옵션    | 결과                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | .gitignore 내용을 게스트 (게스트 편집기 설정에 필터링 되지 않는 것으로 가정) 파일 트리에 표시 됩니다. |
| `hide`    | **기본값입니다.** .Gitignore 내 glob "hideFiles" 속성에 있는 것 처럼 처리 됩니다.                   |
| `exclude` | .Gitignore 내 glob "excludeFiles" 속성에 있는 것 처럼 처리 됩니다.                                 |

단점은 `exclude` 설정은입니다 같은 node_modules 폴더의 내용을 자주.gitignore에는 디버깅 중에 한 단계씩 코드 실행에 유용할 수 있습니다. 따라서 Live Share 지원 기능을 사용 하 여 규칙을 역방향 "!" excludeFiles 속성에서입니다. 이 예를 들어. vsls.json 파일 node_modules 제외 하 고 ".gitignore"의 모든 항목을 제외 하 합니다.

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

숨기기 및 제외 규칙을 계속 하려는 경우 실제로 제외 하지 않고 더 단순하게 하려면 node_modules 숨기려면, 편집할 수 있도록 단순히 파일 같이 개별적으로 처리 됩니다.

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ],
    "hideFiles":[
        "node_modules"
    ]
}
```

### <a name="vslsjson-files-in-sub-folders"></a>. 하위 폴더에 vsls.json 파일

마지막으로, 마찬가지로.gitignore. vsls.json 파일 하위 폴더에 배치할 수 있습니다. 숨기기/제외 규칙부터 시작 하 여 결정 됩니다는. vsls.json 파일 (있는 경우) 공유 루트 폴더 및 다음 연습을 통해 각 하위 폴더에 있는 최고의에서 검색할 지정된 된 파일에. vsls.json 프로세스 파일입니다. 내용을. vsls.json 파일 폴더 파일 트리를 아래쪽에 다음 보완 (또는 재정의) 더 높은 수준에서 설정 된 규칙입니다.

### <a name="disabling-external-file-sharing"></a>외부 파일 공유를 사용 하지 않도록 설정

기본적으로 Live Share를 공유할 수도 호스트 열립니다 외부 공유 폴더에 있는 모든 파일 / 솔루션입니다. 이렇게 하면 쉽게 신속 하 게 다시 공유 하지 않고도 다른 관련 파일을 엽니다.

이 기능을 사용 하지 않도록 설정 하려는 경우:

* **VS Code**, 다음 settings.json을 추가 합니다.

    ```json
    "liveshare.shareExternalFiles": false
    ```

* **Visual Studio**, 도구 집합 &gt; 옵션 &gt; Live Share &gt; False로 "외부 파일 공유"

## <a name="read-only-mode"></a>읽기 전용 모드

호스트에 따라 코드를 공유 하는 경우에 따라 편집 하려면 게스트 하지 않으려고 합니다. 게스트 코드의 일부를 수행 해야 할 수 있습니다 있고 게스트의 여러 프로젝트를 표시 하는 모든 불필요 하거나 실수로 편집 가능 하도록 하지. 라이브 공유 읽기 전용 모드에서 프로젝트를 공유 하는 기능을 제공 합니다.

호스트를 공유 하는 경우, 공동 작업 세션에 대 한 읽기 전용 모드를 설정 하는 옵션이 있습니다. 게스트에 들어오면 있습니다 서로의 커서를 계속 볼 수 있습니다 및 강조 표시와 프로젝트를 통해 이동 하지만 코드를 편집을 만들 수 없습니다.

여전히 읽기 전용 모드에 있는 동안 게스트를 사용 하 여 공동 디버깅할 수 있습니다. 게스트는 디버깅 프로세스를 단계별로 실행 되지만 여전히 추가 또는 중단점을 제거 하 변수 검사 수는 없습니다. 또한 게스트를 사용 하 여 서버 및 터미널 (읽기 전용)를 아직 공유할 수 있습니다.

읽기 전용으로 공동 작업 세션을 시작 하는 방법에 대 한 자세한 수 있습니다. [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

## <a name="co-debugging"></a>공동 디버깅

까다로운 코딩 문제 또는 버그 당면, 경우에 디버깅 하는 경우의 눈이 쌍을 추가 하지 실제로 유용할 수 있습니다. Visual Studio Live Share를 사용 하면 "공동 작업 디버깅" 또는 "배치" 하 여 디버깅 호스트 디버깅을 시작할 때마다 모든 게스트를 사용 하 여 디버깅 세션을 공유 합니다.

호스트로 완벽 한 제어를 통해 디버깅 세션을 시작 하거나 신뢰할 수 없는 사용자와 공유 하는 경우에 일부 문제가 발생할가 중지 되지만 공동 디버깅 하는 경우입니다. 라이브 공유 하면 게스트 콘솔/REPL 명령을 실행 하도록 초대 하 고 따라서 **않아야 할 실행 명령을 실행 하는 악의적인 행위자 위험이**합니다.

따라서 해야 **만 신뢰 하는 사용자를 사용 하 여 공동 디버그 합니다.**

더 알아보세요: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>로컬 서버를 공유합니다.

공동 디버깅 시 호스트가 디버깅 세션을 위해 제공하는 애플리케이션의 서로 다른 부분을 액세스하는 것은 정말 유용할 수 있습니다. 브라우저에서 앱에 액세스, 로컬 데이터베이스에 액세스 하거나 도구에서 REST 끝점을 적중 수 있습니다. 라이브 공유를 통해 공유"서버" 게스트의 컴퓨터에서 정확히 동일한 포트를 호스트의 컴퓨터에서 로컬 포트를 매핑하는 수 있습니다. 게스트 조작할 수 있습니다 다음 응용 프로그램 컴퓨터에서 로컬로 실행 된 것 처럼 정확 하 게 (예: 호스트와 게스트 모두 액세스할 수 실행 되는 웹 앱 http://localhost:3000)합니다.

그러나 호스트로, 해야 **포트 공유를 사용 하 여 매우 신중 하 게** 게스트와 공유만을 사용 하 여 응용 프로그램 대신 시스템 포트를 포트. 게스트에 대 한 공유 포트는 서버/서비스를 자신의 컴퓨터에서 실행 된 것 처럼 정확 하 게 작동 합니다. 이 매우 유용 하지만 잘못 된 포트를 공유 하는 경우는 것은 위험할 수도 수 있습니다. 이러한 이유로 Live Share는 무엇을 해야 하거나 구성 설정 및 작업을 수행 하는 호스트 하지 않고 공유 하지 말아야 하는 방법에 대 한 어떠한가 정도 만들지 않습니다.

Visual Studio에서의 **웹 응용 프로그램 포트** ASP.NET 프로젝트에 지정 된 됩니다 **디버깅만 해당 하는 동안 자동으로 공유** 실행 하는 경우 웹 앱에 대 한 게스트 액세스를 용이 하 게 합니다. 그러나 해제할 수 있습니다이 자동화 도구를 설정 하 여 > 옵션 > Live Share > "공유 웹 앱 디버그" 하려는 경우 "False"로 합니다.

Visual Studio Code에서 Live Share 하려고 **적절 한 응용 프로그램 포트 검색** 와 공유 합니다. 그러나 settings.json에 다음을 추가 하 여 비활성화할 수 있습니다.

        liveshare.autoShareServers: false

두 경우 모두에서 추가 포트를 공유 하는 경우 주의 해야 합니다.

여기에 기능을 구성 하는 방법에 대 한 자세한 수 있습니다. [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>공유 터미널

최신 개발 환경에서는 다양한 명령줄 도구를 자주 사용합니다. 다행스럽게도 Live Share는 호스트에게 필요에 따라 게스트와 “터미널을 공유”할 수 있는 기능을 제공합니다. 공유 터미널와 게스트 모두 명령을 실행 하 고 결과 볼 수 있도록 읽기 전용 또는 완벽 하 게 공동 작업을 수 있습니다. 호스트에 게는 표시 출력을 다른 협력자 또는 임의 개수의 명령줄을 사용 하도록 테스트를 빌드, 실행 또는 도구 심사 환경 관련 문제를 허용할 수 있습니다.

호스트만 시작 하나에서 예기치 않거나 감시 하는 작업을 수행 하는 게스트를 방지 하기 위해 공유 터미널을 시작할 수 있습니다. 공유 터미널 호스트를 시작 하면이 읽기 전용 이거나 인지 읽기/쓰기를 지정할 수 있습니다. 터미널 읽기/쓰기 인 경우에 쉽게 게스트 마음에 들지 않으면 작업을 수행 하는 경우 사용자가 개입할 수 있도록 하는 호스트를 포함 하 여 터미널에서 입력할 수 모든 사용자. 그러나 안전 하 게 하려면 수행 해야 합니다 **만 귀하에 게 읽기/쓰기 액세스 게스트 실제로 필요한 것을 알고 있는 경우** 계획 하 고 읽기 전용으로 터미널만 하려는 경우 게스트를 실행 하면 명령 출력을 참조 하세요.

Visual Studio에서 터미널 기본적으로 공유 되지 않습니다. VS Code에서 터미널 자동으로 공유 **읽기 전용** 기본적으로 합니다. 그러나 settings.json에 다음을 추가 하 여 비활성화할 수 있습니다.

```json
"liveshare.autoShareTerminals": false
```

더 알아보세요: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>AAD 관리자 동의

Microsoft를 사용 하 여 로그인이 지 원하는 **회사 또는 학교 전자 메일 주소** 메시지가 표시 될 수 있습니다 **"관리자 승인 필요"** 로그인 할 때입니다. Live Share의 보안 기능에 대 한 사용자 정보에 대 한 읽기 액세스를 필요 하 고 Azure AD 테 넌 트 디렉터리의 내용에 액세스 하는 새 응용 프로그램에 대 한를 "관리자 동의"를 요구 하도록 설정 됩니다 때문입니다.

AD 관리자에 게 다음 정보를 사용 하 여이 문제를 해결 해야 합니다.

* **응용 프로그램 이름**: Visual Studio Live 공유 (내부)
* **응용 프로그램 유형을**: 웹앱
* **응용 프로그램 상태**: 프로덕션
* **위임 된 권한**: User.Read
* **응용 프로그램 URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **회신 URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

Live Share를 사용 하 여 사용자에 대해 한 번만 해야이 합니다. 참조 [여기](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes) 하 고 [여기](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal) 세부 정보에 대 한 합니다.

## <a name="see-also"></a>참고자료

* [방법: Visual Studio Code를 사용 하 여 공동 작업](../use/vscode.md)
* [방법: Visual Studio를 사용 하 여 공동 작업](../use/vs.md)
* [Live Share 연결 요구 사항](connectivity.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
