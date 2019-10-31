---
title: 개요 - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share 및 해당 기능의 개요
ms.custom: ''
ms.date: 10/30/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: fubaduba
ms.author: fubaduba
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 8091a7ba5cf1f57f192ecea18da4473c8fdd99f7
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73179952"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->
# <a name="live-share-features-and-concepts"></a>Live Share 기능 및 개념 

Live Share은 사용자를 위한 강력한 기능으로 매니페스트 되는 혁신적인 아키텍처 및 개념을 사용 하 여 빌드됩니다. 아래에서는 Live Share의 모든 구별 기능을 제공 하 고 공동 작업 공간에서 리더를 만드는 방법을 알아봅니다. 

### <a name="collaboration-sessions"></a>협업 세션

Visual Studio Live Share에서 모든 협업 활동은 한 명의 **협업 세션 호스트**와 한 명 이상의 **게스트**로 구성됩니다. 호스트는 협업 세션을 시작한 사람이며 여기에 참가한 모든 사람은 게스트입니다.

협업 세션 호스트는 자신의 도구와 서비스를 모두 사용할 수 있지만 게스트는 호스트가 공유해 주는 특정 항목에만 액세스할 수 있습니다. 여기에는 코드, 실행 중인 서버, 디버깅 세션, 터미널 등이 포함됩니다. 현재 공유되는 모든 콘텐츠는 호스트의 머신에 유지되고 _즉시 액세스_ 및 _보안 강화_를 위해 클라우드나 게스트의 머신과 동기화되지 않습니다. 장점은 게스트가 참가한 순간 전체 솔루션을 사용할 수 있고 호스트가 협업 세션을 종료한 순간 콘텐츠를 더 이상 사용할 수 없다는 점입니다. 또한 게스트 성능 향상을 위해 IDE/편집기에서 생성한 임시 파일이 세션이 종료될 때 자동으로 정리됩니다.

#### <a name="sharing"></a>공유

호스트로 “공유”하면 프로젝트, 솔루션 또는 폴더 콘텐츠를 공유하는 협업 세션이 시작됩니다. 게스트는 호스트가 보낸 초대 링크를 사용하여 이 콘텐츠에 액세스합니다. “공유”는 “프로젝트 공유”의 줄임 표현이지만 디버깅과 같은 다른 기능 공유를 나타내기도 합니다.

**자세한 정보:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-project) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-project)

#### <a name="joining"></a>조인

호스트가 보낸 초대 링크를 클릭하면 게스트로 협업 세션에 “참가”할 수 있으며 호스트가 공유하도록 선택한 모든 콘텐츠 또는 기능에 액세스할 수 있습니다. 웹 링크를 통해 확장이 이미 설치된 경우 협업 세션에 신속하게 참가할 수 있으며 정보를 신속하게 설정(아직 설정되지 않은 경우)할 수 있습니다.

**자세한 정보:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#join-a-collaboration-session) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#join-a-collaboration-session)

### <a name="features"></a>기능

#### <a name="co-editing"></a>공동 편집

다른 협력자와 동일한 파일을 열면 즉시, 파일 콘텐츠를 “공동으로 편집” 또는 “공동 편집”할 수 있습니다. 각 협력자의 편집, 커서 및 선택 항목 등을 볼 수 있습니다. 게다가 항상 같은 파일을 편집하지 않아도 되므로 필요에 따라 기회를 보고 공동 작업하고 독립적으로 행동할 수 있습니다.

> [!NOTE]
> 공동 편집에는 몇 가지 제한 사항이 있습니다. 언어별 기능 상태는 [플랫폼 지원](../reference/platform-support.md)을 참조하세요.

**자세한 정보:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-editing) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-editing)

#### <a name="following-and-focusing"></a>따르기와 집중

경우에 따라 여러 파일 또는 코드의 위치에 걸쳐 있는 문제 또는 디자인을 설명해야 합니다. 이러한 상황에서는 공동 편집 시 동료가 프로젝트 전체를 이동하는 대로 동료를 일시적으로 따르는 것이 유용할 수 있습니다. 따라서 게스트로 협업 세션에 참가하면 호스트의 편집 위치를 자동으로 “따르게”하게 됩니다. 호스트와 게스트는 간단한 마우스 클릭으로 서로 따르기를 설정 및 해제할 수 있습니다. 또한 모든 참가자가 나를 따르도록 요청하고 싶을 수도 있습니다. Live Share를 사용하면 쉽게 주의를 끄는 알림을 통해 모든 사람이 나에게 주의를 “집중”하도록 요청할 수 있습니다.

**자세한 정보:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#following) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#following)

#### <a name="co-debugging"></a>공동 디버깅

까다로운 코딩 문제 또는 버그를 디버깅하는 경우 여러 사람의 검토가 정말 유용할 수 있습니다. 호스트로 Live Share를 사용하면 디버깅 세션을 모든 게스트와 공유하여 “공동 작업 디버깅” 또는 “공동 디버깅”이 가능합니다. 각각 공동 편집 기능과 더불어, 함께 진행하면서 개별적으로 조사하는 기능을 누릴 수 있습니다.

> [!NOTE]
> 언어별 또는 플랫폼별 디버깅 기능 상태는 [플랫폼 지원](../reference/platform-support.md)을 참조하세요.

**자세한 정보:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-debugging) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>서버 공유/포트 공유

공동 디버깅 시 호스트가 디버깅 세션을 위해 제공하는 애플리케이션의 서로 다른 부분을 액세스하는 것은 정말 유용할 수 있습니다. 브라우저에서 앱에 액세스하거나 로컬 데이터베이스에 액세스하거나 도구에서 REST 엔드포인트에 도달할 수 있습니다. Live Share를 사용하면 “서버를 공유”할 수 있으므로 호스트 머신의 로컬 포트를 각 게스트 머신의 정확히 동일한 포트에 매핑합니다. 게스트는 마치 머신에서 로컬로 실행 중인 것처럼 애플리케이션을 정확하게 조작할 수 있습니다(예를 들어 호스트와 게스트 모두 다음 위치에 실행 중인 웹앱에 액세스할 수 있음 http://localhost:3000).

**자세한 정보:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-server) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-server)

#### <a name="share-terminals"></a>터미널 공유

최신 개발 환경에서는 다양한 명령줄 도구를 자주 사용합니다. 다행스럽게도 Live Share는 호스트에게 필요에 따라 게스트와 “터미널을 공유”할 수 있는 기능을 제공합니다. 공유 터미널은 읽기 전용이거나 완전하게 공동 작업 가능하므로 호스트와 게스트는 모두 명령을 실행하고 그 결과를 볼 수 있습니다. 호스트는 다른 협력자가 명령을 직접 실행할 수 있는지, 단지 명령 출력만 보는지 항상 통제하고 결정할 수 있습니다. 사실, 자신만 알고 싶은 모든 사항은 공유되지 않는 터미널에서 실행하면 됩니다.

**자세한 정보:** [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-terminal) [![VS](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-terminal)

#### <a name="access-controls"></a>액세스 제어

Visual Studio Live Share는 참가자에게 공동 작업을 위한 여러 좋은 방법을 제공합니다. 그러나 게스트가 호스트와 상호 작용할 수 있는 다양한 옵션과 유연성으로, 게스트의 참가를 명시적으로 승인하거나 특정 파일 또는 폴더에 대한 액세스를 잠그고 싶을 수 있습니다. Live Share에는 읽기 전용을 비롯하여 게스트의 수락을 요구하는 등 이와 관련된 다양한 설정이 있습니다.

**자세한 정보:** [![VS Code](../media/vscode-icon-15x15.png)](../reference/security.md) [![VS](../media/vs-icon-15x15.png)](../reference/security.md)

#### <a name="flexible-connection-modes"></a>유연한 연결 모드

최적의 성능을 보장하기 위해 Visual Studio Live Share는 “직접” 및 “릴레이”라는 두 가지 핵심 “연결 모드”를 지원합니다. 직접 모드에서 게스트는 웹을 통하지 않고 호스트에 직접 연결합니다. 릴레이 모드에서는 완전히 다른 네트워크에 있는 게스트가 인터넷 릴레이를 통해 호스트에 연결할 수 있습니다. 모든 경우, 협력자만 인터넷을 통해 전송되는 내용에 액세스할 수 있도록 연결은 SSH 또는 SSL로 암호화됩니다. 기본적으로 Live Share는 “자동” 모드로, 먼저 직접 연결을 시도한 다음, 릴레이로 장애 조치(failover)하지만 원하는 경우 단일 모드로 잠글 수 있습니다.

**자세한 정보:** [![VS Code](../media/vscode-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode) [![VS](../media/vs-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode)
