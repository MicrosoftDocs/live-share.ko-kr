---
title: 연결-Visual Studio Live 공유 | Microsoft Docs
description: Visual Studio Live 공유에 대 한 연결 및 연결 모드에 대 한 정보.
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
ms.openlocfilehash: 6edc5bcf18dde6f84a4972a1efd755592cbef18c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256423"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Live Share 연결 요구 사항

이 문서에서는 Visual Studio Live Share, 사용 가능한 연결 옵션 및 해당 하는 경우 알려진된 해결 방법에 대 한 연결 요구 사항을 요약 합니다.

## <a name="sign-in"></a>로그인

Live Share를 사용 하 여 로그인 할 수 있습니다 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory) 백업된 작업 또는 학교 계정에는 [Microsoft 계정](https://account.microsoft.com/account), 또는 [GitHub 프로필](https://github.com/)합니다. 일반적으로 로그인 Url에 대 한 이러한 사용할 수 있지만 경우 not, 공용 연결 제품의 수를 지정 하는 대부분의 조직에서 열기를 열고 네트워크 관리자에 게 문의 `login.microsoftonline.com` 및/또는 `github.com` 도메인외에도[아래에 나열 된](#requirements-for-connection-modes)합니다.

> [!NOTE]
> 온-프레미스 AD (ADFS) 계정 및 온-프레미스 GitHub Enterprise 계정을 현재 지원 되지 않습니다 [(투표 👍)](https://github.com/MicrosoftDocs/live-share/issues/341)합니다.

## <a name="connection-modes"></a>연결 모드

최적의 되도록 성능, Visual Studio Live Share 기본적으로 자동으로 검색 하는지 여부를 공동 작업 세션 호스트 컴퓨터 및 게스트 컴퓨터를 네트워크를 통해 직접 통신할 수 있습니다만 서로 경로가 있는 경우 클라우드를 통해 릴레이 합니다. 이 혼합 된 "auto" 모드는 유연 하며 다른 사용자가 동일한 세션에 대 한 직접 연결 하는 동안 일부 게스트 릴레이에 클라우드를 통해 수도 있습니다.

직접 연결 보안을 보장 하지만 5990 5999 사이의 포트 연결을 사용할 수 있도록 열어야 요구 하는 클라우드 기반 메커니즘을 통해 인증 됩니다. 결과적으로, 라는 메시지가 표시 될 처음 공유 데스크톱 방화벽 포트를 엽니다. 이 선택적으로 무시 수락 항상 자동 모드에서 릴레이 사용 하도록 Live Share 단순히 발생 합니다.

모든 Visual Studio Live Share의 연결은 공동 작업 세션의 개체만 해당 내용에 대 한 액세스 권한을 획득할 수 있도록 SSH 또는 SSL 암호화 하 고 중앙 집중식 서비스를 인증 합니다. 또한 Live Share 클라우드 릴레이 라우팅된 모든 트래픽을 유지 되지 않습니다 및 않습니다 하지 "스 눕" 어떤 방식으로 트래픽을 합니다.

## <a name="changing-the-connection-mode"></a>연결 모드를 변경합니다.

직접 또는 릴레이 된 연결을 사용 하지 않도록 설정 하려는 하거나 단순히 연결 문제를 해결할 경우 다른 연결 모드를 강제할 수 있습니다.

| 모드 | 호스트 동작 | 게스트 동작 |
|------|----------------|----------------------|
| 자동 | 호스트의 공동 작업 세션 보안, 인증 된 직접 연결 또는 클라우드 릴레이 된 연결을 허용합니다. | 직접 연결을 사용 하 고이 작업이 실패 하면 클라우드를 통해 릴레이를 대체 합니다. |
| 직접 | 호스트의 공동 작업 세션 인증, 보안 직접 연결만 허용 합니다. | 직접 연결을 사용 하려고 시도 하 고 연결할 수 없는 경우 중지 합니다. |
| Relay | 호스트의 공동 작업 세션의 직접 연결을 허용 하지 않습니다. 포트가 없는 호스트의 컴퓨터에서 열려 있습니다. | 항상 클라우드를 통해 연결합니다. |

모드를 변경 합니다.

**VS:**

1. 도구 > 옵션 > Live 공유 합니다.
2. "연결 모드" 드롭다운 목록에서 모드를 선택 합니다.
3. VS를 다시 시작 합니다.

**VS Code:**

1. Settings.json 편집 (파일 > 기본 설정 > 설정).
2. 설정 `"liveshare.connectionMode"` 하 `"auto"`를 `"direct"`, 또는 `"relay"` 기본 설정에 따라 합니다.
3. VS Code를 다시 시작 합니다.

## <a name="requirements-for-connection-modes"></a>연결 모드에 대 한 요구 사항

특정 포트 및 Live 공유에 대 한 함수를 사용할 수 있어야 하는 Url에는 연결 모드를 따라 결정 됩니다.

| 모드 | 클라이언트 액세스 요구 사항 | 문제 해결 |
|------|--------------|-----------------|
| 임의의 값 | 에 대 한 아웃 바운드 액세스 `*.liveshare.vsengsaas.visualstudio.com:443` | 확인 회사 또는 개인 네트워크 방화벽을 사용 하면이 도메인에 연결할 수 있습니다. 입력 https://insiders.liveshare.vsengsaas.visualstudio.com 브라우저에서 Visual Studio Live Share 홈 페이지에서 배치를 확인 합니다. 에 실행 중일 수 있습니다 [프록시 문제](#proxies) 는 해결 해야 합니다.|
| 모든 (VS Code) | 에 대 한 아웃 바운드 액세스 `download.microsoft.com:443` | 확인 회사 또는 개인 네트워크 방화벽을 사용 하면이 도메인에 연결할 수 있습니다. 에 실행 중일 수 있습니다 [프록시 문제](#proxies) 는 해결 해야 합니다. |
| 자동 | 자동-전환 합니다. 릴레이 모드 및 직접 참조 합니다. | 직접 또는 릴레이 문제를 해결 하는 모드를 전환 합니다. |
| 직접 | 호스트의 경우: 포트에 인바운드 로컬 네트워크 연결을 허용 하도록 열 범위 5990 5999 요구 합니다.<br /><br />게스트의 경우: 이 동일한 포트에서 호스트에 대 한 아웃 바운드 액세스를 네트워크 경로입니다. | "Vsls 에이전트"이 포트 범위에 대 한 데스크톱 방화벽 소프트웨어에 의해 차단 되지 서로 ping 할 수 있는지 확인 합니다. 그룹 정책에서에서이 방지 해야 하는 인스턴스 Windows 및 기타 데스크톱 소프트웨어 라는 메시지가 표시 처음으로 에이전트를 시작, 있지만 살펴본 [항목을 수동으로 추가](#manually-adding-a-firewall-entry)합니다. 에 실행 중일 수 있습니다 [프록시 문제](#proxies) 는 해결 해야 합니다. |
| Relay | 에 대 한 아웃 바운드 액세스 `*.servicebus.windows.net:443`합니다. | 확인 회사 또는 개인 네트워크 방화벽을 사용 하면이 도메인에 연결할 수 있습니다. 에 실행 중일 수 있습니다 [프록시 문제](#proxies) 는 해결 해야 합니다.|

## <a name="manually-adding-a-firewall-entry"></a>방화벽 항목을 수동으로 추가

직접 모드는 개인 방화벽 허용에서는 위에서 설명한 대로 **vsls 에이전트** 5990 5999 범위는 포트에서 연결을 허용 하도록 합니다. 직접 모드를 사용 하지만 방화벽 vsls 에이전트 항목이 없는 발견 하려는 경우 수동으로 추가할 수 있습니다. 에 대 한 정보를 찾을 수 있지만이 방법은 방화벽 소프트웨어에 따라 달라 집니다  **[Windows 방화벽을 구성](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)** 합니다.

Vsls 에이전트에 대 한 항목이 표시 되지 않으면, 다음 위치 중 하나에서 실행 파일 에이전트를 찾을 수 있습니다.

### <a name="vs-code-agent-location"></a>VS 코드 에이전트 위치

대체 **버전** 아래 경로 중 하나에 확장 버전 번호:

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Visual Studio 에이전트 위치

Visual Studio 위치 보다 동적인 이지만 실행 파일을 찾으려면 다음이 단계를 수행 합니다.

1. Visual Studio 설치 위치로 이동 합니다. 일반적으로 이것이 `C:\Program Files (x86)\Microsoft Visual Studio\EDITION` 여기서 **EDITION** Community, Enterprise, 등

2. 검색을 실행 `vsls-agent.exe` 에서 아래 합니다 **IDE\Extensions** 하위 폴더입니다.

이 단계를 수행 해야 하는 안타깝게도 **Visual Studio Live Share를 업데이트할 때마다 있습니다.**

## <a name="proxies"></a>Proxy

Visual Studio Live Share는 현재 프록시 사용과 관련 된 몇 가지 제한이 있습니다. 자동 프록시 설정을 Windows, macOS 또는 Linux를 사용 하는 경우와 Windows에서 특정 프록시 구성으로 작업 해야 하는 동안 합니다 **HTTP_PROXY** 하 고 **HTTPS_PROXY** 환경 변수를 해야 합니다. 설정할 *전역적으로*입니다.

프록시에 이러한 설정 자동으로 하지 않는 경우 다음 형식으로 변수를 수동으로 설정할 수 있습니다.

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

인증 프록시를 사용 하는 경우 추가할 수 있습니다를 통해 사용자 및 암호 다음과 같습니다.

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

이러한 설정 하면 문제가 해결 되지 않을 경우 [알려주세요](https://github.com/MicrosoftDocs/live-share/issues/86) 수 살펴보겠습니다는 지원을 개선 하므로 프록시의 세부 사항을 설정 합니다.

## <a name="see-also"></a>참고자료

- [방법: Visual Studio Code를 사용 하 여 공동 작업](../use/vscode.md)
- [방법: Visual Studio를 사용 하 여 공동 작업](../use/vs.md)
- [Live Share의 보안 기능](security.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
