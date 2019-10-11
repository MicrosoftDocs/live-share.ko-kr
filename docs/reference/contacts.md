---
title: 현재 상태-Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share의 연락처에 대 한 현재 상태 서비스에 대 한 정보입니다.
ms.custom: ''
ms.date: 10/08/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: fishah
ms.author: fishah
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: a3b4c9f2b469e937d958e82df28a04044abf38d3
ms.sourcegitcommit: 50069912a317f8685976013e80738bbaa403a3fe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2019
ms.locfileid: "72178477"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="contacts-in-live-share"></a>Live Share의 연락처 

Live Share를 사용 하 고 외부 응용 프로그램 (예: 채팅 또는 전자 메일)을 통해 전송 되는 링크를 빠르게 받을 수 있는지 확인 합니다. 공동 작업을 장려 하는 것이 좋습니다 .이를 선호 하는 것이 가장 좋습니다. 이제 이제는 현재 **상태**에 대 한 **연락처** 가 있는 Live Share.

>연락처는 **Live Share v 1.0.950** 이상 버전에 대해 자동으로 사용 하도록 설정 됩니다.

아래 이미지에 표시 된 것 처럼 연락처는 Live Share 창에 별도의 창으로 나타납니다. 

![연락처](../media/vscode-contacts-intro.png)

<em>Live Share 창에 연락처 창 표시</em>
## <a name="who-shows-up-in-my-contacts"></a>내 연락처에 표시 되는 사람은 누구 인가요?

연락처 창은 작업 하는 동안 개발자의 자연 워크플로를 지 원하는 두 가지 유형의 연락처를 표시 합니다.
### <a name="1-recent-contacts"></a>1. 최근 연락처  
 Live Share를 사용 하 여 이전에 협력 한 개발자입니다. 실제로 대부분의 개발자는 동일한 사람들과 공동 작업을 수행 하므로 최근에 사용한 목록을 통해 팀/교실/등의 작업을 더 반복 가능한 방법으로 사용할 수 있습니다.
### <a name="2-suggested-contacts"></a>2. 제안 된 연락처
최근 30 일 내에 현재 열려 있는 프로젝트를 제공한 개발자입니다. 실제로 이러한 작업은 공동 작업을 수행 하는 데 도움이 될 것 이므로 쉽게 시작할 수 있도록 하는 것이 좋습니다.

## <a name="direct-user-invitations"></a>직접 사용자 초대 
모든 연락처는 편집기 내에서 Live Share 세션에 직접 초대할 수 있습니다. 세션에 조인 하는 옵션을 제공 하는 알림 메시지를 받게 됩니다. 이렇게 하면 세션 Url을 완전히 교환할 필요가 없습니다.
@no__t 0DirectInvitationVSCode @ no__t-1<em>피어 (right)를 세션에 직접 초대 하는 Live Share 호스트 (왼쪽)</em>

## <a name="how-does-status-for-contacts-work"></a>연락처의 상태는 어떻게 작동 하나요?
개발자가 Live Share를 사용 하 여 로그인 하면 **해당 가용성 상태가 피어에 게시 됩니다.** 따라서 팀의 누군가가 온라인 상태 인지 확인 한 다음 위와 같이 직접 초대를 사용 하 여 공동 작업을 바로 시작할 수 있습니다.
상태는 편집기 내에서 직접 설정할 수 있으므로 컨텍스트 전환이 없어도 팀에 대 한 가용성을 알릴 수 있습니다. Live Share 연락처에는 현재 4 개의 상태가 있습니다.

**1. 사용 가능:**  Live Share 확장이 있고 현재 편집기를 사용 하 고 있지만 세션에 있지 않은 경우 기본 상태는 `Available`이 됩니다.

**2. 방해 금지:**  현재 활성 Live Share 세션에 있고 모든 초대 알림이 표시 되지 않는 경우 상태는 `Do not disturb`으로 설정 됩니다.

**3. 자리 비움:**  5 분 동안 활동이 없으면 상태가 자동으로 `Away`으로 전환 됩니다.

**4. 오프 라인:**  오랜 시간 동안 또는 [공유 상태 옵트아웃 (opt out)](##ManagingPresence) 을 선택 하는 경우 오프 라인 상태로 유지 됩니다.


## 연락처 상태<a name="ManagingPresence"> </a> 관리

이 기능을 옵트아웃 (opt out) 하려는 경우-0 @no__t을 선택 하 여 상태 설정을 사용 하지 않도록 설정할 수 있습니다. 사용 하지 않도록 설정 된 경우에도 다른 상태를 보고 초대할 수 있지만 상태는 게시 되지 않으며 다른 사용자가 직접 초대할 수 없습니다.
상태 원을 클릭 하 여 오프 라인으로 전환 하도록 선택할 수 있습니다. 그러면 다음 드롭다운 메뉴가 표시 됩니다.

![dropdownstatus @ no__t-1 상태 <em>드롭다운 표시</em>

## <a name="faqs"></a>FAQ 

###### <a name="1-will-i-be-automatically-opting-into-sharing-status-when-i-use-live-share-v10950-and-above"></a>1. Live Share v 1.0.950 이상을 사용 하는 경우 공유 상태가 자동으로 선택 됩니다.

처음으로 연락처가 표시 되 면 알림 메시지를 표시 하 고 사용자의 상태를 공유 하는 옵션을 선택할 수 있습니다. 그런 다음 위와 같이 옵트아웃 (opt out)을 선택 하지 않으면 연락처와의 상태를 자동으로 공유 합니다.

###### <a name="2-can-i-add-my-own-contacts"></a>2. 내 연락처를 추가할 수 있나요?

현재 연락처 서비스는 자주 코드를 공유 하거나 함께 사용 하는 협력자를 자동으로 검색 하 고 사용자 고유의 연락처를 추가 하는 옵션을 제공 하지 않습니다. 


>연락처를 수동으로 추가할 수 있는 것이 도움이 될 것입니다. 여기에서 GitHub 기능 요청을 열어 우선 순위를 지정 하는 데 도움을 주세요 [.](https://github.com/MicrosoftDocs/live-share/issues/new?template=feature_request.md)
 

 