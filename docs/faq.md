---
title: FAQ | Microsoft Docs
description: Visual Studio Live Share에 대 한 질문과 대답입니다.
ms.custom: ''
ms.date: 05/05/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 3da327261766ea0aea7ed167059c864100d25da0
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870490"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="frequently-asked-questions"></a>질문과 대답

## <a name="what-is-live-share"></a>Live Share 이란?
Live Share를 사용하면 사용 중인 프로그래밍 언어나 빌드 중인 앱 유형에 관계 없이 다른 사람과 공동으로 실시간 편집 및 디버깅이 가능합니다. 이를 통해 현재 프로젝트를 즉시 (및 안전 하 게) 공유할 수 있으며, 필요한 경우 디버깅 세션, 터미널 인스턴스, localhost 웹 앱 등을 공유할 수 있습니다. 세션을 조인 하는 개발자는 사용자 환경 (예: 언어 서비스, 디버깅)에서 모든 편집기 컨텍스트를 수신 하 여 리포지토리를 복제 하거나 Sdk를 설치 하지 않고도 생산적인 공동 작업을 즉시 시작할 수 있도록 합니다.

## <a name="what-are-the-tooling-requirements-for-using-live-share"></a>Live Share 사용을 위한 도구 요구 사항은 무엇 인가요?
Live Share의 [핵심 기능은](#what-are-the-core-capabilities-of-live-share) 다음 도구에서 완벽 하 게 지원 됩니다.

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [Visual Studio 2017 (15.6 +)](https://visualstudio.microsoft.com/vs/older-downloads/)
* [Visual Studio Code](https://code.visualstudio.com/)

사용자 피드백에 응답 하기 위해 신속 하 게 반복 합니다. 이렇게 하려면 Visual Studio 내의 기능을 활용 하 고 해당 하는 미리 보기/참가자 릴리스부터만 제공 되는 Visual Studio Code 합니다. 설명서에서 최신 버전의 VS 또는 VS Code를 필요로 하는 기능을 표시 합니다. 예를 들어 로컬 실행 취소/다시 실행 지원에는 Visual Studio 2017 15.7 +가 필요 합니다.

## <a name="what-are-the-core-capabilities-of-live-share"></a>Live Share의 핵심 기능은 무엇 인가요?
Live Share를 사용 하면 보안 연결을 통해 코드 베이스를 팀 멤버와 공유할 수 있습니다. Live Share를 사용 하면 작업 영역에서 여러 파일을 공동 편집할 수 있으며, 팀 동료와 응용 프로그램을 디버그 하는 것이 더 중요 합니다. 공동 편집 중에는 동료 들이 편집 내용을 즉시 볼 수 있습니다. 공동 디버깅 중에는 응용 프로그램의 동일한 디버그 세션을 공유 합니다. 즉, 사용자와 동료가 중단점 및 단계를 사용 하 여 프로그램 실행을 제어할 수 있지만 변수, 조사식, 지역 및 REPLs를 독립적으로 검사할 수 있습니다 (예: Visual Studio의 직접 실행 창).

Live Share에는 버그 조사, 다른 사용자의 컴퓨터에서 재현 하지 않는 문제 표시, 디자인 문제 해결, 코드 쌍 사용, 코딩 인터뷰 수행, 팀의 다른 멤버 멘토링 또는 임시 코드 검토 수행 등의 다양 한 사용 사례가 있습니다.

## <a name="by-using-live-share-is-my-code-stored-on-a-microsoft-server"></a>Live Share를 사용 하 여 내 코드가 Microsoft 서버에 저장 되나요?
아니요, 공유 코드는 공유를 시작한 개발자의 컴퓨터에만 상주 합니다. 어떤 방식으로든 클라우드에 저장 되거나 업로드 되지 않습니다. 대신, Live Share은 사용자와 사용자의 팀 (종단 간 암호화) 간에 보안 연결을 설정 하 고 공유 되는 코드에서 데이터를 검사 하거나 수집 하지 않습니다.

## <a name="does-this-remote-based-model-work-anywhere-is-it-peer-to-peer"></a>이 원격 기반 모델이 어디에서 작동 하나요? 피어 투 피어 입니까?
Live Share의 유일한 요구 사항은 공유 및 해당 동료가 각각 인터넷에 액세스할 수 있어야 한다는 것입니다. 공동 작업 세션 중에 팀 멤버 간의 보안 통신은 Azure relay에서 촉진 합니다. 작업 영역 (즉, 원본 파일)은 클라우드에 저장 되지 않습니다. 대기 시간을 줄이기 위해 하나를 사용할 수 있지만 특별 한 피어 투 피어 연결은 필요 하지 않습니다. 자세한 내용은 문서에서 [연결 모드 변경](https://aka.ms/vsls-docs/connection-mode) 을 참조 하세요.

## <a name="what-is-shared-during-a-live-share-session"></a>Live Share 세션 중에 공유 되는 항목
Live Share은 모든 키보드 및 마우스 입력을 전송 하지 않습니다. 각 공동 작업에 필요한 데이터만 동료의 컴퓨터에 전달 합니다. 예를 들어 작업 영역을 공유 하면 폴더 구조가 공유 됩니다. 공동으로 파일을 편집 하는 경우 해당 파일의 내용이 공유 됩니다. 공동 디버깅 하는 경우 디버그 작업 (예: 단계별 실행) 및 상태 (예: 호출 스택 및 지역)가 공유 됩니다.

## <a name="when-will-live-share-be-released"></a>언제 Live Share 언제 출시 되나요?
Live Share 이제 일반 공급 됩니다. 지금 [Live Share를 시작할](https://aka.ms/vsls-start) 수 있습니다.

## <a name="how-much-will-it-cost"></a>비용은 얼마인가요?
Microsoft는 개발자가 지속적으로 사용할 수 있는 Visual Studio Live Share의 시키며 관리가 무료 계층으로 최선을 다하고 있습니다. 커뮤니티의 요구 사항을 더 잘 이해할 수 있으므로 고급 기능이 포함 된 유료 계층의 도입을 평가할 예정입니다.

## <a name="how-is-my-code-shared-with-other-teammates"></a>내 코드는 다른 동료와 어떻게 공유 되나요?
Live Share를 사용 하는 경우 코드를 사용 하 여 작업 중인 코드를 사용 하 여 사용자가 편집기에서 명령을 원격으로 실행 하는 보안 클라우드 서비스를 통해 팀에 액세스할 수 있습니다. 동료가 클라우드에 저장 하거나 팀의 컴퓨터에 영구적으로 저장할 필요 없이 파일을 열고 편집할 수 있습니다.

Live Share를 사용 하면 프로젝트 트리, 코드 탐색 및 검색과 같은 기능에 즉시 액세스할 수 있습니다. 또한 팀 동료가 IntelliSense와 같은 편집기의 향상 된 기능을 이용할 수 있습니다.

## <a name="what-happens-if-a-user-goes-offline-or-stops-sharing"></a>사용자가 오프 라인으로 전환 되거나 공유를 중지 하는 경우 어떻게 되나요?
원격 모델을 사용 하려면 Live Share를 통한 개발자 공유와 해당 동료가 온라인 상태 여야 연결 해야 합니다. 사용자가 오프 라인 상태일 때 Live Share를 사용 하려고 하면 다시 온라인 상태가 될 때까지 세션에 참여할 수 없습니다. 또한, 공동 작업이 중지 되 면 (예: 편집기를 닫거나 오프 라인으로 전환 하거나 공유를 중지 하는 경우) 팀 동료의 추가 작업 또는 파일 액세스를 즉시 사용할 수 없게 됩니다.

## <a name="what-about-screen-sharing"></a>화면 공유는 어떻습니까?
Live Share를 사용 하 여 프로젝트의 코드와 해당 컨텍스트를 공유할 수 있습니다. 즉, 아군 동료가 친숙 한 도구를 사용 하 여 코드 베이스로 쉽게 이동 하 고 작업을 수행할 수 있습니다. 사용자의 편집자 또는 다른 앱은 사용자의 동료가 공유 하거나 볼 수 없으며, 작업 스타일을 변경 하거나 웹 기반 앱을 사용할 필요가 없습니다.

Live Share는 메뉴 항목을 표시 하거나 앱 또는 편집기의 시각적 측면을 논의할 수 있는 화면 공유를 대체 하지 않습니다. 대신 채팅, 음성, 비디오 및 화면 공유와 함께 Live Share를 사용 하는 옵션이 있습니다.

## <a name="what-about-other-collaboration-tools"></a>다른 공동 작업 도구는 어떻게 되나요?
Live Share은 채팅, 인스턴트 메시징 또는 전자 메일 기술에 사용할 수 있습니다. 개발자 간의 많은 공동 작업 상호 작용은 이러한 도구에서 시작 하는 것으로 나타났습니다. 그러나 코드에 대해 설명 하는 경우에는 대개 텍스트, 코드 조각 또는 단일 파일에 대 한 문제를 설명 하는 데 너무 어려운 점이 있을 수 있습니다. 더 많은 컨텍스트가 필요 합니다.

Live Share는 문제에 대 한 도움말 검색, 버그 해결, 쌍 프로그래밍, 코딩 인터뷰 수행, 코드 커밋 또는 풀 요청 전 임시 검토 수행 등의 여러 가지 작업에 사용할 수 있습니다.

## <a name="what-about-other-web-editors"></a>다른 웹 편집기는 어떻게 되나요?
웹 기반 편집기를 사용 하는 경우 두 팀이 모두 동일한 웹 앱을 사용 하 여 공동 작업 혜택을 받아야 합니다 .이는 기본, 일상적인 편집기 일 수 없습니다. 대부분의 웹 기반 편집기는 클라우드 환경에서 호스트 되는 가상 머신으로 빌드 및 배포 하는 것으로 가정 합니다.

이는 많은 시나리오에 적합할 수 있지만 개발자는 VM 또는 클라우드에서 호스트 되지 않는 앱에서 공동 작업을 하려는 경우가 많습니다.  Live Share을 통해 사용자와 사용자의 동료가 웹 기반 편집기에서 제공 하는 것과 동일한 기능을 사용할 수 있을 뿐만 아니라 도구 에코 시스템의 기능을 사용할 수 있습니다.

Live Share 단계로 이동 하 여 디버그 세션을 공유할 수 있습니다.  이렇게 하면 개발 워크플로를 변경 하거나 응용 프로그램 디자인을 변경 하지 않고도 컴퓨터에서 발생 하는 문제를 추적 하는 데 도움이 되는 다른 사용자를 참여 시킬 때 특히 유용 합니다.

## <a name="which-languages-and-platforms-will-be-supported"></a>지원 되는 언어 및 플랫폼은 무엇 인가요?
Microsoft의 목표는 개발 중인 응용 프로그램 종류에 관계 없이 풍부한 공동 작업을 수행할 수 있도록 다양 한 언어 및 플랫폼을 지 원하는 것입니다. 현재 작동 하는 항목에 대 한 자세한 내용은 [언어 및 플랫폼 지원](reference/platform-support.md) 문서를 참조 하세요.

## <a name="how-many-developers-can-join-a-collaboration-session"></a>공동 작업 세션에 참여할 수 있는 개발자는 몇 개입니까?
현재는 프로젝트 ("호스팅")를 공유 하는 개발자 외에도 30 개의 동시 게스트를 지원 합니다. 

## <a name="what-is-the-roadmap"></a>로드맵 이란?
알려진 문제 집합 및 [로드맵 항목을 볼 수 있습니다.](https://aka.ms/vsls-issues) 모든 문제가 아닌 기능 요청만 보려면 [여기](https://aka.ms/vsls-feature-requests)를 참조 하세요. 제품의 방향을 파악 하는 데 도움이 되도록 기존 항목을 사전 투표 하 고 새로운 기능 요청을 기록 하 고 버그 보고서를 기록 하는 것이 좋습니다.

## <a name="see-also"></a>추가 정보

- [언어 및 플랫폼 지원](platform-support.md)
- [Live Share 연결 요구 사항](reference/connectivity.md)
- [Live Share의 보안 기능](reference/security.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)

문제가 있으신가요? [문제 해결](troubleshooting.md)을 참조하거나 [피드백을 제공](support.md)해 주세요.
