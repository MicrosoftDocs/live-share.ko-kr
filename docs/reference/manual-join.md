---
title: 수동 조인-Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live에서 공동 작업 세션을 수동으로 조인에 대 한 정보를 공유 합니다.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 57d26c2c63bd5b92e62a72368f97bb8aee63313c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255937"
---
# <a name="join-a-session-manually"></a>세션을 수동으로 조인

공동 작업 세션에 참가할 브라우저에서 링크 열기, 하는 것 외에도 링크는 이미 실행 중인 도구에 붙여 넣어를 수동으로 조인할 수 있습니다. 이 일반적으로 보다 또는 어떤 이유로 작동에 대 한 초대 링크를 가져오는 중 문제가 발생 하는 경우 다른 도구를 사용 하려는 경우에 유용할 수 있습니다.

정확한 지시 달라질 [Visual Studio](#join-from-visual-studio) 및 [Visual Studio Code](#join-from-visual-studio-code), 자세한 내용은 사용 하려는 도구를 선택 합니다.

## <a name="join-from-visual-studio-code"></a>Visual Studio Code에서 조인

### <a name="1-sign-in"></a>1. 로그인

>**참고:** 읽기 전용 게스트로 공동 작업 세션에 참가 하려는 경우 로그인을 건너뛸 수 있습니다. 보기 및 공유 되는 코드를 탐색에 대 한 액세스는 했지만 편집할 수 없습니다.

![웹 브라우저를 사용 하 여 로그인 하 라는 알림](../media/vscode-sign-in-toast.png)

공동 작업을 수행 하기 위해 해야 로그인 Visual Studio Live Share에는 모든 사용자가 알 수 있도록 합니다. **클릭** "Live Share" 상태 표시줄 항목 또는 키를 누릅니다 **Ctrl + Shift + P / Cmd + Shift + P** 선택한는 "라이브 공유: 브라우저를 로그인"명령입니다.

![VS 코드 로그인 단추](../media/vscode-sign-in-button.png)

알림을 시작에 로그인 하 라는 메시지가 표시 되는 동안 브라우저가 시작 됩니다. 로그인 한 브라우저에서 프로세스를 완료 한 다음 수행 하는 경우 브라우저를 닫기만 합니다.

실행 하는 경우 VS Code를 사용 하 여 문제를 성공적으로 로그인를 가져오지 못함, 브라우저에서 성공 화면에서 "문제가" 링크를 클릭 하 고 지침을 따릅니다. 체크 아웃 [문제 해결](../troubleshooting.md#sign-in) 더 많은 팁입니다.

### <a name="2-use-the-join-command"></a>2. 조인 명령을 사용 하 여

VS Code 작업 표시줄에서 Live Share viewlet를 열고 "조인 공동 작업 세션..."를 선택 합니다. 아이콘 또는 항목입니다.

![조인 viewlet 아이콘](../media/vscode-join-viewlet.png)

>**참고:** 읽기 전용 guest로 조인 하는 경우 참가자를 세션에서 사용자를 식별 하는 데 표시 이름을 입력 하 라는 다음 나타납니다.

### <a name="3-paste-the-invite-link"></a>3. 초대 링크를 붙여 넣습니다.

보낸을 확인 하려면 ' Enter' 키를 눌러 초대 URL에 붙여 넣습니다.

정말 간단하죠. 하면 일시적으로 공동 작업 세션에 연결 되어야 합니다.

## <a name="join-from-visual-studio"></a>Visual Studio에서 연결

### <a name="1-sign-in"></a>1. 로그인

설치한 Visual Studio를 시작 하 고 아직 없는 경우 로그인 합니다. 보다 Visual Studio에 대 한 다른 로그인을 사용 해야 하는 경우에 [개인 설정 계정을](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)로 이동 하세요 **도구 &gt; 옵션 &gt; Live Share &gt; 사용자 계정**합니다.

![VS에 로그인](../media/vs-sign-in-button.png)

그래도 문제가 있나요? 참조 [문제 해결](../troubleshooting.md#sign-in)합니다.

### <a name="2-use-the-join-command"></a>2. 조인 명령을 사용 하 여

단순히 이동 **파일 > 공동 작업 세션 참가**합니다.

![VS 조인 메뉴](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. 초대 링크를 붙여 넣습니다.

보낸을 확인 하려면 ' Enter' 키를 눌러 초대 URL에 붙여 넣습니다.

정말 간단하죠. 하면 일시적으로 공동 작업 세션에 연결 되어야 합니다.

## <a name="see-also"></a>참고자료

빠른 시작

- [빠른 시작: 첫 번째 프로젝트를 공유 합니다.](../quickstart/share.md)
- [빠른 시작: 첫 번째 세션](../quickstart/join.md)

방법

- [방법: Visual Studio Code를 사용 하 여 공동 작업](../use/vscode.md)
- [방법: Visual Studio를 사용 하 여 공동 작업](../use/vs.md)
- [방법: 피드백 제공](../support.md)

참조

- [Live Share 연결 요구 사항](connectivity.md)
- [Live Share의 보안 기능](security.md)
- [Linux 설치 세부 정보](linux.md)
- [언어 및 플랫폼 지원](platform-support.md)
- [확장 지원](extensions.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
