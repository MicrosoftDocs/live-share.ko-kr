---
title: 사용자 프로필 | Microsoft Docs
description: Visual Studio Live Share 사용자 프로필을 보고 제거 하는 방법에 대 한 개요입니다.
ms.custom: ''
ms.date: 05/222/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: c1c0363074c0737ae3aedb68952f3147e58cddb9
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870809"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>User Profile

Visual Studio Live Share를 사용 하 여 인증 하는 경우 사용자 프로필을 만듭니다 .이 프로필을 사용 하면 공동 작업 하는 참가자가 사용자의 사용자 (예: 전자 메일 주소, 아바타)를 확인할 수 있습니다. 지정 된 시간에 사용 하는 id 공급자에 따라 다음 페이지 중 하나로 이동 하 여 Live Share 사용자를 대신 하 여 저장 한 프로필 정보를 볼 수 있습니다.

- [Microsoft 계정/Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

이 페이지에서는 id를 확인 하기 위해 로그인 하 라는 메시지가 표시 되 고 사용자 프로필에 대 한 원시 JSON 출력이 표시 됩니다.

<img width="500px" src="media/user-profile.png" />

Visual Studio Live Share 현재 로그인 한 id에 대해 저장 된 프로필이 없는 경우에도이를 확인할 수 있습니다.

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>프로필 제거

사용자 프로필을 제거 하려면 `Delete your account` [사용자 프로필 페이지](#user-profile)에서 단추를 클릭 하면 됩니다. 그렇지 않으면 마지막으로 성공한 로그인 이후 30 일 동안 프로필이 자동으로 삭제 됩니다 Visual Studio Live Share. 이 컨텍스트에서 "성공적인 로그인"은 사용 중인 도구에 따라 다음을 나타냅니다.

| IDE/편집기 | 사용자 프로필은 마지막으로 30 일 후에 삭제 됩니다. |
|-|-|
| Visual Studio | IDE의 새 인스턴스를 시작 합니다. Single Sign-On를 지원 하기 위해 Visual Studio의 새 인스턴스를 열 때마다 Visual Studio Live Share 인증 세션을 새로 고칩니다. |
| Visual Studio Code | 브라우저 기반 인증 워크플로를 완료 합니다 (예: 단추를 클릭 `Sign In` 하거나 명령을 실행 `Live Share: Sign in with browser` ). 을 (를) 공유할 때마다 로그인 할 필요가 없도록 클라이언트에서 인증 세션을 Visual Studio Live Share 합니다. 그러나이 세션은 30 일 후에 만료 되며, 브라우저를 통해 명시적으로 로그인 할 때까지 자동으로 새로 고쳐지지 않습니다. |

## <a name="see-also"></a>추가 정보

- [언어 및 플랫폼 지원](reference/platform-support.md)
- [Live Share 연결 요구 사항](reference/connectivity.md)
- [Live Share의 보안 기능](reference/security.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)

문제가 있으신가요? [문제 해결](troubleshooting.md)을 참조하거나 [피드백을 제공](support.md)해 주세요.
