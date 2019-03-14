---
title: 사용자 프로필-Visual Studio Live 공유 | Microsoft Docs
description: 개요 보기 및 Visual Studio Live Share 사용자 프로필을 제거 하는 방법입니다.
ms.custom: ''
ms.date: 05/222/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 7ef7c48b94222969409a0f26111e2b9b99efddc5
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255858"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>사용자 프로필

Visual Studio Live Share를 사용 하 여 인증할 때 해당 사용자 프로필을 생성 하면 모든 참가자는 참조를 사용 하 여 공동 작업을 허용 하는 (예: 전자 메일 주소, 아바타). 지정된 된 시간에 Live Share (사용 하는 id 공급자)에 따라 다음 페이지 중 하나로 이동 하 여 저장 사용자 대신 프로필 정보를 볼 수 있습니다.

- [Microsoft Account / Azure Active Directory](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

페이지에 로그인 하 여 id를 확인 하도록 요청 되며 그런 다음 사용자 프로필에 대 한 원시 JSON 출력을 표시 합니다.

<img width="500px" src="media/user-profile.png" />

Visual Studio Live Share 현재 로그인 된 id에 대해 저장 된 프로필에 없는 경우 다음이 알 수 있습니다는 합니다.

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>프로필 제거

사용자 프로필을 제거 하려는 경우 클릭할 수 이라는 링크가 `Click here to get your data removed from our systems` 에 [사용자 프로필 페이지](#user-profile)합니다. 또는 직접 (에 따라 사용 하는 id 공급자) 다음 페이지 중 하나를 방문할 수 있습니다.

- [Microsoft Account / Azure Active Directory](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/deleteme)
- [GitHub](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/github/deleteme)

그렇지 않은 경우 Visual Studio Live Share는 자동으로 삭제 프로필 마지막 성공적인 로그인 후 30 일. 이 컨텍스트에서 "로그인" 다음을 나타냅니다 (에 따라 사용 중인 도구):

| I/편집기 | 사용자 프로필은 마지막으로 후 30 일 동안 삭제할 수 있습니다... |
|-|-|
| Visual Studio | IDE의 새 인스턴스를 시작 합니다. Single sign on을 지원 하기 위해 Visual Studio Live Share를 Visual Studio의 새 인스턴스를 열 때마다 인증 세션을 새로 고칩니다. |
| Visual Studio Code | 브라우저 기반 인증 워크플로가 완료 되는 (예:을 클릭 하는 `Sign In` 단추 또는 실행을 `Live Share: Sign in with browser` 명령). Visual Studio Live Share 로그인에 공유 될 때마다 필요 하지 않도록 하려면 클라이언트에서 인증 세션에 저장 됩니다. 그러나 해당 세션 30 일 후 만료 되 고 자동으로 새로 고쳐지면 명시적 로그인 하면 브라우저를 통해 다시까지. |

## <a name="see-also"></a>참고자료

- [언어 및 플랫폼 지원](reference/platform-support.md)
- [Live Share 연결 요구 사항](reference/connectivity.md)
- [Live Share의 보안 기능](reference/security.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)

문제가 있으신가요? [문제 해결](troubleshooting.md)을 참조하거나 [피드백을 제공](support.md)해 주세요.
