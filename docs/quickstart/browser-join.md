---
title: 브라우저에서 조인-Visual Studio Live Share | Microsoft Docs
description: Thr 브라우저에서 조인 소개
ms.date: 03/18/2020
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: fishah
ms.author: fishah
manager: joncart
ms.workload:
- liveshare
ms.openlocfilehash: 741292a3df8b86a8f7a9484875b352ebe6e8ec10
ms.sourcegitcommit: 382f069abbd81ed258d497a974b30379be36b4f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79510638"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="preview-joining-a-live-share-session-from-the-browser"></a>✨ [Preview] ✨ 브라우저에서 Live Share 세션에 조인

이제 모든 Live Share 공동 작업 세션에서 브라우저의 형태로 조인할 수 있습니다. 이는 세션에 대 한 게스트가 더 이상 세션에 연결 하기 위해 VS Code 또는 Visual Studio를 설치할 필요가 없음을 의미 합니다. 이는 다른 사용자가 세션을 신속 하 게 하거나 데스크톱 클라이언트를 자주 설치 하지 않은 학생의 경우 이러한 모든 인스턴스에 유용 합니다.

> [!TIP]
> 브라우저에서 조인 하는 방법에 대 한 가장 일반적인 질문은 아래 FAQ 섹션을 참조 하세요.

# <a name="how-to-join-a-live-share-session-from-the-browser"></a>브라우저에서 Live Share 세션을 조인 하는 방법 

### <a name="1-host-starts-session"></a>1. 호스트: 세션 시작 
시작 하려면 호스트에서 Visual Studio 또는 VS Code로 이동 하 여 공동 작업 세션을 시작 해야 합니다. 호스트에서 폴더 또는 프로젝트를 공유 하는 경우

![시작 세션의 애니메이션](https://user-images.githubusercontent.com/51928518/76938928-b814e300-68b4-11ea-923e-cefabd4688c6.gif)

### <a name="2-guest-uses-shared-link-to-join-from-browser"></a>2. 게스트: 공유 링크를 사용 하 여 브라우저에서 조인 
Live Share는 게스트와 공유할 수 있는 조인 링크를 생성 합니다. 이제 게스트가이 링크를 사용 하 여 웹 페이지를 탐색할 수 있습니다. 그러면 브라우저를 계속 진행 하는 옵션이 제공 됩니다.

![세션에 대 한 조인 애니메이션](https://user-images.githubusercontent.com/51928518/76941137-b8af7880-68b8-11ea-8228-41fdf4afd3ef.gif)

### <a name="3-guest-enjoys-full-fidelity-collaboration-experience-from-browser"></a>3. 게스트: 브라우저에서 전체 충실도 공동 작업 환경 활용할 
게스트가 세션에 참여 한 후에는 데스크톱 클라이언트에서 공동 작업 하는 경우와 동일한 방식으로 작업을 수행할 수 있습니다.

![전체 충실도 애니메이션](https://user-images.githubusercontent.com/51928518/76942009-40e24d80-68ba-11ea-885c-6eb1069ed550.gif)
# <a name="frequently-asked-questions"></a>질문과 대답 

##### <a name="1-is-there-an-environment-running-in-the-background-that-is-hosting-my-session-in-the-browser"></a>1. 브라우저에서 세션을 호스팅하는 백그라운드에서 실행 중인 환경이 있나요?
브라우저에서 Live Share 세션에 연결 하는 경우 새 환경이 분리 되지 않습니다. 서버를 사용 하지 않는 서비스입니다. 
##### <a name="2-do-i-have-to-pay-for-the-service-of-joining-from-the-browser"></a>2. 브라우저에서 조인 하는 서비스에 대 한 요금을 지불 해야 하나요?
브라우저에서 조인은 모든 Live Share와 매우 유사 하 게 사용할 수 있습니다.

##### <a name="3-how-is-this-different-from-visual-studio-online"></a>3. Visual Studio Online과 어떻게 다른 가요?
브라우저에서 조인 하는 경우 세션 중에 브라우저에서 VS Code 클라이언트에만 액세스할 수 있습니다. 세션이 종료 되 면 편집기 기능과 함께 모든 파일 및 폴더가 닫힙니다. 사용자 고유의 환경을 사용 하 여 고유한 파일을 편집 하기 위해 브라우저에서 편집기를 사용 하려면 [Visual Studio Online](aka.ms/vso) 을 사용 해야 합니다.

##### <a name="4-does-this-work-for-all-browsers"></a>4. 모든 브라우저에서 작동 하나요?
예. 모든 브라우저에서 작동 합니다. 
##### <a name="5-is-there-a-vs-client-that-i-can-use-in-the-browser"></a>5. 브라우저에서 사용할 수 있는 VS 클라이언트가 있나요?
이를 아직 사용할 수 없습니다. 

# <a name="feedback-and-issues"></a>사용자 의견 및 문제 
이 기능은 미리 보기 기능으로, 사용자 의견을 보내 환경을 개선 하는 데 도움이 될 것입니다. 여기에서 GitHub 리포지토리에 표시 되는 의견이 나 문제를 입력 하세요 [.](https://github.com/MicrosoftDocs/live-share/issues/new?template=bug_report.md)