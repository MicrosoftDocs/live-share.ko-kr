---
title: 문제 해결 | Microsoft Docs
description: Visual Studio Live Share에 대 한 문제 해결 팁 및 요령.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: troubleshooting
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 692e129252ac92c159660842b62a45fe4f7db864
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870852"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>문제 해결 Visual Studio Live Share

이 문서에서는 일반적인 문제 및 질문에 대 한 문제 해결 팁, 해결 방법 및 답변을 다룹니다. [FAQ](faq.md)를 살펴볼 수도 있습니다. 

## <a name="installation--tool-requirements"></a>설치/도구 요구 사항

다음은 Visual Studio Live Share 설치와 관련 된 문제 해결 팁입니다.

| 도구 | 문제 | 해결 방법/해결 방법 |
|------|---------|------------|
|VS Code <strong>(Macos)</strong>| <strong>Macos가 .Net Core에서 더 이상 지원 되지 않음을 알리는 경고가 나타납니다.<strong>| 이 경고는 [.Net Core에서](https://docs.microsoft.com/en-us/dotnet/core/install/dependencies?tabs=netcore31&pivots=os-macos) 이전 버전을 더 이상 지원 하지 않는 <strong>(10.13 +)</strong> 이전 버전을 더 이상 지원 하지 않는 최신 업데이트 때문에 나타납니다. Live Share 확장을 사용 하도록 설정 하려면 OS를 업데이트 하세요.
| VS | 확장 설치 관리자에서 Visual Studio Live Share 확장을 설치 하려고 할 때 사용할 <strong>Visual Studio 버전을 찾을 수 없습니다</strong> . | Visual Studio Live Share 호스트와 게스트 모두에 대해 **Visual Studio 2017 버전 15.6** 이상이 필요 합니다. [Visual Studio 2017의](https://visualstudio.com/vs/) 최신 안정적인 업데이트를 설치 하 고 다시 시도 합니다. |
| VS 코드 | "**종속성을 설치할 수** 없습니다." 오류는 처음 시작할 때 확장이 **설치를 완료** 하는 동안 또는 **누락 되었거나 이미 존재** 하는 파일에 대 한 오류가 발생 하는 경우에 나타납니다. | **네트워크 연결이 양호한** 지 확인 합니다. 인 경우 **프록시 또는 방화벽** 문제를 실행 하 고 있을 수 있습니다. [연결 문제 해결](#connectivity)을 참조 하세요. <br /><br />|
| VS 코드 | Marketplace에서 Visual Studio Live Share 확장을 설치 하면 원하는 버전 대신 <strong>VS Code의 안정적/참가자 버전으로 설치</strong> 됩니다. | 기본 설정에 따라 안정화 또는 참가자를 시작 VS Code "확장" 탭을 클릭 하 고 "Visual Studio Live Share"를 검색 한 후 여기에서 설치 합니다. |
| VS Code (**Linux**) | **Linux** 에 확장을 설치한 후에는 Live Share 확장이 활성화 되지 않고 **상태 표시줄 항목이 표시 되지** 않습니다. | Visual Studio Live Share는 기본적으로 Linux의 특정 배포판에서 충족 되지 않을 수 있는 다양 한 Linux 필수 구성 요소를 포함 하는 .NET Core 2.0에 종속 됩니다. 설치 해야 하는 항목에 대 [한 자세한 내용은 여기를](reference/linux.md#install-linux-prerequisites) 참조 하세요. |

## <a name="sign-in"></a>로그인

다음은 로그인 문제에 대 한 문제 해결 팁입니다.

| 도구 | 문제 | 해결 방법/해결 방법 |
|------|---------|------------|
| VS | Visual Studio에 로그인 하는 데 사용 하는 것과 <strong>다른 id</strong> 를 사용 하 여 Visual Studio Live Share에 로그인 해야 합니다. | 도구 > 옵션 > Live Share > 사용자 계정으로 이동 하 여 대체 계정을 선택 합니다. |
| VS 코드 | 로그인 하는 동안 브라우저 창이 <strong>표시 되 고 프로세스가 성공적으로 웹 페이지에 표시 되</strong>는 동안 브라우저를 닫은 후에도 상태 표시줄에 <strong>"로그인" 이라는 메시지가</strong> 표시 됩니다. | 로그인 한 후에 "문제가 있나요?"를 클릭 합니다. 지침에 따라 도구에 임시 사용자 코드를 입력 합니다.<br /><br />또한 문제가 발생 한 것을 확인할 수 있으므로 [버그를 기록](https://aka.ms/vsls-problem)하세요. |
| 모두 | <strong>시간 초과 또는 연결 오류가 발생</strong>합니다. | [연결 문제 해결](#connectivity)을 참조 하세요. |
| 모두 | Microsoft에서 지원 되는 **회사 또는 학교 전자 메일 주소** 를 사용 하 여 로그인 할 때 **"관리자 승인 필요"** 라는 메시지가 표시 됩니다. | Azure AD 개념는 디렉터리의 콘텐츠에 액세스 하는 새 응용 프로그램에 "관리자 동의"를 요구 하도록 설정 되어 있습니다. 자세한 내용은 [여기](reference/security.md)를 참조하세요. |
| VS Code (**Macos**) | 로그인 할 때 **SecKeychainAddGenericPassword ()가 실패** 했음을 나타내는 오류가 표시 됩니다. | 이는 암호 변경이 로그인 키 집합에 반영 되지 않는 macOS와 관련 된 일반적인 문제 때문에 거의 항상 발생 합니다. "키 집합 액세스"로 이동 하 여 로그인 키 집합을 잠그고 다시 잠금 해제 해 보세요. 이 경우 문제를 해결 하기에 충분 한 것일 수 있지만 현재 암호를 사용 하 여 잠금을 해제할 수 없는 경우 이전 항목을 사용해 보세요. 작동 하는 경우 로그인 키 집합 암호를 현재 암호로 변경 합니다. 자세한 내용은 [여기](https://support.apple.com/en-us/HT201609)를 참조하세요. |
| VS Code (**Linux**) | 브라우저를 통해 로그인 한 후 사용자 코드에 입력 하면 **오류 코드 XX와 함께 secret_password_store_sync ()이 실패** 했음을 나타내는 오류가 표시 됩니다. | 이는 일반적으로 `gnome-keyring` 및/또는 설치 하지 않기 때문에 발생 `libsecret-1-0` /  `libsecret` 합니다. `seahorse`데스크톱 환경에서 "암호 및 키" 응용 프로그램을 설치 하 고 사용 하 여 gnome가 올바르게 구성 되었는지 확인할 수 있습니다. [Linux 필수 구성 요소](reference/linux.md#install-linux-prerequisites)에 대 한 자세한 내용은 여기를 참조 하세요. |
| VS Code (**Linux**) | Live Share v 0.3.295이 하를 사용 하 <strong>는 사용자 코드를 입력 하 라는 메시지가</strong> 표시 되지만 브라우저가 표시 되지 않습니다. | Linux에서 사용자 코드 요구 사항을 제거 하기 위해 노력 하 고 있습니다. 사용자가 로그인 하는 데 사용할 수 있는 평균 시간에 브라우저 창이 표시 됩니다. 그렇지 않으면 VS Code에서 브라우저 창이 숨겨질 수 있습니다. 이 경우 다음 팁을 참조 하세요.  |
| VS 코드 | "로그인"을 클릭 하거나 "Live Share: 로그인" 명령을 사용 하 여 <strong>자격 증명을 입력할 수 있는 브라우저 창이 표시 되지 않습니다</strong>. | 1. [여기에 로그인](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2. 로그인 한 후에 "문제 발생"을 클릭 합니다.<br /> 3. 지침에 따라 도구에 임시 사용자 코드를 입력 합니다. |
| 모두 | 공동 작업 세션에 <strong>참여</strong> 하려고 </strong> 하지만 <strong>전자 메일 업데이트를 수신 하지는 않으려고</strong>합니다. | VS/VS Code에서 Live Share 확장에 로그인 하면 전자 메일 업데이트를 받을 수 <strong>없습니다</strong> .<br /><br />Live Share에는 게스트가 조인 된 id에 대 한 가시성을 갖도록 보안 조치로 로그인 해야 합니다. [이 기능](https://github.com/MicrosoftDocs/live-share/issues/3) 을 사용 하는 경우 익명 사용자가 가입 하도록 허용 하는 옵션 (예: 이름/사용자 정의 이름이 없는 사용자)을 선택 합니다. |

## <a name="share-and-join"></a>공유 및 조인

다음은 로그인 문제에 대 한 문제 해결 팁입니다.

| 도구 | 문제 | 해결 방법/해결 방법 |
|------|----------------|------------|
| 모두 | <strong>공유/조인:</strong> 연결할 수 없는 시간 초과 또는 오류가 발생 합니다. | [연결 문제 해결](#connectivity)을 참조 하세요. |
| VS 코드 | <strong>조인:</strong> 브라우저에서 조인 페이지를 연 후에 <strong>VS Code를 시작할 수 있는 메시지가 표시 되지</strong> 않았습니다. |  팁: <ul><li><i>VS Code를 한 번 이상 시작 하 고 상태 표시줄에서 설치가 완료</i> 될 때까지 대기 해야 합니다.</li><li>작동 하지 않는 경우 "Live Share: 시작 관리자 설치" 명령을 실행 해 보세요.</li><li>**Linux 사용자**: 위의 명령을 실행 하는 동안 관리자 (sudo) 암호를 입력 하 라는 메시지가 표시 되 면이를 수행 하십시오.</li><li>마지막으로, 해결 방법으로 [수동으로 조인](reference/manual-join.md) 을 참조 하세요.</li></ul> 이 문제가 발생 하는 경우 발생 하는 상황을 확인 하 여 [버그를 기록](https://aka.ms/vsls-new-issue)하세요. |
| VS | <strong>조인:</strong> 브라우저에서 조인 페이지를 연 후에는 <strong>메시지를 표시 하지 않고 VS를 시작할 수 없습니다 </strong> . |  [수동으로 참가](reference/manual-join.md)를 참조하세요.<br /><br /> 로그를 볼 수도 있으므로 Visual Studio의 "문제 보고 ..."를 사용 하 여 [버그를 기록](https://aka.ms/vsls-problem) 하세요. 기능과. |
| 모두 | <strong>조인:</strong> 웹 링크를 클릭 하는 대신 <strong>Visual Studio/VS Code에 직접 조인 링크를 붙여 넣는</strong> 것이 좋습니다. | [수동으로 참가](reference/manual-join.md)를 참조하세요. |
| 모두 | <strong>조인:</strong> 브라우저를 통해 조인할 때 "**작업 영역의 소유자가 오프 라인** 으로 표시 됩니다." 라는 메시지가 표시 됩니다. | 가능한 해결 방법:<br /><ul><li>[수동으로 조인](reference/manual-join.md)해 보세요. 수동 조인에 영향을 주지 않는 서비스 문제로 인해 지역 간 (예: 동부 및 미국 서 부) 조인에 문제가 있습니다.</li><li>"자동" 연결 모드에서 실행 하는 경우 Live Share 호스트에 직접 라우팅할 수 없습니다. [릴레이 모드](reference/connectivity.md)를 시도 합니다.</li></ul>더 가능성은 [연결 문제 해결](#connectivity) 을 참조 하세요. |
| VS 코드 | <strong>조인:</strong> 로그인 <strong>하기 전에</strong>브라우저를 통해 조인한 경우 로그인 하 라는 메시지가 표시 되지 않고 </strong> 조인이 완료 되지 않습니다. |  이것은 [알려진 버그](https://github.com/MicrosoftDocs/live-share/issues/167)입니다. 로그인 상태 표시줄 항목을 클릭 하 여 로그인 한 다음 다시 조인 합니다. |

## <a name="connectivity"></a>연결

아래 정보는 로그인, 공유 또는 가입할 때 연결 또는 시간 제한과 관련 된 문제가 있는 경우 문제를 해결 하는 데 도움이 됩니다.

[Live Share에 대 한 연결 요구 사항](reference/connectivity.md) 문서에 설명 된 것 처럼 다양 한 연결 모드의 요구 사항이 서로 다르기 때문에 몇 가지 문제가 발생할 수 있습니다.

| 도구 | 문제 | 가능한 원인 |
|------|------|----------------|
| 모두 | <strong>프록시</strong> 를 사용 하 고 있으며 연결 문제가 많이 발생 하 고 있습니다. | 프록시 설정은 복잡할 수 있습니다.  **HTTP_PROXY** 및 **HTTPS_PROXY** 환경 변수를 **전역적** 으로 설정 하 고 도구를 다시 시작 하십시오. 자세한 내용은 [프록시 설정](reference/connectivity.md#proxies) 을 참조 하세요. 아직 지원 하지 않는 몇 가지 구성이 있을 수 있으므로이 문제가 해결 되지 [않으면 알려주세요.](https://github.com/MicrosoftDocs/live-share/issues/86) |
| VS 코드 | 확장을 설치 하 고 처음으로 VS Code를 시작 하 고 나면 <strong>상태 표시줄에 "설치 완료"가 표시 되 면 오류가</strong>발생 합니다. |  인터넷에 액세스할 수 없거나 포트 443에서 download.visualstudio.microsoft.com 및/또는 download.microsoft.com에 대 한 액세스 권한이 개인 또는 회사 방화벽에 의해 차단 되었습니다. 이 시점에서 Live Share를 다운로드 해야 하는 이유에 대 한 자세한 내용은 [여기](https://github.com/MicrosoftDocs/live-share/issues/58) 를 참조 하세요. |
| 모두 | <strong>Visual Studio Live Share에 로그인 할 수 없습니다.</strong> | 인터넷에 액세스할 수 없거나 포트 80/443의 *. liveshare.vsengsaas.visualstudio.com에 대 한 액세스가 개인 또는 회사 방화벽에 의해 차단 되었습니다. 브라우저에서를 입력 하 https://insiders.liveshare.vsengsaas.visualstudio.com 고 Visual Studio Live Share 홈페이지를 확인 합니다. |
| 모두 | <strong>자동 모드</strong> (기본값) 이지만, 로그인 할 수 있지만 공유 하거나 조인할 때 <strong>시간 제한 또는 연결 오류가</strong> 표시 됩니다. | 직접 및 릴레이 모드 모두 연결에 실패 하거나 auto 모드를 사용 하는 버그가 있습니다. [직접 또는 릴레이 모드로 전환한](reference/connectivity.md#changing-the-connection-mode)후에 연결할 수 있는 경우 [버그를 발생 시킵니다](https://aka.ms/vsls-problem). |
| 모두 | <strong>직접 모드</strong>에 있지만, 로그인 할 수는 있지만 공유 하거나 조인할 때 <strong>시간 제한 또는 연결 오류가</strong> 표시 됩니다. | 게스트와 호스트는 직접 연결할 수 없습니다. [자동 또는 릴레이 모드](reference/connectivity.md#changing-the-connection-mode) 를 시도 하 여 문제가 발생 하지 않는 경우를 확인 합니다. [수동으로 개인 방화벽을 통해 Live Share을 허용](reference/connectivity.md#manually-adding-a-firewall-entry) 하거나 릴레이 모드를 사용 해야 할 수 있습니다. |
| 모두 | <strong>릴레이 모드</strong>에 있지만, 로그인 할 수는 있지만 공유 하거나 조인할 때 <strong>시간 제한 또는 연결 오류</strong> 에 대 한 알림이 표시 됩니다. | 포트 80/443에서 *. servicebus.windows.net에 대 한 액세스가 차단 되었습니다. 개인 또는 회사 방화벽에 의해 차단 됩니다. [직접 모드](reference/connectivity.md#changing-the-connection-mode)를 시도 하세요. |

연결 요구 사항에 대 한 자세한 내용은 [Live Share의 연결 요구 사항](reference/connectivity.md) 문서를 참조 하세요.

## <a name="see-also"></a>추가 정보

빠른 시작

- [첫 번째 프로젝트 공유](quickstart/share.md)
- [첫 번째 세션 참가](quickstart/join.md)

방법

- [Visual Studio Code를 사용하여 공동 작업](use/vscode.md)
- [Visual Studio를 사용하여 공동 작업](use/vs.md)

참조

- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)
- [Live Share 연결 요구 사항](reference/connectivity.md)
- [Linux 설치 세부 정보](reference/linux.md)
- [언어 및 플랫폼 지원](reference/platform-support.md)
- [확장 지원](reference/extensions.md)

그래도 문제가 있나요? [사용자 의견을 제공할](support.md)수 있습니다.
