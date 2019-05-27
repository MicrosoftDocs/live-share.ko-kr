---
title: FAQ-Visual Studio Live 공유 | Microsoft Docs
description: Visual Studio Live 공유에 대 한 질문과 대답입니다.
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
ms.openlocfilehash: 91ffc42c06e70839dbadbd2487cd02970ded3346
ms.sourcegitcommit: bfa1020882095fcc7d31cd71cf1f2e601e3bea06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2019
ms.locfileid: "66224707"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="frequently-asked-questions"></a>질문과 대답

## <a name="what-is-live-share"></a>Live Share 란?
Live Share를 사용하면 사용 중인 프로그래밍 언어나 빌드 중인 앱 유형에 관계 없이 다른 사람과 공동으로 실시간 편집 및 디버깅이 가능합니다. 즉시 (및 안전 하 게) 현재 프로젝트를 공유 하 고 필요에 따라 다음 디버깅 세션, 터미널 인스턴스, localhost web apps 등을 공유할 수 있습니다. 세션을 조인 하는 개발자가 효율적으로 공동 작업을 즉시 모든 리포지토리를 복제 하거나 모든 Sdk를 설치 하지 않고도 시작할 수 있도록 (예: 언어 서비스를 디버깅), 환경에서 모든 해당 편집기 컨텍스트를 받습니다.

## <a name="what-are-the-tooling-requirements-for-using-live-share"></a>Live Share를 사용 하기 위한 도구 요구 사항은 무엇입니까?
합니다 [기능을 핵심](#what-are-the-core-capabilities-of-live-share) Live Share의 완전히 지원 됩니다 다음 도구에서:

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [Visual Studio 2017 (15.6 이상)](https://visualstudio.microsoft.com/vs/older-downloads/)
* [Visual Studio Code](https://code.visualstudio.com/)

사용자 피드백에 응답할 신속 하 게 반복 합니다. 이렇게 하려면 Visual Studio 내에서 기능을 활용 하기 및만 Visual Studio Code가 각 미리 보기/insider 릴리스 사용 가능 합니다. 나타내고 귀하에 게 어떤 기능 설명서의 최신 버전의 VS 또는 VS Code에 필요 합니다. 예를 들어, 로컬 실행 취소/다시 실행 지원에는 Visual Studio 2017 15.7 + 필요합니다.

## <a name="what-are-the-core-capabilities-of-live-share"></a>Live Share의 핵심 기능은 무엇 인가요?
라이브 공유를 사용 하면 공유에 안전한 연결을 통해 팀 멤버를 사용 하 여 코드 베이스입니다. Live Share를 사용 하 여 공동으로 작업 영역에서 여러 파일을 편집할 수 있습니다 더 중요 한 응용 프로그램 및 디버그 팀 동료와 합니다. 공동 편집을 편집 하는 동안 즉시 표시 되 고 동료입니다. 공동 디버깅 하는 동안 응용 프로그램의 동일한 디버그 세션을 공유 합니다. 이 의미 하 고 동료는 중단점 및 단계를 사용 하 여 프로그램 실행을 제어할 수 있습니다 있지만 있습니다 독립적으로 검사할 수 없습니다 변수, 조사식, 지역 및 생산적인 (예: Visual Studio에서 직접 실행 창).

라이브 공유와 같은 다양 한 용도가지고: 함께 버그를 조사 다른 사람의 컴퓨터에서 재현 되지 않는 문제를 보여 주는 디자인 해결 문제, 프로그래밍, 인터뷰를 코딩, 멘토링 다른 팀 멤버 또는 수행을 수행 하는 쌍 임시 코드를 검토합니다.

## <a name="by-using-live-share-is-my-code-stored-on-a-microsoft-server"></a>Live Share를 사용 하 여 Microsoft 서버에 저장 된 코드는?
아니요, 공유 코드 공유를 시작 하는 개발자의 컴퓨터에만 상주 합니다. 저장 하거나 클라우드에 업로드 하 고 어떤 방식으로든에서 않습니다. 대신, Live Share 하기만 하면 됩니다 (즉, 암호화 된 엔드-투-엔드) 팀 멤버, 간에 보안 연결을 설정 및 검사 미치거나 공유 되는 코드에서 모든 데이터를 수집 합니다.

## <a name="does-this-remote-based-model-work-anywhere-is-it-peer-to-peer"></a>이 원격 기반 모델 어디서 든 작동 하나요? 피어-투-피어 입니까?
라이브 공유의 유일한 요구 사항은 공유 하는 사용자 및 해당 팀 동료는 각각 인터넷에 액세스할 수 있는 것입니다. 공동 작업 세션 중 팀 구성원 간에 보안 통신 Azure 릴레이 통해 쉽게 처리 됩니다. 작업 영역 (예: 소스 파일)는 클라우드에 저장 되지 않습니다. 특수 피어-투-피어 연결 없음 지연을 줄이기 위해 사용 될 수 있지만 필요 합니다. 참조 [연결 모드를 변경](https://aka.ms/vsls-docs/connection-mode) 에 대 한 자세한 문서.

## <a name="what-is-shared-during-a-live-share-session"></a>Live Share 세션 중 공유는 무엇입니까?
Live 공유 모든 키보드 및 마우스 입력을 전송 하지 않습니다. 또한 동료의 컴퓨터에 각 공동 작업에 필요한 데이터만 통신 합니다. 예를 들어, 작업 영역을 공유 하는 경우에 폴더 구조에 공유 됩니다. 공동으로 파일을 편집 하는 경우 해당 파일의 내용은 공유 됩니다. 협력을 디버깅 하는 경우 (예: 단계별 실행) 하는 디버그 작업 및 상태 (예: 호출 스택 및 지역) 공유 됩니다.

## <a name="when-will-live-share-be-released"></a>Live Share 나오나요?
라이브 공유 출시 되었습니다! 할 수 있습니다 [Live Share를 사용 하 여 시작](https://aka.ms/vsls-start) 지금 합니다.

## <a name="how-much-will-it-cost"></a>얼마나 비용은 얼마 입니까?
지속적으로 사용 하는 개발자를 위한 Visual Studio Live Share의 시키며 무료 계층을 위해 노력할 것입니다. 에서는 커뮤니티의 요구 사항을 더 잘 이해 하는 대로 고급 기능을 사용 하 여 유료 계층 도입을 평가 수는 있습니다.

## <a name="how-is-my-code-shared-with-other-teammates"></a>다른 팀 멤버를 사용 하 여 코드를 공유 하는 방법을
Live Share를 사용 하는 경우 팀원이 액세스할 수 있도록 해당 보안 클라우드 서비스를 통해 원격 명령을 해당 편집기에서 사용할 수 있는에서 작업 하는 코드를 수행 하면 됩니다. 동료를 열고 클라우드에 저장할 또는 영구적으로 팀 동료의 컴퓨터에 저장할 필요 없이 파일을 편집할 수 있습니다.

라이브 공유 프로젝트 트리, 코드 탐색 및 검색 등의 기능에 즉시 액세스할 수 있습니다. 또한 팀원이 IntelliSense와 같은 편집기 향상 기능을 활용할 수 있습니다.

## <a name="what-happens-if-a-user-goes-offline-or-stops-sharing"></a>사용자, 오프 라인 상태가 되거나 공유를 중지 하는 경우 어떻게 되나요?
원격 모델에 필요한 Live Share 및 해당 팀 동료를 통해 공유 하는 개발자를 연결할 온라인 이어야 합니다. 동료가 오프 라인 상태일 때 Live Share를 사용 하려고 하면 모두 다시 온라인 상태가 될 때까지 세션에 참가 하기 없게 됩니다는 합니다. 또한 공동 작업 중지 됩니다 (예: 프로그램 편집기를 닫고, 오프 라인으로 이동 또는 공유를 중지), 작업 또는 동료에 의해 파일 액세스 한 다음 추가 되 면 즉시 사용 하지 않습니다.

## <a name="what-about-screen-sharing"></a>화면 공유 어떻습니까?
라이브 공유를 사용 하면 프로젝트의 코드와 해당 컨텍스트를 공유할 수 있습니다. 동료가 수 쉽게 코드 베이스로 이동 및 친숙 한 도구를 사용 하 여 작업을 의미 합니다. 편집기 또는 다른 앱 공유 하거나 볼 수 있는 프로그램 팀 동료 하 여 않으며에 스타일을 변경 하거나 웹 기반 앱을 사용할 필요가 없습니다.

라이브 공유 화면 공유 수 하려는 메뉴 항목을 표시 하거나 앱 또는 편집기의 시각적 측면을 설명 하는 것을 대체 하지 않습니다. 대신, 채팅, 음성, 비디오 및 화면 공유와 함께 Live Share를 사용 하는 옵션을 해야 합니다.

## <a name="what-about-other-collaboration-tools"></a>다른 공동 작업 도구는 어떤가요?
라이브 공유 채팅, 인스턴트 메시징, 또는 전자 메일 기술을 사용할 수 있습니다. 개발자 간에 많은 공동 작업 상호 작용 이러한 도구에서 시작 하는 관찰 했습니다. 그러나 코드에 대 한 토론 때 자주 받게 경우 단순히 지점에 너무 텍스트, 코드 조각 또는 단일 파일을 사용 하 여 문제에 설명 하기 어려운 자세한 컨텍스트가 필요 합니다.

다양 한 작업 같은 라이브 공유를 사용할 있습니다: 코드 커밋 또는 끌어오기 요청을 하기 전에 프로그래밍, 코딩 인터뷰를 수행 하거나 수행 하는 임시 쌍 검토 버그를 해결 하는 문제에 대 한 도움말을 검색 합니다.

## <a name="what-about-other-web-editors"></a>다른 웹 편집기의 경우는 어떨까요?
웹 기반 편집기를 사용 하 여 두 팀원이 하지 않을 수 있는 일상적인 기본 편집기가 공동 작업 이점을 얻으려면 동일한 웹 앱을 사용 해야 합니다. 여러 웹 기반 편집기 빌드하고 클라우드 환경에서 호스팅되는 가상 컴퓨터에 배포를 가정 합니다.

대부분의 시나리오에 유용할 수 있습니다, 있지만 개발자 하려는 경우가 많습니다 공동 작업 앱 또는 클라우드 VM에서 호스트 되지 않습니다.  Live Share를 사용 하 여 하 고 동료가 웹 기반 편집기에서 사용할 수 있는 동일한 기능 외에 도구의 에코 시스템의 기능을 사용할 수 있습니다.

라이브 공유 단계에도 더 및 디버그 세션을 공유할 수 있습니다.  이렇게 하면 해당 개발 워크플로 변경 하거나 응용 프로그램 디자인을 변경할 필요 없이 컴퓨터에 발생 하는 문제를 추적할 수 있도록 다른 인 리스트 먼 트 하는 데 특히 유용 합니다.

## <a name="which-languages-and-platforms-will-be-supported"></a>어떤 언어 및 플랫폼 지원 되나요?
우리의 목표는 언어 및 플랫폼을 개발 중인 응용 프로그램 종류에 관계 없이 풍부한 공동 작업을 사용할 수 있도록 다양 한 분야를 지원 하기 위해서입니다. 참조 된 [언어 및 플랫폼 지원이](reference/platform-support.md) 문서를 현재 작동 하세요.

## <a name="how-many-developers-can-join-a-collaboration-session"></a>얼마나 많은 개발자는 공동 작업 세션에 참가할 수 있습니까?
현재 개발자 ("호스팅")를 공유 하는 것 외에도 30 동시 게스트 지원 프로젝트입니다. 

## <a name="what-is-the-roadmap"></a>로드맵은 무엇 인가요?
알려진된 문제 및 로드맵 항목 집합을 볼 수 있습니다 [여기](https://aka.ms/vsls-issues)합니다. 모든 문제 보다는 참조만 기능 요청을 원하는 경우 참조 [여기](https://aka.ms/vsls-feature-requests)합니다. 좋습니다 셰이프를 앞으로 이동 하는 제품의 방향을 투표 기존 항목, 새 기능 요청이 있는 경우 파일 및 버그 보고서를 고객에 게 로그 수 있습니다.

## <a name="see-also"></a>참고자료

- [언어 및 플랫폼 지원](platform-support.md)
- [Live Share 연결 요구 사항](reference/connectivity.md)
- [Live Share의 보안 기능](reference/security.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)

문제가 있으신가요? [문제 해결](troubleshooting.md)을 참조하거나 [피드백을 제공](support.md)해 주세요.
