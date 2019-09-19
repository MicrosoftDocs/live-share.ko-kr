---
title: Visual Studio Code를 사용하여 공동 작업 - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Code 및 Live Share에 대한 협업 방법 세트.
ms.custom: ''
ms.date: 09/16/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: fishah
ms.author: fishah
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: ba2fd7558df2658efffda1c8578450f9c678d35d
ms.sourcegitcommit: 21e564ac23293e373b515892fa881d049f333cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71127413"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>방법: Live Share를 사용 하 여 기술 인터뷰

기술 인터뷰를 위해 Live Share 사용을 시작 하기 전에 다음과 같은 단일 정수 단계를 완료 해야 합니다. 다음 단계를 수행 하 여 **marketplace에서 Visual Studio Code 및 Live Share 확장 팩을 다운로드** [합니다.](../use/vscode.md#Installation)

Live Share은 재사용 가능한 세션을 호스트 하는 기능을 제공 합니다. 즉, 기술 인터뷰에 대해 미리 Live Share 세션을 예약할 수 있으며 링크 만료에 대해 걱정 하지 않아도 됩니다.

> [!TIP] 
>재사용 가능한 세션 링크는 지속 되며, 만든 날짜 또는 마지막 사용 날짜 로부터 30 일 동안 지속 됩니다. 인터뷰에 대해 재사용 가능한 세션 링크를 생성 하는 동안 인터뷰는 링크를 만든 날짜의 30 일 이내에 있습니다. 링크가 만료 되 면 다시 사용할 수 있는 새 세션을 만듭니다. (링크가 만료 되지 않도록 할 수 있는 방법이 있지만이 방법은 인터뷰에 대 한 것이 더 쉽습니다.)

### <a name="what-to-do-as-an-interviewer"></a>**Interviewer로 할 일은 무엇 인가요?**

Interviewer Live Share 세션의 호스트 역할을 합니다. Live Share에 익숙하지 않은 경우 방법 가이드의 [프로젝트 공유](../use/vscode.md) 섹션을 참조 하는 것이 좋습니다.

이제 기술 인터뷰에 대 한 Live Share 세션을 만들기 위해 일반 공동 작업 세션 대신 특별 한 "재사용 가능한 세션"을 만듭니다. 이렇게 하면 사전에 예약 하 여 언제 든 지 사용할 수 있는 Live Share 세션을 사용할 수 있습니다.

다시 사용할 수 있는 세션을 만들려면 다음을 수행 합니다.

1. `Command Palette` 사용 하 여 이동`Ctrl+Shift+P`
1. "라이브 Sha ..."를 입력 합니다. **'_Live Share를 클릭 합니다. 재사용 가능한 세션 링크_** 만들기 ' 명령입니다.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. 그러면 재사용 가능한 세션이 생성 되 고이에 대 한 링크가 클립보드에 복사 됩니다. 편집기의 오른쪽 아래 모서리에 알림 팝업이 표시 됩니다.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. 재사용 가능한 세션을 만들었습니다. 세션 면맞춤 링크를 공유 하 고 세션에 액세스할 때마다 사용 합니다.

이 링크를 받은 후에는 전자 메일을 통해 interviewee 또는 예약 메커니즘을 선택 하 여 공유 하면 됩니다. 인터뷰 시점에 해당 링크를 클릭 하면 Live Share 세션에 있을 것입니다. 

### <a name="what-to-do-as-the-interviewee"></a>**Interviewee로 할 일은 무엇 인가요?**

Live Share를 사용 하 여 기술적인 인터뷰를 기대 하는 경우에는 행운을 빌어요. 인터뷰 동안 편안 하 게 사용할 수 있도록 기본 Live Share 기능에 대해 잘 알고 있어야 합니다.

1. 인터뷰 전에 약간의 작업을 수행 하 Live Share는 방법에 대 한 이해를 돕기 위해 [방법 가이드](../use/vscode.md) 를 참조 하세요.

1. 인터뷰를 시작할 때 설치가 완료 될 때까지 기다리지 않도록 Visual Studio Code을 미리 설치 하는 것이 좋습니다.

1. 시간이 없으면 신경 쓰지 없습니다. 인터뷰를 예약 하는 동안 interviewer가 보내는 Live Share 세션에 대 한 링크만 있으면 전체 인터뷰를 수행 해야 합니다. 링크를 클릭 하면 필요한 모든 단계가 자동으로 수행 됩니다.

1. 인터뷰 시점에서 링크를 클릭 하 고 수행 하는 단계를 수행 합니다. 초기에 나 interviewer가 인터뷰에 늦을 경우 걱정 하지 마세요. Interviewer가 가입 될 때까지 기다리는 ' 로비 '에 있는 것입니다. 다른 단계는 필요 하지 않으며 interviewer 조인 하면 세션이 자동으로 시작 됩니다.

>[!NOTE]
>Interviewer 조인 되기 전이나 후에 세션의 연결을 끊은 경우 걱정 하지 마세요. 아직 닫혀 있지 않은 경우 해당 세션을 종료 하 고 같은 링크를 다시 클릭 합니다.

이제 인터뷰에 대해 Live Share를 사용 하 여 이동 하도록 설정 되었습니다. 
