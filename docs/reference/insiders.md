---
title: 참가자-Visual Studio Live 공유 | Microsoft Docs
description: Visual Studio Live Share 내 '참가자' 채널의 설명입니다.
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
ms.openlocfilehash: a79effc25c09851301bb2231511a8a9d8a9f549b
ms.sourcegitcommit: 6e84bf17eedd616417f474551344c2161700c4d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67192717"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>참가자

Visual Studio Live Share 팀 사용자 의견을 반영 하 고, 순서를 신속 하 게 반복 하 려 하 고 이때 두 가지 별도 기능 "채널"의 일부로, 새로운 기능을 수신 하는 방법을 신속 하 게 결정할 수 있도록 합니다. 기본적으로 Visual Studio Live Share 확장을 설치한 후 사용 중인는 `Stable` 집합 (예: 공동 편집, 공유 디버깅, 터미널) 프로덕션이 준비 된 기능을 모두 포함 하는 기능입니다. 그러나 현재 진행 하는 기능에 초기 액세스 하려는 경우 있습니다 수에 옵트인 합니다 `Insiders` IDE에서 다음 설정을 변경 하 여 기능 집합:

* Visual Studio

    ![feature-set-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![feature-set-vscode](../media/feature-set-vscode.png)

다음 섹션에서는 현재 내에 있는 기능 집합을 `Insiders` 집합 장착 되어 있으며 따라서 앞에서 언급 한 설정을 변경 하면 평가 준비가:

## <a name="direct-user-invitations"></a>직접 사용자 초대

Visual Studio 및 Visual Studio Code를 모두 제공 하는 현재는 `Contacts` 두 가지 주요 기능을 사용 하도록 설정 하는 창:

1. 목록을 표시 `Suggested Contacts`, 지난 30 일 내에 현재 열려 있는 프로젝트에 기여 했는 개발자는 합니다. 실제로, 공동 작업 하려는 가능성이 담당자 이며 따라서 좋습니다을 쉽게 시작 하기 위해.

2. 목록을 제공 `Recent Contacts`, Live Share를 사용 하 여 이전에 기록한 했으므로 개발자는 합니다. 실제로 대부분의 개발자는 자주 동일한 사람들과 공동 작업 하 고 최근에 사용한 목록에 팀/클래스 룸/etc를 사용 하는 반복 가능한 보다 의미를 활성화 하는 따라서 합니다.

그러나는 `Contacts` 목록 현재 수만 있습니다/제안 된 최근 연락처 전자 메일을 통해 초대 알게는 효율적이 지 않은 않을 수 있습니다. Live Share 최신 업데이트를 설치 하 고 사용 하도록 `Insiders` (위에서 설명한 대로), 이제 있으므로 할 **개발자가 IDE에서 직접 공동 작업 세션에 초대**! Visual Studio Code를 사용 하는 경우 해야 설치를 [참가자 빌드](https://code.visualstudio.com/insiders/) 이 기능이 작동 하기 위해.

![직접 Invitatiosn](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>구성 요소를 직접 피어 (오른쪽) 세션에 초대 (왼쪽) Live Share 호스트</em>

일단 개발자 로그인 Live Share를 사용 하 여 해당 가용성 상태를 자신의 동료에 게 게시 됩니다. 결과적으로, 다른 팀원이 온라인 상태가 되 고 즉시 시작 하는 공동 작업을 볼 수 있습니다. 여부 세션에 참가 하는 옵션이 제공 하는 알림 메시지를 받게 됩니다. 이 세션 Url을 완전히 교환할 필요가 없습니다.

전까지 비활성 시간 5 분 후 상태를 자동으로 바뀝니다 `Away`, 상태는 자동으로 전환 하면 Live Share 세션 내에서 및 `Do not disturb` (suprresses 초대 토스트 알림을). 다시 활성화 하거나 Live Share 세션을 유지 한 후 상태를 자동으로 다시 전환 됩니다 `Available`합니다. 이 동작으로 실제로 Live Share 상태를 관리할 필요가 없습니다. 직접 초대를 사용 하도록 설정 하 고 동료 되 고 있는지 공동 작업에 사용할 수 있는 여부와 통신 하는 것이 단순히 있습니다. 그러나 원하는 경우 사용자의 상태를 설정할 항상 수동으로 있습니다.

옵트아웃 하려면이 기능을 원한다 면 비활성화할 수 있습니다 단순히는 `Presence` Visual Studio 및 Visual Studio Code에서 Live Share 설정 내에서 설정 합니다. 비활성화 여전히 수 서로의 상태를 보고, 초대 하지만 상태를 게시할 수 없습니다, 하 고 직접 아닙니다 초대 합니다.

## <a name="see-also"></a>참고자료

- [언어 및 플랫폼 지원](platform-support.md)
- [Live Share 연결 요구 사항](connectivity.md)
- [Live Share의 보안 기능](security.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
