---
title: 수동 조인-Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live share에서 수동으로 공동 작업 세션을 조인 하는 방법에 대 한 정보입니다.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 1057c6276302fb0df682798dd06684b4835c051e
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170123"
---
# <a name="join-a-session-manually"></a>수동으로 세션 조인

브라우저에서 링크를 열어 공동 작업 세션에 참여 하는 것 외에도 이미 실행 중인 도구에 링크를 붙여넣어 수동으로 조인할 수 있습니다. 이는 일반적으로 수행 하는 것과 다른 도구를 사용 하려는 경우 나 어떤 이유로 든 초대 링크를 가져오는 데 문제가 있는 경우에 유용할 수 있습니다.

정확한 지침은 [Visual Studio](#join-from-visual-studio) 와 [Visual Studio Code](#join-from-visual-studio-code)에 따라 다르며, 자세한 정보를 얻기 위해 사용할 도구를 선택 합니다.

## <a name="join-from-visual-studio-code"></a>Visual Studio Code에서 조인

### <a name="1-sign-in"></a>1. 로그인

>**참고:** 공동 작업 세션을 읽기 전용 게스트로 조인 하려면 로그인을 건너뛸 수 있습니다. 공유 되는 코드를 보고 탐색할 수는 있지만 편집할 수는 없습니다.

![웹 브라우저를 사용하여 로그인하라는 알림 메시지](../media/vscode-sign-in-toast.png)

공동 작업을 수행하려면 모든 사람이 사용자의 신원을 알도록 Visual Studio Live Share에 로그인해야 합니다. "Live Share" 상태 표시줄 항목을 **클릭** 하거나 **ctrl + shift + p/Cmd + shift + P** 를 누르고 "Live Share: 브라우저를 사용 하 여 로그인" 명령을 선택 합니다.

![VS Code 로그인 단추](../media/vscode-sign-in-button.png)

로그인을 요청 하는 알림이 표시 되는 동안 브라우저가 시작 됩니다. 브라우저에서 로그인 프로세스를 완료한 다음, 완료될 때 브라우저를 닫기만 하면 됩니다.

성공적인 로그인을 선택 하지 VS Code에 문제가 발생 하는 경우 브라우저의 성공 화면에서 "문제 발생" 링크를 클릭 하 고 지침을 따릅니다. 자세한 팁은 [문제 해결](../troubleshooting.md#sign-in) 을 확인 하세요.

### <a name="2-use-the-join-command"></a>2. 조인 명령을 사용 합니다.

VS Code 활동 표시줄에서 Live Share 뷰 렛을 열고 "공동 작업 세션 참여 ..."를 선택 합니다. 아이콘 또는 항목입니다.

![viewlet 참가 아이콘](../media/vscode-join-viewlet.png)

>**참고:** 읽기 전용 게스트로 조인 하는 경우 참가자가 세션에서 사용자를 식별 하는 데 도움이 되는 표시 이름을 입력 하 라는 메시지가 표시 됩니다.

### <a name="3-paste-the-invite-link"></a>3. 초대 링크 붙여넣기

보낸 초대 URL을 붙여넣은 다음 ' Enter ' 키를 눌러 확인 합니다.

정말 간단하죠. 일시적으로 협업 세션에 연결되어야 합니다.

## <a name="join-from-visual-studio"></a>Visual Studio에서 조인

### <a name="1-sign-in"></a>1. 로그인

설치 되 면 Visual Studio를 시작 하 고 아직 로그인 하지 않았으면 로그인 합니다. [개인 설정 계정](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)보다 Visual Studio에 대 한 다른 로그인을 사용 해야 하는 경우 **도구 &gt; 옵션 &gt; Live Share &gt; 사용자 계정**으로 이동 합니다.

![VS 로그인](../media/vs-sign-in-button.png)

그래도 문제가 있나요? [문제 해결](../troubleshooting.md#sign-in)을 참조 하세요.

### <a name="2-use-the-join-command"></a>2. 조인 명령을 사용 합니다.

**파일 > 참여 공동 작업 세션**으로 이동 하기만 하면 됩니다.

![VS 참가 메뉴](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. 초대 링크 붙여넣기

보낸 초대 URL을 붙여넣은 다음 ' Enter ' 키를 눌러 확인 합니다.

정말 간단하죠. 일시적으로 협업 세션에 연결되어야 합니다.

## <a name="see-also"></a>참조

퀵 스타트

- [빠른 시작: 첫 번째 프로젝트 공유](../quickstart/share.md)
- [빠른 시작: 첫 번째 세션 참여](../quickstart/join.md)

방법

- [방법: Visual Studio Code를 사용 하 여 공동 작업](../how-to-guides/vscode.md)
- [방법: Visual Studio를 사용 하 여 공동 작업](../how-to-guides/vs.md)
- [방법: 피드백 제공](../support.md)

참고

- [Live Share 연결 요구 사항](connectivity.md)
- [Live Share의 보안 기능](security.md)
- [Linux 설치 세부 정보](linux.md)
- [언어 및 플랫폼 지원](platform-support.md)
- [확장 지원](extensions.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
