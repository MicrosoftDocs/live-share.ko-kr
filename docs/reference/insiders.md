---
title: 참가자-Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share 내의 ' 참가자 ' 채널에 대 한 설명입니다.
ms.custom: ''
ms.date: 04/02/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 04bfb314ebae711566a8bab8b0ada8f2fbd2e940
ms.sourcegitcommit: 6b46e300d76eda661ab34c67a3b909d5c162cd9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/28/2019
ms.locfileid: "70062294"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>참가자

Visual Studio Live Share 팀은 신속 하 게 반복 하 고, 새로운 아이디어를 시도 하 고, 고객에 게 귀를 보내고 있습니다. Insider은 사용자에 게 모든 새로운 기능을 먼저 사용해 보고 소중한 의견을 제공할 수 있는 기회를 제공 합니다. 아래의 [참가자](#BecomeanInsider) 가 되는 방법을 알아보고 개발자 공동 작업의 미래를 파악 하는 데 도움을 주세요. 

## <a name="new-to-insiders"></a>✨ 새 참가자 ✨


### <a name="reusable-sessions-vs-code"></a>**재사용 가능한 세션 (VS Code)**

이제 재사용 가능한 세션을 호스트할 수 Live Share. 재사용 가능한 세션은 다양 한 시나리오에서 Live Share 세션을 다시 사용 하는 기능을 제공 합니다. 즉, 기술 인터뷰, 주간 mob-프로그래밍 세션에 대해 Live Share 세션을 미리 예약 하 고, 친구를 멘토링 하는 동안 동일한 세션을 사용할 수 있습니다.

다시 사용할 수 있는 세션을 만들려면 다음을 수행 합니다.
1. `Command Palette` 사용 하 여 이동`Ctrl+Shift+P`
1. "라이브 Sha ..."를 입력 합니다. **'_Live Share를 클릭 합니다. 재사용 가능한 세션 링크_** 만들기 ' 명령입니다.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. 그러면 재사용 가능한 세션이 생성 되 고이에 대 한 링크가 클립보드에 복사 됩니다. 편집기의 오른쪽 아래 모서리에 알림 팝업이 표시 됩니다.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. 재사용 가능한 세션을 만들었습니다. 세션 면맞춤 링크를 공유 하 고 세션에 액세스할 때마다 사용 합니다.

> [!TIP] 
>재사용 가능한 세션 링크는 지속 되며, 만든 날짜 또는 마지막 사용 날짜 로부터 30 일 동안 지속 됩니다. 즉, 적어도 30 일 마다 세션을 계속 해 서 사용 하는 경우 만료에 대해 걱정할 필요가 없습니다. 쉽게 액세스할 수 있는 안전한 장소에 링크를 저장 하면 됩니다.
 

### <a name="direct-user-invitations"></a>**직접 사용자 초대**

현재 Visual Studio와 Visual Studio Code는 두 가지 주요 `Contacts` 기능을 사용할 수 있는 창을 제공 합니다.

1. 최근 30 일 내 `Suggested Contacts`에 현재 열려 있는 프로젝트를 제공한 개발자 인의 목록을 표시 합니다. 실제로 이러한 작업은 공동 작업을 수행 하는 데 도움이 될 것 이므로 쉽게 시작할 수 있도록 하는 것이 좋습니다.

2. 이전에 Live Share를 `Recent Contacts`사용 하 여 협력 된 개발자 인 목록을 제공 합니다. 실제로 대부분의 개발자는 동일한 사람들과 공동 작업을 수행 하므로 최근에 사용한 목록을 통해 팀/교실/등의 작업을 더 반복 가능한 방법으로 사용할 수 있습니다.

그러나이 목록에서는 현재 전자 메일을 통해 최근/제안 된 연락처를 초대 하는 것만 가능 합니다 .이는이 처럼 효율적이 지 않습니다. `Contacts` 최신 Live Share 업데이트를 설치 하 고 (위에 설명 `Insiders` 된 대로)를 사용 하도록 설정 하면 이제 **개발자를 IDE에서 직접 공동 작업 세션으로 초대할**수 있습니다. Visual Studio Code를 사용 하는 경우이 기능이 작동 하려면 [참가자 빌드](https://code.visualstudio.com/insiders/) 를 설치 해야 합니다.

![직접 Invitatiosn](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>피어 (right)를 세션에 직접 초대 하는 Live Share 호스트 (왼쪽)</em>

개발자가 Live Share를 사용 하 여 로그인 하면 해당 가용성 상태가 피어에 게시 됩니다. 결과적으로 팀의 누군가가 온라인 상태이 고 즉시 공동 작업을 시작 하는 것을 볼 수 있습니다. 세션에 조인 하는 옵션을 제공 하는 알림 메시지를 받게 됩니다. 이렇게 하면 세션 Url을 완전히 교환할 필요가 없습니다.

5 분 동안 활동이 없을 경우 상태가 자동으로로 `Away`전환 되 고 Live Share 세션 내에 있으면 상태가 자동으로 (suprresses 초대 알림 메시지 알림)로 `Do not disturb` 전환 됩니다. 다시 활성 상태가 되 고 Live Share 세션을 종료 하면 상태가 자동으로로 `Available`다시 전환 됩니다. 이 동작을 사용 하면 실제로 Live Share 상태를 관리할 필요가 없습니다. 직접 초대를 사용 하도록 설정 하 고 공동 작업을 사용할 수 있는지 여부와 상관 없이 동료와 의견을 교환할 수 있습니다. 그러나 원하는 경우 언제 든 지 수동으로 상태를 설정할 수 있습니다.

이 기능을 옵트아웃 (opt out) 하려는 경우 Visual Studio의 Live Share 설정 및 `Presence` Visual Studio Code에서 설정을 사용 하지 않도록 설정할 수 있습니다. 사용 하지 않도록 설정 된 경우에도 다른 상태를 보고 초대할 수 있지만 상태는 게시 되지 않으며 다른 사용자가 직접 초대할 수 없습니다.

 

## 참가자 <a name="BecomeanInsider"></a> 가 됩니다.

기본적으로 Visual Studio Live Share 확장을 설치한 후에는 모든 프로덕션 준비 기능 `Stable` (예: 공동 편집, 공유 디버깅, 터미널)을 포함 하는 기능 집합을 사용 하 게 됩니다. 그러나 작업 중인 기능에 대 한 초기 액세스 권한을 얻으려면 IDE에서 다음 설정을 변경 하 여 `Insiders` 기능 집합을 옵트인 (opt in) 할 수 있습니다.

* Visual Studio

    ![feature-set-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![feature-set-vscode](../media/feature-set-vscode.png)

다음 섹션에서는 현재 `Insiders` 기능 집합 내에 있는 기능 집합을 설명 하므로, 앞서 언급 한 설정을 변경한 후에는 평가할 준비가 된 것입니다.



## <a name="see-also"></a>참고자료

- [언어 및 플랫폼 지원](platform-support.md)
- [Live Share 연결 요구 사항](connectivity.md)
- [Live Share의 보안 기능](security.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
