---
title: Visual Studio Code를 사용하여 공동 작업 - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Code 및 Live Share에 대한 협업 방법 세트.
ms.custom: ''
ms.date: 09/16/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: fubaduba
ms.author: fubaduba
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: ff5dff3e6a88dba8e0d6f49c5bdcf52d1163ef1a
ms.sourcegitcommit: 6b1c502ba1763527aa69bad2e0c919d60a47153d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86300293"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>방법: Live Share를 사용 하 여 기술 인터뷰 수행

인터뷰를 위해 Live Share를 사용 하면 interviewer 및 후보가 전체 충실도 IDE 또는 편집기를 사용 하 여 빠르고 안정적인 인터뷰 세션을 수행할 수 있습니다. 이 자습서에서는 인터뷰 환경에 대해 [' 계획 된 세션 '](../reference/insiders.md) 및 [Live Share 웹 조인을](../quickstart/browser-join.md) 사용 하는 방법을 집중적으로 다룹니다. 

## <a name="setup-for-interviewer-vs-code"></a>Interviewer 설치 (VS Code)

[Visual Studio Code](../use/vscode.md) 를 설치 하 고 marketplace에서 [Live Share 확장 팩](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack) 을 다운로드 합니다. 확장 팩은 인터뷰를 위한 오디오 지원을 제공 합니다.

>[!TIP]
>VS Code에서 Live Share를 사용 하 여 인터뷰 하는 최상의 환경을 제공 하려면 Live Share 참가자 기능 플래그를 설정 해야 합니다. *기본 설정: UserSettings > 확장 > Visual Studio Live Share > 기능 집합: 참가자*

>[!NOTE]
> Live Share 채팅은 VS Code에서 Live Share 확장을 사용 하 여 빌드됩니다.

## <a name="scheduling-an-interview"></a>인터뷰 예약 

**VS Code Live Share** 는 Live Share 세션을 미리 만들 수 있는 기능을 제공 합니다. 다음 단계를 사용 하 여 세션을 미리 만들 수 있습니다.

### <a name="option-a-insider"></a>옵션 A (Insider)
1. 뷰 렛에서로 이동 하 여 `Planned Sessions` 새 세션을 만듭니다. 이제 사용자에 대 한 Live Share 세션을 미리 만들었습니다 .이 세션은 인터뷰 시점에 사용자가 사용할 수 있도록 합니다. 

![계획-세션-createlink](../media/planned-session-creation-vscode.PNG)


2. 뷰 렛에서 링크를 복사 하 여 후보로 보냅니다. 후보자에 게 보내는 링크를 사용 하 여 세션에 참가 하기 위해 인터뷰 시점에 사용할 수 있습니다.

![계획 된 세션-copylink](../media/planned-session-copylink-vscode.PNG)


### <a name="option-b-not-an-insider"></a>옵션 B (Insider 아님)

1. `Command Palette`사용 하 여 이동`Ctrl+Shift+P`
1. "라이브 Sha ..."를 입력 합니다. '_Live Share: 재사용 가능한 세션 링크 만들기_' 명령을 클릭 합니다.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. 그러면 재사용 가능한 세션이 생성 되 고이에 대 한 링크가 클립보드에 복사 됩니다. 편집기의 오른쪽 아래 모서리에 알림 팝업이 표시 됩니다.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. 링크를 보냅니다.

이 링크를 받은 후에는 전자 메일을 통해 interviewee 또는 예약 메커니즘을 선택 하 여 공유 하면 됩니다. 인터뷰 시점에 해당 링크를 클릭 하면 Live Share 세션에 있을 것입니다. 
> [!TIP] 
>재사용 가능한 세션 링크는 지속 되며, 만든 날짜 또는 마지막 사용 날짜 로부터 30 일 동안 지속 됩니다. 인터뷰에 대해 재사용 가능한 세션 링크를 생성 하는 동안 인터뷰는 링크를 만든 날짜의 30 일 이내에 있습니다. 링크가 만료 되 면 다시 사용할 수 있는 새 세션을 만듭니다. (링크가 만료 되지 않도록 할 수 있는 방법이 있지만이 방법은 인터뷰에 대 한 것이 더 쉽습니다.)

**참고:** 현재 Visual Studio의 Live Share에는 세션을 미리 만들 수 있는 기능이 없습니다. Visual Studio에서 Live Share를 사용 하 여 수행 하는 인터뷰의 경우 [여기](../quickstart/share.md) 에서 인스턴트 Live Share 세션을 시작 하는 방법에 대 한 가이드를 따르세요.



## <a name="setup-for-candidate"></a>후보 설치
후보는 항상 인터뷰에 참여 하기 위해 Visual Studio 또는 Visual Studio Code를 설치할 수 있지만 이렇게 할 필요는 없습니다. **Live Share 인터뷰 세션은 이전에 설치 하지 않고 후보에 의해 조인 될 수 있습니다.** 세션을 시작할 때 인터뷰 링크를 클릭 하 고 **브라우저에서 조인할**수 있습니다. 자세한 내용은 [여기를 참조 하세요.](../quickstart/browser-join.md)


<!--
### **What to do as an Interviewer?**

As an interviewer you will act as the host of the Live Share session. If you are not familiar with Live Share, we suggest you refer to the [share a project](../use/vscode.md) section of our how-to guide
### **What to do as the Interviewee?**

If you are expecting to do a Technical Interview using Live Share, you are in luck! We want to make sure you are familiar with the basic Live Share features so you feel comfortable during your interview.

1. Before the interview, take some time and look over the [How-to guide](../use/vscode.md) so you understand how Live Share works.

1. You may want to install Visual Studio Code beforehand so that you are not waiting for the installation to complete once you start your interview

1. If you don't have the time, no worries. All you need to have a full interview is the link to a Live Share session your interviewer sends you while scheduling the interview. Just clicking on the link will automatically take you through all the steps needed.

1. At the time of the interview, just click on the link and follow the steps it takes you through. If you are early or your interviewer is late to the interview, don't worry! You will just be in the 'lobby' waiting for your interviewer to join. No other steps are required, and once your interviewer joins the session will automatically start.

>[!NOTE]
>If you find that the session has disconnected before or after the interviewer joined, don't worry. Just exit out of that session if (it isn't already closed) and re-click on the same link!

You are now all set to go with using Live Share for your interview! 
-->
