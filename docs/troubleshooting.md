---
title: 문제 해결-Visual Studio Live 공유 | Microsoft Docs
description: Visual Studio Live 공유에 대 한 팁과 요령을 해결 합니다.
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
ms.openlocfilehash: 5fc611714d148a9ba1d5a6848e0399af753d1a37
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640213"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>Visual Studio Live 공유 문제 해결

이 문서에서는 문제 해결 팁, 해결 방법 및 일반적인 문제 및 질문에 대 한 답변에 설명 합니다. 살펴봅니다 수도 합니다 [FAQ](faq.md)합니다. 

## <a name="installation--tool-requirements"></a>설치 / 도구 요구 사항

다음은 문제 해결 Visual Studio Live Share 설치와 관련 된 팁입니다.

| 도구 | 문제점 | 해결 방법 / 해결 방법 |
|------|---------|------------|
| VS | 확장 설치 관리자 <strong>버전의 Visual Studio를 찾을 수 없습니다</strong> Visual Studio Live Share 확장을 설치할 때 사용 하도록 합니다. | Visual Studio Live Share 필요 **Visual Studio 2017 버전 15.6** 호스트와 게스트 모두에 대 한 이상. 안정적인 최신 설치 [Visual Studio 2017의 업데이트](https://visualstudio.com/vs/) 을 다시 시도 하세요.|
| VS Code | MacOS에서 VS Code를 사용 하 여 Visual Studio Live Share를 사용 하려고 하면 오류가 나타납니다 <strong>El Capitan 이하로</strong>합니다. | Visual Studio Live Share의 OS 지원.NET Core에 종속 되는 현재 [macOS Sierra 지 원하는 이상.]((https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).) |
| VS Code | "**종속성을 설치할 수 없습니다**" 오류가 나타납니다 while 확장이 **설치를 완료 하** 첫 번째 시작에 대 한 오류가 발생할 **없거나 이미 파일**. | 확인에 **양호한 네트워크 연결**합니다. 인 경우 있습니다 실행 될 수에 **프록시 또는 방화벽** 문제입니다. 참조 [연결 문제 해결](#connectivity)합니다. <br /><br />|
| VS Code | Marketplace에서 Visual Studio Live Share 확장을 설치 <strong>VS Code의 stable/참가자 버전에서 설치</strong> 원하는 버전을 대신 합니다. | VS Code 안정화 또는 기본 설정에 따라 참가자 시작, "extensions" 탭을 클릭 하, "Visual Studio Live Share"를 검색 하 고 여기에서 설치 합니다. |
| VS Code (**Linux**) | Live Share 확장을 활성화 하지 않습니다 하 고 **상태 표시줄 항목이 표시** 에서 확장을 설치한 후 **Linux**합니다. | Visual Studio Live Share Linux 필수 구성 요소가 기본적으로 특정 Linux 배포는에서 충족 되지 않을 수 있습니다 수 있는.NET Core 2.0에 따라 달라 집니다. 참조 [대 한 자세한 내용은 여기](reference/linux.md#install-linux-prerequisites) 에서 무엇을 설치 해야 합니다. |

## <a name="sign-in"></a>로그인

다음은 문제 해결 로그인 문제에 대 한 팁입니다.

| 도구 | 문제점 | 해결 방법 / 해결 방법 |
|------|---------|------------|
| VS | Visual Studio Live Share 사용 하 여 로그인 해야는 <strong>다른 id</strong> Visual Studio에 로그인 하는 데 사용할 수 있습니다. | 도구 > 옵션 > Live Share > 사용자 계정을 대체 계정을 선택 합니다. |
| VS Code | 브라우저 창 팝업에서 로그인 하는 동안 및 프로세스 동안 <strong>웹 페이지에 성공한 것으로 나타납니다</strong>, 상태 표시줄 <strong>여전히 라는 "로그인"</strong> 브라우저를 닫은 후 합니다. | 로그인 한 후 "데 문제가 있나요?"를 클릭 및 도구에는 임시 사용자 코드를 입력 하도록 지시를 따릅니다.<br /><br />의견도 기다리고 어떤 발생할 수 있습니다, 되므로 보려는 하세요 [버그 기록](https://aka.ms/vsls-problem)합니다. |
| 모두 | 발생 하는 한 <strong>시간 초과 또는 연결 오류</strong>합니다. | 참조 [연결 문제 해결](#connectivity)합니다. |
| 모두 | Microsoft를 사용 하 여 로그인이 지 원하는 **회사 또는 학교 전자 메일 주소** 라는 메시지가 표시 **"관리자 승인 필요"** 합니다. | Azure AD 원칙은 사용자 설치 디렉터리의 내용에 액세스 하는 새 응용 프로그램에 대 한 "관리자 동의" 할 것입니다. 참조 [여기](reference/security.md) 대 한 자세한 내용은 합니다. |
| VS Code (**macOS**) | 서명가 없다는 오류를 참조 하면 **실패 한 SecKeychainAddGenericPassword()** 합니다. | 이것이 거의 항상 macOS 사용 하 여 일반적인 문제로 인해 로그인 키 집합에서 암호 변경 내용이 반영 되지 않습니다. "키 집합 액세스"로 이동, 로그인 키 집합 잠금 및 다음 다시 잠금 해제를 시도 합니다. 이 문제를 해결 하지만 현재 암호를 사용 하 여 잠금 해제할 수 없는 경우 이전에 하나를 시도 하기에 충분 수 있습니다. 작동 하는 경우를 현재 암호로 로그인 키 집합 암호를 변경 합니다. 참조 [여기](https://support.apple.com/en-us/HT201609) 세부 정보에 대 한 합니다. |
| VS Code (**Linux**) | 브라우저를 통해 로그인 한 후 사용자 코드에서 입력할 때 오류 메시지가 표시 **secret_password_store_sync() 실패 했습니다. 오류 코드: XX**합니다. | 이 일반적으로 인해 `gnome-keyring` 및/또는 `libsecret-1-0` /  `libsecret` 설치 되지 않습니다. Gnome-인증 키를 확인할 수 있습니다를 설치 하 여 올바르게 구성 되어 `seahorse` 다음 "암호 및 키" 응용 프로그램을 사용 하 여 데스크톱 환경의 합니다. 에 대해 자세히 알아보세요 [Linux 필수 구성 요소 여기](reference/linux.md#install-linux-prerequisites)합니다. |
| VS Code (**Linux**) | 하려는 <strong>사용자 코드를 입력 하 라는 메시지가 표시</strong> v0.3.295 Live Share를 사용 하 여 또는 아래 않지만 브라우저 없음 확보할 수 있도록 표시 됩니다. | Linux에서 사용자 코드 요구 사항을 제거 하는 중입니다. 평균 시간, 브라우저 창을 사용 하 여 로그인 할 나타납니다. 그렇지 않은 경우 브라우저 창 VS Code 숨겨져 있을 수 있습니다. 없는 경우 다음 팁을 참조 하세요.  |
| VS Code | "로그인"을 클릭 한 후 (또는 사용 하 여는 "라이브 공유: 로그인"명령)을 <strong>브라우저 창이 표시 되지 않게 사용자의 자격 증명을 입력할 수 있도록</strong>입니다. | 1. [여기에 로그인 합니다.](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2. 로그인 한 후 "데 문제가 있나요?"를 클릭<br /> 3. 도구에는 임시 사용자 코드를 입력 하도록 지시를 따릅니다. |
| 모두 | 하려는 <strong>조인</strong> 공동 작업 세션</strong> 되지만 <strong>하지 않은 / 전자 메일 업데이트를 수신 하지 않으려는</strong>합니다. | VS/VS Code에서 Live Share 확장에 로그인 <strong>되지</strong> 전자 메일 업데이트 수신을 옵트인 있습니다.<br /><br />라이브 공유 게스트가 호스트에 가입한 하는 id로 표시 되므로 보안 조치로 로그인 하려면 필요 합니다. [이 기능을 긍정적](https://github.com/MicrosoftDocs/live-share/issues/3) 익명 사용자가 가입 하도록 허용 하는 옵션 수행 하려는 경우 (예: 사용자 이름이 없는 사용자 정의 이름 /). |

## <a name="share-and-join"></a>공유 및 조인

다음은 문제 해결 로그인 문제에 대 한 팁입니다.

| 도구 | 문제점 | 해결 방법 / 해결 방법 |
|------|----------------|------------|
| 모두 | <strong>공유/조인 합니다.</strong> 제한 시간 또는 연결할 수 없다는 오류가 발생 하는 합니다. | 참조 [연결 문제 해결](#connectivity)합니다. |
| VS Code | <strong>조인 합니다.</strong> 했습니다 <strong>메시지 표시 / VS Code를 시작할 수 없는</strong> 브라우저에서 조인 페이지를 연 후 합니다. |  팁: <ul><li>하면 해야 <i>VS Code를 최소 한 번 시작 및 설치 상태 표시줄의 완료를 대기 합니다.</i></li><li>작동 하지 않는 경우 실행 된 "Live 공유: 시작 관리자 Setup"명령입니다.</li><li>**Linux 사용자**: 위의 명령을 실행할 때 관리자 (sudo) 암호를 입력 하 라는 메시지가 나타나면 그렇게 해 주세요.</li><li>마지막으로, 참조 [수동으로 조인](reference/manual-join.md) 문제를 해결 합니다.</li></ul> 이 문제에 도달 하면 새로운 발생할 수 있습니다, 되므로 참조 일원이 하세요 [버그를 기록해](https://aka.ms/vsls-new-issue)합니다. |
| VS | <strong>조인 합니다.</strong> 했습니다 <strong>메시지 표시 / VS 실행할 수 없는</strong>  브라우저에서 조인 페이지를 연 후 합니다. |  [수동으로 참가](reference/manual-join.md)를 참조하세요.<br /><br /> 의견도 기다리고 있으므로 로그를 보려면 하세요 [버그 기록](https://aka.ms/vsls-problem) Visual Studio의 "보고서는 문제..."를 사용 하 여 기능입니다. |
| 모두 | <strong>조인 합니다.</strong> 하려는 <strong>Visual Studio에서 참가 링크를 직접 붙여 VS Code /</strong> 대신 웹 링크를 클릭 합니다. | [수동으로 참가](reference/manual-join.md)를 참조하세요. |
| 모두 | <strong>조인 합니다.</strong> 라는 메시지가 표시 "**오프 라인 상태가 될 것 같습니다. 작업 영역의 소유자**," 브라우저를 통해 조인 하는 경우. | 가능한 해결 방법:<br /><ul><li>시도 [수동으로 조인](reference/manual-join.md)합니다. 지역 간 문제가 살펴본 (동부 및 서 부 예: 미국) 수동 조인 하는 데 영향을 미치지 않는 서비스 문제로 인해 조인 합니다.</li><li>라이브 공유 "auto" 연결 모드로 실행 될 때 호스트에 직접 라우팅하 못할 수 있습니다. 시도 [릴레이 모드](reference/connectivity.md)합니다.</li></ul>참조 [연결 문제 해결](#connectivity) 많은 가능성 |
| VS Code | <strong>조인 합니다.</strong> 브라우저를 통해 조인 <strong>에 로그인 하기 전에</strong>에 로그인 하 라는 메시지가 표시 되지 않았습니다</strong>, 및 조인을 완료 되지 않습니다. |  이 [알려진된 버그가](https://github.com/MicrosoftDocs/live-share/issues/167)합니다. 로그인 한 후에 다시 참가 상태 표시줄 항목에 있는 기호를 클릭 합니다. |

## <a name="connectivity"></a>연결

아래 정보를 공유 하거나 조인 또는 관련 된 연결 제한 시간에 로그인 할 때 문제가 발생 하면 문제를 해결 하면 도움이 됩니다.

에 설명 된 대로 [Live 공유에 대 한 연결 요구 사항을](reference/connectivity.md) 문서에서는 다양 한 연결 모드 요구 사항이 서로 다 다른 몇 가지 잠재적인 문제가 진행 되므로 작동 합니다.

| 도구 | 문제점 | 가능한 원인 |
|------|------|----------------|
| 모두 | 사용 하는 한 <strong>프록시</strong> 다양 한 연결 문제가 표시 되 고 | 프록시 설정을 까다로울 수 있습니다.  설정 합니다 **HTTP_PROXY** 및 **HTTPS_PROXY** 환경 변수 **전역적으로** 다음 도구를 다시 시작 해야 합니다. 참조 [프록시 설정을](reference/connectivity.md#proxies) 대 한 자세한 내용은 합니다. 일부 구성에서는 아직 지원 하지 않습니다, 가능성이 있으므로 [알려주세요](https://github.com/MicrosoftDocs/live-share/issues/86) 이를 작동 하지 않는 경우. |
| VS Code | 가져오기 확장을 설치 하 고 VS Code를 처음 시작 후는 <strong>"설치 완료" 상태 표시줄에 표시 되 면 오류가</strong>합니다. |  Download.visualstudio.microsoft.com에 대 한 액세스를 인터넷에 액세스할 수 없습니다 및/또는 포트 443에서 download.microsoft.com 개인 또는 회사 방화벽에 의해 차단 됩니다. 참조 [여기](https://github.com/MicrosoftDocs/live-share/issues/58) 이유에 대 한 내용은 Live Share이 시점에서 다운로드 해야 합니다. |
| 모두 | <strong>Visual Studio Live Share에 로그인 할 수 없습니다.</strong> | 인터넷에 액세스 하거나에 액세스할 수 없습니다 *. liveshare.vsengsaas.visualstudio.com 80/443 포트에서 개인 또는 회사 방화벽에 의해 차단 됩니다. 입력 https://insiders.liveshare.vsengsaas.visualstudio.com 브라우저에서 Visual Studio Live Share 홈 페이지에서 배치를 확인 합니다. |
| 모두 | 본인이 <strong>auto 모드</strong> (기본값), 로그인 하지만 참조 수를 <strong>시간 초과 또는 연결 오류</strong> 공유 또는 조인 하는 경우. | 하거나 둘 다 직접 및 연결에 실패 하는 모드 이거나 auto 모드를 사용 하 여 버그를 릴레이 합니다. 한 후 연결할 수 있는지 [직접 전환 또는 릴레이 모드](reference/connectivity.md#changing-the-connection-mode)하세요 [버그 발생](https://aka.ms/vsls-problem)합니다. |
| 모두 | 본인이 <strong>직접 모드</strong>, 로그인 하지만 참조 수를 <strong>시간 초과 또는 연결 오류</strong> 공유 또는 조인 하는 경우. | 게스트 및 호스트를 직접 연결할 수 없습니다. 시도 [auto 또는 릴레이 모드](reference/connectivity.md#changing-the-connection-mode) 문제가 사라집니다으로 실행 하는 경우를 확인 합니다. 해야 할 수 있습니다 [개인 방화벽을 통해 Live Share를 수동으로 허용할](reference/connectivity.md#manually-adding-a-firewall-entry) 또는 릴레이 모드를 사용 하면 됩니다. |
| 모두 | 본인이 <strong>릴레이 모드</strong>, 로그인 할 수 있지만 사용자에 게 알립니다를 <strong>시간 초과 또는 연결 오류</strong> 공유 또는 조인 하는 경우. | 에 대 한 액세스 *. servicebus.windows.net 80/443 포트에서 차단 된 개인 또는 회사 방화벽에 의해 차단 됩니다. 시도 [직접 모드](reference/connectivity.md#changing-the-connection-mode)합니다. |

참조 된 [Live 공유에 대 한 연결 요구 사항을](reference/connectivity.md) 연결 요구 사항에 대 한 자세한 내용은 문서.

## <a name="see-also"></a>참고자료

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

여전히 문제가 있나요? 할 수 있습니다 [의견](support.md)합니다.
