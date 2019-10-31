---
title: 연결-Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share에 대 한 연결 및 연결 모드에 대 한 정보입니다.
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
ms.openlocfilehash: c1d537ac80daddcf83d18942c8d837f3c0ce370b
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73169985"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Live Share 연결 요구 사항

이 문서에서는 Visual Studio Live Share, 사용 가능한 연결 옵션 및 알려진 해결 방법 (해당 하는 경우)에 대 한 연결 요구 사항을 요약 합니다.

## <a name="sign-in"></a>로그인

[Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory) 지원 되는 회사 또는 학교 계정, [Microsoft 계정](https://account.microsoft.com/account)또는 [GitHub 프로필](https://github.com/)을 사용 하 여 Live Share에 로그인 할 수 있습니다. 이러한 항목에 대 한 로그인 Url은 일반적으로이를 사용 하는 공용 제품 수를 고려 하 여 대부분의 조직에서 열려 있지만, 그렇지 않은 경우에는 [아래 나열 된](#requirements-for-connection-modes)도메인 외에도 `login.microsoftonline.com` 및/또는 `github.com`를 열 수 있도록 네트워크 관리자에 게 문의 하세요.

> [!NOTE]
> 프레미스 AD (ADFS) 계정 및 온-프레미스 GitHub Enterprise 계정은 현재 지원 되지 않습니다 [(최신 응답 👍)](https://github.com/MicrosoftDocs/live-share/issues/341).

## <a name="connection-modes"></a>연결 모드

최적의 성능을 보장 하기 위해 기본적으로 Visual Studio Live Share는 공동 작업 세션 호스트 컴퓨터와 게스트 컴퓨터가 네트워크를 통해 직접 통신할 수 있는지 여부를 자동으로 감지 하 고 둘 사이에 경로가 없는 경우 클라우드를 통해서만 릴레이 합니다. 이러한 혼합 된 "자동" 모드는 유연 하 고 일부 게스트가 동일한 세션에 직접 연결 하는 동안 클라우드를 통해 릴레이할 수 있습니다.

직접 연결은 보안을 보장 하기 위해 클라우드 기반 메커니즘을 통해 인증 되지만, 연결을 사용 하도록 설정 하려면 5990 ~ 5999 사이의 포트를 열어야 합니다. 결과적으로, 처음으로 공유 하는 경우 데스크톱 방화벽에서 포트를 열도록 요청할 수 있습니다. 이 옵션을 사용 하는 것은 무시 해도 되지만 자동 모드에서 항상 릴레이를 사용 하는 Live Share 발생 합니다.

Visual Studio Live Share의 모든 연결은 공동 작업 세션의 해당 콘텐츠에 대 한 액세스 권한을 얻을 수 있도록 중앙 서비스에 대해 암호화 및 인증 된 SSH 또는 SSL입니다. 또한 Live Share의 클라우드 relay는이를 통해 라우팅되는 트래픽을 유지 하지 않으며 어떤 방식으로든 트래픽을 "스 눕" 하지 않습니다.

## <a name="changing-the-connection-mode"></a>연결 모드 변경

직접 또는 릴레이 된 연결을 사용 하지 않도록 설정 하거나 단순히 연결 문제를 해결 하려는 경우 다른 연결 모드를 강제 적용할 수 있습니다.

| 모드 | 호스트 동작 | 게스트 동작 |
|------|----------------|----------------------|
| 자동 | 호스트의 공동 작업 세션은 보안, 인증 된 직접 연결 또는 클라우드 릴레이 된 연결을 허용 합니다. | 는 직접 연결을 사용 하려고 시도 하 고 실패 하는 경우 클라우드를 통한 릴레이로 대체 합니다. |
| 직접 | 호스트의 공동 작업 세션은 인증 된 보안 직접 연결만 허용 합니다. | 직접 연결을 사용 하려고 시도 하 고 연결할 수 없는 경우 중지 합니다. |
| Relay | 호스트의 공동 작업 세션에서 직접 연결을 허용 하지 않습니다. 호스트의 컴퓨터에서 열려 있는 포트가 없습니다. | 는 항상 클라우드를 통해 연결 합니다. |

모드를 변경 하려면:

**-**

1. 도구 > 옵션 > Live Share으로 이동 합니다.
2. "연결 모드" 드롭다운에서 모드를 선택 합니다.
3. 다시 시작 및

**VS Code:**

1. 설정. json (파일 > 기본 설정 > 설정)을 편집 합니다.
2. 기본 설정에 따라 `"liveshare.connectionMode"`를 `"auto"`, `"direct"`또는 `"relay"`로 설정 합니다.
3. VS Code를 다시 시작 합니다.

## <a name="requirements-for-connection-modes"></a>연결 모드에 대 한 요구 사항

연결 모드에 따라 Live Share 작동 하는 데 사용할 수 있어야 하는 특정 포트 및 Url이 결정 됩니다.

| 모드 | 클라이언트 액세스 요구 사항 | 문제 해결 |
|------|--------------|-----------------|
| 임의의 값 | `*.liveshare.vsengsaas.visualstudio.com:443`에 대 한 아웃 바운드 액세스 | 회사 또는 개인 네트워크 방화벽을 통해이 도메인에 연결할 수 있는지 확인 합니다. 브라우저에 https://insiders.liveshare.vsengsaas.visualstudio.com 를 입력 하 고 Visual Studio Live Share 홈 페이지에 있는지 확인 합니다. 해결 해야 하는 [프록시 문제](#proxies) 를 실행할 수도 있습니다.|
| Any (VS Code) | `download.microsoft.com:443`에 대 한 아웃 바운드 액세스 | 회사 또는 개인 네트워크 방화벽을 통해이 도메인에 연결할 수 있는지 확인 합니다. 해결 해야 하는 [프록시 문제](#proxies) 를 실행할 수도 있습니다. |
| 자동 | 자동 전환. 직접 및 릴레이 모드를 참조 하세요. | 문제를 해결 하려면 직접 또는 릴레이 모드로 전환 합니다. |
| 직접 | 호스트: 인바운드 로컬 네트워크 연결을 허용 하려면 5990-5999 범위의 포트를 열어야 합니다.<br /><br />게스트:이 동일한 포트에서 호스트에 대 한 네트워크 경로 및 아웃 바운드 액세스입니다. | "Vsls-agent"가이 포트 범위에 대 한 데스크톱 방화벽 소프트웨어에 의해 차단 되지 않는지, 그리고 서로 ping 할 수 있는지 확인 합니다. Windows 및 기타 데스크톱 소프트웨어는 에이전트가 처음 시작 될 때 메시지를 표시 해야 하지만 그룹 정책에서이 작업을 차단 하는 것을 방지 하 고 [항목을 수동으로 추가](#manually-adding-a-firewall-entry)해야 하는 경우를 확인 합니다. 해결 해야 하는 [프록시 문제](#proxies) 를 실행할 수도 있습니다. |
| Relay | `*.servicebus.windows.net:443`에 대 한 아웃 바운드 액세스입니다. | 회사 또는 개인 네트워크 방화벽을 통해이 도메인에 연결할 수 있는지 확인 합니다. 해결 해야 하는 [프록시 문제](#proxies) 를 실행할 수도 있습니다.|

## <a name="manually-adding-a-firewall-entry"></a>수동으로 방화벽 항목 추가

위에서 설명한 대로 직접 모드에서는 개인 방화벽이 **vsls-agent** 가 포트 범위 5990-5999의 연결을 허용 하도록 허용 해야 합니다. 직접 모드를 사용 하지만 방화벽에 vsls 에이전트 항목이 없다는 것을 발견 한 경우 수동으로 추가할 수 있습니다. 이 작업을 수행 하는 방법은 방화벽 소프트웨어에 따라 다르지만 **[여기에서 Windows 방화벽을 구성](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)** 하는 방법에 대 한 정보를 찾을 수 있습니다.

Vsls-agent에 대 한 항목이 표시 되지 않으면 다음 위치 중 하나에서 에이전트 실행 파일을 찾을 수 있습니다.

### <a name="vs-code-agent-location"></a>VS Code 에이전트 위치

다음 경로 중 하나에서 **확장 버전 번호를 대체 합니다** .

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Visual Studio 에이전트 위치

Visual Studio 위치는 동적 이지만 다음 단계를 수행 하 여 실행 파일을 찾을 수 있습니다.

1. Visual Studio 설치 위치로 이동 합니다. 이는 일반적으로 **버전이** Community, Enterprise 등 인 `C:\Program Files (x86)\Microsoft Visual Studio\EDITION`입니다.

2. **IDE\Extensions** 하위 폴더 아래에서 `vsls-agent.exe`에 대 한 검색을 실행 합니다.

그러나 **Visual Studio Live Share를 업데이트할** 때마다이 단계를 수행 해야 할 수 있습니다.

## <a name="proxies"></a>Proxy

Visual Studio Live Share 현재 프록시 사용에 대 한 몇 가지 제한 사항이 있습니다. Windows에서 자동 프록시 설정이 작동 하는 반면 macOS 또는 Linux를 사용 하는 경우 및 Windows의 특정 프록시 구성에서 **HTTP_PROXY** 및 **HTTPS_PROXY** 환경 변수를 *전역적*으로 설정 해야 합니다.

프록시가 자동으로 이러한 설정을 자동으로 설정 하지 않는 경우 다음과 같은 형식으로 변수를 수동으로 설정할 수 있습니다.

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

인증 프록시가 있는 경우 다음과 같이 사용자와 암호를 추가할 수 있습니다.

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

이러한 설정으로 인해 문제가 해결 되지 않으면 지원 향상에 대 한 [자세한](https://github.com/MicrosoftDocs/live-share/issues/86) 내용을 확인할 수 있도록 프록시 설정의 세부 정보를 알려주세요.

## <a name="see-also"></a>참조

- [방법: Visual Studio Code를 사용 하 여 공동 작업](../how-to-guides/vscode.md)
- [방법: Visual Studio를 사용 하 여 공동 작업](../how-to-guides/vs.md)
- [Live Share의 보안 기능](security.md)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
