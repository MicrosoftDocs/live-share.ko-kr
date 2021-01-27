---
title: 보안 | Microsoft Docs
description: Visual Studio Live Share의 보안 기능에 대 한 정보입니다.
ms.custom: ''
ms.date: 12/17/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 2b3021e96b321976772e6ab99a18cceb56929404
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870882"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Live Share의 보안 기능

Visual Studio Live Share의 공동 작업 세션은 세션에 조인 하 고 공동 편집, 디버그 등의 작업을 수행할 수 있는 강력한 기능입니다. 그러나 이러한 액세스 수준을 고려 하면에서 제공 하 Live Share 보안 기능에 관심이 있을 것입니다. 이 문서에서는 필요에 따라 환경을 보호 하기 위한 몇 가지 권장 사항 및 옵션을 제공 합니다.

**공동 작업 도구와 마찬가지로 신뢰할 수 있는 사용자와 코드, 콘텐츠 및 응용 프로그램을 공유 하기만 하면 됩니다.**

## <a name="connectivity"></a>연결

피어 간 세션을 시작할 때 Live Share 피어 투 피어 연결을 설정 하려고 시도 하는 경우 (예: 방화벽/t s p s로 인 한)이 가능 하지 않은 경우 (예: 방화벽/t s p s)는 클라우드 릴레이를 사용 하 여 대체 합니다. 그러나 두 연결 유형 (P2P 또는 relay)에서 피어 간에 전송 되는 모든 데이터는 SSH 프로토콜을 사용 하 여 종단 간 암호화 됩니다. 릴레이 연결의 경우 SSH 암호화는 TLS 암호화 Websocket 위에 계층화 됩니다. 즉, Live Share는 보안을 위해 클라우드 릴레이 서비스에 의존 하지 않습니다. 릴레이가 손상 된 경우에도 Live Share 통신의 암호를 해독할 수 없습니다.

Live Share 서비스의 역할은 사용자 인증 및 세션 검색으로 제한 됩니다. 서비스 자체는 세션의 콘텐츠를 저장 하거나 액세스 권한을 보유 하지 않습니다. Live Share의 모든 사용자 콘텐츠는 SSH 세션을 통해 전송 됩니다. 여기에는 코드, 터미널, 공유 서버 및이를 기반으로 하는 Live Share 또는 확장에서 제공 하는 기타 공동 작업 기능이 포함 됩니다.

이러한 동작 및 Live Share의 연결 요구 사항 변경에 대 한 자세한 내용은 **[Live Share 연결 요구 사항](connectivity.md)** 을 참조 하세요.

### <a name="wire-encryption"></a>실시간 암호화 

SSH 프로토콜은 Diffie-Hellman 키 교환을 사용 하 여 세션에 대 한 공유 암호를 설정 하 고 AES 대칭 암호화를 위한 키에서 파생 됩니다. 암호화 키는 세션 기간 동안 주기적으로 회전 됩니다. 공유 세션 암호 및 모든 암호화 키는 양쪽 모두 메모리 내에서 유지 관리 되며 세션 기간 동안만 유효 합니다. 이러한 메시지는 디스크에 기록 되거나 서비스 (Live Share 포함)로 전송 되지 않습니다.

### <a name="peer-authentication"></a>피어 인증

또한 SSH 세션은 양방향 인증입니다. 호스트 (SSH 서버 역할)는 SSH 프로토콜에 대 한 표준으로 공개/개인 키 인증을 사용 합니다. 호스트는 Live Share 세션을 공유 하는 경우 세션에 대 한 고유한 RSA 공개/개인 키 쌍을 생성 합니다. 호스트 개인 키는 호스트 프로세스의 메모리에만 유지 됩니다. 디스크에 기록 되거나 Live Share 서비스를 비롯 한 모든 서비스로 전송 되지 않습니다. 호스트 공개 키는 게스트에서 초대 링크를 통해 액세스할 수 있는 세션 연결 정보 (IP 주소 및/또는 릴레이 끝점)와 함께 Live Share 서비스에 게시 됩니다. 게스트가 호스트의 SSH 세션에 연결 되 면 게스트는 SSH 호스트 인증 프로토콜을 사용 하 여 호스트가 게시 된 공개 키에 해당 하는 개인 키를 보유 하 고 있는지 확인 합니다 (게스트는 실제로 개인 키를 볼 수 없음).

게스트는 Live Share 토큰을 사용 하 여 호스트에 대해 자신을 인증 합니다. 토큰은 사용자 id에 대 한 클레임을 포함 하는 Live Share 서비스에서 발급 한 서명 된 JWT로, MSA, AAD 또는 GitHub 로그인을 통해 가져옵니다. 또한 토큰은 특정 Live Share 세션 (초대 링크가 있거나 호스트에 의해 특별히 초대 됨)에 액세스할 수 있음을 나타내는 클레임을 포함 합니다. 호스트는이 토큰의 유효성을 검사 하 고, 클레임을 확인 하 고 (옵션에 따라 호스트 사용자에 게 메시지를 표시할 수 있음) 게스트가 세션에 참여 하도록 허용 합니다.

## <a name="invitations-and-join-access"></a>초대 및 조인 액세스

새 공동 작업 세션을 시작할 때마다 Live Share 초대 링크에 배치 되는 **새 고유 식별자** 를 생성 합니다. 이러한 링크는 링크의 식별자가 "비 추측할"이 고 _단일 공동 작업 세션이 지속 되는 동안에만 유효_ 하기 때문에 신뢰할 수 있는 견고한 보안 기반을 제공 합니다.

### <a name="removing-an-unexpected-guest"></a>예기치 않은 게스트 제거

호스트인 경우 게스트가 공동 작업 세션에 가입할 때마다 자동으로 알림이 표시 됩니다.

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

그래도 알림이 표시 되지 않는 이유로 인해 조인 된 게스트를 제거 하는 기능을 제공 합니다. (예를 들어 회사 전체 채팅 시스템에서 실수로 링크를 게시 하 고 임의의 직원을 조인 하는 경우) 표시 되는 알림에서 "제거" 단추를 클릭 하기만 하면 공동 작업 세션에서 제거 됩니다.

**VS Code** 에서 조인 알림을 해제 한 경우에도 참가자를 제거할 수 있습니다. 탐색기에서 Live Share 보기 또는 VS Code 활동 표시줄의 사용자 지정 탭을 열어 참가자의 이름을 마우스로 가리키거나 마우스 오른쪽 단추로 클릭 하 고 "참가자 제거" 아이콘 또는 옵션을 선택할 수 있습니다.

![VS Code에서 참가자 제거](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>게스트 승인 필요

일반적으로 공동 작업 세션에 참여 하는 참가자는 Microsoft AAD (회사 또는 학교 계정), 개인 Microsoft 계정 또는 GitHub 계정을 사용 하 여 **Live Share에 로그인** 됩니다. 로그인 한 사용자에 대 한 "알림 + 제거" 기본값은 이러한 게스트에 대 한 적절 한 속도와 제어를 제공 하지만 중요 한 작업을 수행 하는 경우 약간의 **작업을 잠글** 수 있습니다.

또한 특정 상황에서는 모든 게스트가 공동 작업 세션에 참여 하도록 강제 하는 것이 문제가 될 수 있습니다. 예를 들어 게스트, 교실/학습 시나리오로 참여 하거나 지원 되는 계정 유형 중 하나가 없는 사람과 공동으로 작업 하는 경우 새 사용자에 게 Live Share 하도록 요청 하는 경우가 있습니다. 이러한 이유로 Live Share을 사용 하면 **로그인 하지** 않은 사용자가 공동 작업 세션을 **읽기 전용** 게스트로 조인할 수 있습니다. 호스트는 이러한 게스트를 기본적으로 조인 하기 전에 **승인** 해야 하지만 이러한 "익명" 게스트를 허용 하지 않거나 대신 항상 승인 해야 할 수 있습니다.

#### <a name="requiring-guest-approval-for-signed-in-users"></a>로그인 한 사용자에 대 한 게스트 승인 필요

"승인" 할 때까지 로그인 한 게스트가 공동 작업 세션을 조인 하지 않도록 하려면 다음 설정을 변경 합니다.

* **VS Code** 에서 settings.js(파일 > 기본 설정 > 설정)에 다음을 추가 합니다.

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* **Visual Studio** 에서 도구 > 옵션 > Live Share > "게스트 승인 필요"를 True로 설정 합니다.

    ![게스트 승인 설정이 강조 표시 된 Visual Studio 설정 창](../media/vs-setting-guestapproval.png)

이 시점부터 조인 하는 각 게스트를 승인 하 라는 메시지가 표시 됩니다.

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

게스트로 호스트에서이 설정을 사용 하는 세션에 참여 하는 경우 호스트에서 승인 될 때까지 대기 중인 Live Share 상태 표시줄 또는 조인 대화 상자에 알림이 표시 됩니다.

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>로그인 하지 않은 사용자 자동 거부 또는 수락 (익명)

위에서 설명한 대로 Live Share **로그인 되지 않은 사용자가** 공동 작업 세션을 **읽기 전용** 게스트로 조인 하도록 구성할 수 있습니다.  이러한 **"익명" 게스트는 가입할 때 이름을 입력 해야** 하지만 단순한 이름은 실제 로그인과 동일한 수준의 보증을 제공 하지 않습니다. 따라서 기본적으로 호스트에는 위에서 설명한 "게스트 승인 필요" 설정에 관계 없이 익명 게스트 **를 승인 하 라는 메시지가 표시 됩니다** .

다음과 같이 **항상** 익명 게스트를 거부 (익명 게스트 사용 안 함) 하거나 항상 익명 사용자를 **허용할** 수 있습니다.

* **VS Code** 에서 settings.js( `liveshare.anonymousGuestApproval` 파일 > 기본 설정 > 설정)에서 `accept` , `reject` 또는 `prompt` (기본값)로 설정 합니다.

* **Visual Studio** 에서 도구 > 옵션 > Live Share "익명 게스트 승인"을 > 하 여 적절 하 게 수락, 거부 또는 프롬프트 (기본값)를 설정 합니다.

 **에 관계 없이 신뢰할 수 있는 사용자 에게만 Live Share 초대 링크를 전송 해야 합니다.**

## <a name="controlling-file-access-and-visibility"></a>파일 액세스 및 표시 유형 제어

게스트로 서 Live Share의 원격 모델은 프로젝트의 전체 콘텐츠를 동기화 하지 않고 호스트에서 공유 하는 파일 및 폴더에 대 한 읽기/쓰기 액세스를 빠르게 제공 합니다. 따라서 전체 공유 파일 트리에서 파일을 독립적으로 탐색 하 고 편집할 수 있습니다. **그러나 이러한 자유도는 호스트에 대 한 몇 가지 위험을 야기 합니다.** 개념에서 개발자는 사용자의 지식 없이 소스 코드를 사용 하 여 수정 하거나 공유 파일 트리의 어딘가에 있는 중요 한 소스 코드 또는 "비밀"을 볼 수 있습니다. 따라서 호스트는 항상 공유 하는 프로젝트 전체에 대 한 액세스 권한을 게스트에 게 원하지 않을 수 있습니다. 다행히이 원격 모델의 이점은 기능을 저하 시 키 지 않고 다른 사용자와 공유 하지 않을 파일을 "제외" 할 수 있다는 것입니다. 게스트는 이러한 파일에 대 한 액세스를 자체적으로 수행 하려는 경우에도 일반적으로 이러한 파일에 액세스 해야 하는 디버깅 세션 등의 작업에 참여할 수 있습니다.

공유 하는 폴더 또는 프로젝트에 **.vsls.js파일에** 추가 하 여이를 수행할 수 있습니다. 이 json 형식의 파일에 추가 하는 모든 설정은 Live Share 파일을 처리 하는 방식을 변경 합니다. 직접 제어를 제공 하는 것 외에도 이러한 파일은 소스 제어에 커밋될 수 있으므로 프로젝트를 복제 하는 모든 사용자가 추가 작업을 수행할 필요 없이 이러한 규칙을 활용할 수 있습니다.

파일에 .vsls.js예제는 다음과 같습니다.

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
> 공동 작업 세션을 시작할 때 공유 하는 모든 파일/폴더를 **읽기** 전용으로 설정할 수도 있습니다. 자세한 내용은 [아래](#read-only-mode) 를 참조 하세요.

이러한 속성을 통해 게스트에서 수행할 수 있는 작업을 변경 하는 방법을 살펴보겠습니다.

### <a name="properties"></a>속성

**Excludefiles** 속성을 사용 하면 Live Share 게스트가 특정 파일 또는 폴더를 열 수 없도록 하는 glob 파일 패턴 (.gitignore 파일과 매우 유사)의 목록을 지정할 수 있습니다. 이는 사용자가 편집 위치로 이동 하거나 이동 하는 것과 같은 시나리오를 포함 하 여 _공동 작업 디버깅 중에 파일을 한 단계씩 실행 하 고 정의로 이동 등의 코드 탐색 기능을 제공 합니다._ 암호, 인증서 또는 암호를 포함 하는 경우와 같은 상황에서 공유 하지 않으려는 파일에 사용 됩니다. 예를 들어 보안을 제어 하기 때문에 파일에 대 한 .vsls.js항상 제외 됩니다.

**HideFiles** 속성은 비슷하지만 엄격한 것은 아닙니다. 이러한 파일은 단순히 파일 트리에서 숨겨집니다. 예를 들어, 디버깅 하는 동안 이러한 파일 중 하나를 한 단계씩 실행 하면 편집기에서 계속 열립니다. 이 속성은 다른 소스 제어 시스템을 사용 하는 경우와 마찬가지로 .gitignore 파일 설정이 없거나 혼란 또는 혼동을 피하기 위해 이미 존재 하는 것을 원하는 경우에 주로 유용 합니다.

**.Gitignore** 설정은 Live Share 공유 폴더에 있는 .gitignore 파일의 콘텐츠를 처리 하는 방법을 설정 합니다. 기본적으로 .gitignore 파일에 있는 모든 glob는 "hideFiles" 속성에 지정 된 것 처럼 처리 됩니다. 그러나 다음 값 중 하나를 사용 하 여 다른 동작을 선택할 수 있습니다.

| 옵션    | 결과                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | .gitignore 콘텐츠는 게스트 편집기 설정에 의해 필터링 되지 않는다고 가정 하 고 파일 트리의 게스트에 표시 됩니다. |
| `hide`    | **기본값입니다.** .Gitignore 내의 glob는 "hideFiles" 속성에 있는 것 처럼 처리 됩니다.                   |
| `exclude` | .Gitignore 내의 glob는 "excludeFiles" 속성에 있는 것 처럼 처리 됩니다.                                 |

설정의 단점은 `exclude` node_modules와 같은 폴더의 내용이 자주 .gitignore 하지만 디버깅 중에 한 단계씩 실행 하는 데 유용할 수 있습니다. 따라서 Live Share는 excludeFiles 속성에서 "!"을 사용 하 여 규칙을 되돌리는 기능을 지원 합니다. 예를 들어 파일에 대 한이 .vsls.js는 node_modules를 제외 하 고 ".gitignore"에 있는 모든 항목을 제외 합니다.

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

숨기기 및 제외 규칙은 개별적으로 처리 되므로 실제로 제외 하지 않고 간단 하 게 node_modules 숨기려는 경우 다음과 같이 파일을 편집할 수 있습니다.

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

### <a name="vslsjson-files-in-sub-folders"></a>하위 폴더에 있는 파일에 대 한 .vsls.js

마지막으로 .gitignore 파일에 대 한 .vsls.js를 하위 폴더에 배치할 수 있습니다. 숨기기/제외 규칙은 공유한 루트 폴더의 파일에 대 한 .vsls.js(있는 경우)로 시작 하 여 지정 된 파일에서 처리할 파일의 .vsls.js를 찾기 위해 각 하위 폴더를 탐색 하는 방법으로 결정 됩니다. 폴더의 파일에 대 한 .vsls.js내용은 파일 트리를 따라, 더 높은 수준에서 설정 된 추가 (또는 재정의) 규칙을 보완 합니다.

### <a name="disabling-external-file-sharing"></a>외부 파일 공유 사용 안 함

기본적으로 Live Share는 호스트에서 여는 공유 폴더/솔루션 외부에 있는 파일도 공유 합니다. 이렇게 하면 다시 공유 하지 않고도 관련 된 다른 파일을 쉽게 열 수 있습니다.

이 기능을 사용 하지 않도록 설정 하려면 다음을 수행 합니다.

* **VS Code** 에서 settings.js에 다음을 추가 합니다.

    ```json
    "liveshare.shareExternalFiles": false
    ```

* **Visual Studio** 에서 도구 옵션을 &gt; &gt; &gt; "외부 파일 공유" Live Share False로 설정 합니다.

## <a name="read-only-mode"></a>읽기 전용 모드

경우에 따라 코드를 호스트로 공유 하는 경우 게스트가 편집 하지 않도록 할 수 있습니다. 사용자의 코드를 확인 하는 데 게스트가 필요 하거나, 많은 게스트에 게 프로젝트를 표시 하 고 불필요 하거나 실수로 편집 하지 않으려고 할 수 있습니다. Live Share는 읽기 전용 모드에서 프로젝트를 공유 하는 기능을 제공 합니다.

호스트로 서, 공유 하는 경우 공동 작업 세션에 대해 읽기 전용 모드를 사용 하도록 설정 하는 옵션이 있습니다. 게스트가 조인 되 면 코드를 편집할 수 없게 됩니다. 그러나 다른 사용자의 커서 및 강조 표시는 물론 프로젝트를 탐색할 수 있습니다.

읽기 전용 모드에서 게스트를 사용 하 여 공동 디버그할 수 있습니다. 게스트는 디버깅 프로세스를 단계별로 실행 하는 기능을 제공 하지 않지만 중단점을 추가 또는 제거 하 고 변수를 검사할 수 있습니다. 또한 게스트를 사용 하 여 서버 및 터미널 (읽기 전용)을 공유할 수 있습니다.

읽기 전용 공동 작업 세션을 시작 하는 방법에 대해 자세히 알아볼 수 있습니다. [ ![ VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [ ![ VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

## <a name="co-debugging"></a>공동 디버깅

매우 간단한 코딩 문제 또는 버그를 주요 당면 디버깅할 때 눈에 더 많은 것을 포함 하는 것이 유용할 수 있습니다. Visual Studio Live Share를 사용 하면 호스트에서 디버깅을 시작할 때마다 디버깅 세션을 모든 게스트와 공유 하 여 "공동 디버깅" 또는 "공동 디버깅"을 사용할 수 있습니다.

호스트는 디버깅 세션이 시작 또는 중지 되는 시점을 완벽 하 게 제어 하지만 신뢰 하지 않는 사람과 공유 하는 경우 공동 디버깅으로 인해 일부 위험이 발생 합니다. Live Share를 사용 하 여 콘솔/REPL 명령을 실행할 수 있으므로 **악의적인 행위자가 실행 하지 않으려는 명령을 실행할 위험이** 있습니다.

따라서 **신뢰할 수 있는 사용자로만 공동 디버그할** 수 있습니다.

자세한 정보: [ ![ VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [ ![ VS](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>로컬 서버 공유

공동 디버깅 시 호스트가 디버깅 세션을 위해 제공하는 애플리케이션의 서로 다른 부분을 액세스하는 것은 정말 유용할 수 있습니다. 브라우저에서 앱에 액세스 하거나 로컬 데이터베이스에 액세스 하거나 도구에서 REST 끝점을 적중 하는 것이 좋습니다. Live Share를 사용 하면 호스트 컴퓨터의 로컬 포트를 게스트 컴퓨터의 동일한 포트에 매핑하는 "서버를 공유할" 수 있습니다. 게스트는 컴퓨터에서 로컬로 실행 하는 것 처럼 정확 하 게 응용 프로그램과 상호 작용할 수 있습니다. 예를 들어 호스트와 게스트 모두에서 실행 되는 웹 앱에 액세스할 수 있습니다. http://localhost:3000)

그러나 호스트는 게스트와 **공유 하는 포트를 매우 선택적으로 사용** 하 고 시스템 포트 대신 응용 프로그램 포트만 공유 해야 합니다. 게스트의 경우 공유 포트는 서버/서비스를 자신의 머신에서 실행하는 것처럼 정확하게 작동합니다. 이 공유 포트는 매우 유용하지만 잘못된 포트를 공유하는 경우 위험할 수도 있습니다. 따라서 Live Share는 구성 설정이 나 호스트에서 작업을 수행 하지 않고 공유 해야 하는 항목에 대 한 가정을 하지 않습니다.

Visual Studio에서 ASP.NET 프로젝트에 지정 된 **웹 응용 프로그램 포트** 는를 실행 하는 동안 웹 앱에 대 한 게스트 액세스를 용이 하 게 하기 위해 **디버깅 중에 자동으로 공유** 됩니다. 그러나 선호 하는 경우 도구 > 옵션 > Live Share > 설정 하 여이 자동화를 해제할 수 있습니다.

Visual Studio Code에서 Live Share **적절 한 응용 프로그램 포트를 검색** 하 고 공유 합니다. 그러나 settings.js에 다음을 추가 하 여이 기능을 사용 하지 않도록 설정할 수 있습니다.

        liveshare.autoShareServers: false

두 경우 모두 추가 포트를 공유할 때 주의를 기울여야 합니다.

이 기능을 구성 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요. [ ![ VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [ ![ VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>터미널 공유

최신 개발 환경에서는 다양한 명령줄 도구를 자주 사용합니다. 다행스럽게도 Live Share는 호스트에게 필요에 따라 게스트와 “터미널을 공유”할 수 있는 기능을 제공합니다. 공유 터미널은 읽기 전용이거나 완전하게 공동 작업이 가능하므로 호스트와 게스트는 모두 명령을 실행하고 그 결과를 볼 수 있습니다. 호스트로 서 다른 협력자가 출력을 표시 하거나 원하는 수의 명령줄 도구를 사용 하 여 테스트, 빌드 또는 심사 환경 특정 문제를 실행 하는 것을 허용할 수 있습니다.

호스트만 공유 터미널을 시작 하 여 게스트를 시작 하지 않도록 하 고 기대 하거나 시청 하지 않는 작업을 수행할 수 있습니다. 공유 터미널을 호스트로 시작 하는 경우 읽기 전용 또는 읽기/쓰기 여야 하는지 여부를 지정할 수 있습니다. 터미널이 읽기/쓰기인 경우 호스트를 포함하여 누구나 터미널에 입력할 수 있습니다. 그러면 게스트가 호스트의 마음에 들지 않는 작업을 수행하는 경우 개입하기가 쉬워집니다. 그러나 안전하려면 호스트는 **게스트가 실제로 필요하다는 것을 아는 경우 게스트에게 읽기/쓰기 액세스 권한만 부여** 하고, 호스트가 실행하는 모든 명령의 출력을 게스트가 참조하기를 원하는 경우에 읽기 전용 터미널을 계속 사용해야 합니다.

Visual Studio에서 터미널은 기본적으로 공유 되지 않습니다. VS Code에서 터미널은 기본적으로 자동으로 **읽기** 전용으로 공유 됩니다. 그러나 settings.js에 다음을 추가 하 여이 기능을 사용 하지 않도록 설정할 수 있습니다.

```json
"liveshare.autoShareTerminals": false
```

자세한 정보: [ ![ VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [ ![ VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>AAD 관리자 동의

Microsoft에서 지원 되는 **회사 또는 학교 전자 메일 주소** 를 사용 하 여 로그인 할 때 로그인 할 때 **"관리자 승인 필요" 라는** 메시지가 표시 될 수 있습니다. 이는 Live Share 보안 기능에 대 한 사용자 정보에 대 한 읽기 권한이 있어야 하며, Azure AD 테 넌 트가 디렉터리의 콘텐츠에 액세스 하는 새 응용 프로그램에 대해 "관리자 동의"를 요구 하도록 설정 되어 있기 때문입니다.

AD 관리자는 다음 정보를 사용 하 여이 문제를 해결 해야 합니다.

* **응용 프로그램 이름**: Visual Studio Live Share (참가자)
* **응용 프로그램 유형**: 웹 앱
* **응용 프로그램 상태**: 프로덕션
* **위임 된 권한**: User. 읽기
* **응용 프로그램 URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **회신 URL**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

이 작업은 Live Share를 사용 하는 모든 사용자에 대해 한 번만 수행 해야 합니다. 자세한 [](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes) 내용은 여기 [및 여기를 참조](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal) 하세요.

## <a name="see-also"></a>추가 정보

* [방법: Visual Studio Code를 사용하여 공동 작업](../use/vscode.md)
* [방법: Visual Studio를 사용하여 공동 작업](../use/vs.md)
* [Live Share 연결 요구 사항](connectivity.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
