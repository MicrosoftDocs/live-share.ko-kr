---
title: 플랫폼 및 언어 지원-Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live share의 플랫폼 및 언어 지원에 대 한 개요입니다.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 386a8204787ed378413e1b35b7c2a80e0de678ce
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170097"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>언어 및 플랫폼 지원

Visual Studio Live Share 기능은 다양 한 언어와 응용 프로그램 플랫폼에서 작동 하기 위한 것입니다. 그러나 변형 수가 많기 때문에 일부 플랫폼과 언어가 다른 플랫폼과 언어 보다 더 완전 하 게 제공 됩니다. 이 문서에서는 현재 지원 되는 기능에 대해 많이 사용 되는 다양 한 언어 및 플랫폼의 현재 알려진 상태를 다룹니다.

필요한 언어 또는 플랫폼을 확인 하세요. 표시 되지 않는 항목을 추가 하 시겠습니까? [여기에서 투표 하세요.](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

모든 언어/플랫폼에는 동일한 파일 intellisense (각 확장이 설치 된 경우)와 색 지정 및 공동 편집 지원이 있습니다. 아래 목록에는 현재 전체 지원 되지 않는 고급 기능이 포함 되어 있습니다.

### <a name="languages"></a>언어

| 언어 | 공유 언어 서비스 | 공유 디버깅 |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *해당 없음* |
| Ballerina | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *해당 없음* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *해당 없음* <sup>4</sup> |
| [크리스탈](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *해당 없음* <sup>4</sup> |
| CSHTML | *해당 없음* <sup>1</sup> | ✅ |
| CSS | *해당 없음* | *해당 없음* |
| 사냥 | ✅ | ✅ |
| Docker | ✅ | *해당 없음* |
| Elixir | ✅ | ✅ |
| 느릅나무 | ✅ |  *해당 없음* <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  *해당 없음* <sup>4</sup> |
| 흐름 | ✅ |  *해당 없음* <sup>4</sup> |
| Fortran | ✅ | *해당 없음* |
| 이동 | ✅ | ✅ |
| Gradle | ✅ | *해당 없음* <sup>4</sup> |
| GraphQL | ✅ | *해당 없음* <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *해당 없음* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript/TypeScript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *해당 없음* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *해당 없음* | *해당 없음* <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *해당 없음* |
| MATLAB |  ✅ | *해당 없음* <sup>4</sup> |
| Objective-C | ✅ | *해당 없음* <sup>4</sup> |
| 파스칼식 | ✅ | *해당 없음* <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *해당 없음* | ✅ |
| Python |  ✅ | ✅ |
| PureScript | ✅ | *해당 없음* <sup>4</sup> |
| R |  ✅ | *해당 없음* <sup>4</sup> |
| [이유/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *해당 없음* <sup>4</sup> |
| reStructuredText | ✅ | *해당 없음* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *해당 없음* <sup>4</sup> |
| [Sass](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *해당 없음* |
| Scala | ✅ | *해당 없음* <sup>4</sup> |
| Solidity | ✅ | *해당 없음* <sup>4</sup> |
| SQL/T-SQL | *해당 없음* | *해당 없음* <sup>4</sup> |
| [스타일러스](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *해당 없음* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *해당 없음* <sup>4</sup> |
| Swift | ✅ | *해당 없음* <sup>4</sup> |
| Terraform | ✅ | *해당 없음* <sup>4</sup> |
| XML | ✅ | *해당 없음* <sup>4</sup> |
| YAML | ✅ | *해당 없음* <sup>4</sup> |

<sup>1</sup> 확장에서 C# CSHTML 지원이 지원 되지 않습니다.<br />
<sup>2</sup> 클라이언트 디버깅을 수행할 때 HTML의 포함 된 JavaScript가 지원 됩니다.<br />
<sup>3</sup> 노드 또는 브라우저의 JavaScript/TypeScript 디버깅<br />
<sup>4</sup> VS Code의 각 확장은 현재 디버깅을 지원 하지 않습니다. 이를 수행 하는 즉시 공동 디버깅 지원 추가를 조사 합니다. <br />

### <a name="platforms"></a>플랫폼

| 앱/플랫폼 유형 | 공유 디버깅 | 앱 공유 |
|-------------------|--------------|-------------|
| Arduino | ✅ | *해당 없음* |
| Azure App Service | ✅ | *해당 없음* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure Functions (로컬 및 원격) | ✅ | ✅ <sup>1</sup> |
| 블록 체인 (Ethereum) | ✅ | ✅ <sup>1</sup> |
| 콘솔/CLI | ✅ | ✅ <sup>4</sup> |
| Databases | <sup>5</sup> | ✅ <sup>1</sup> |
| 데스크톱 (전자/네이티브) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| 게임 (Unity) | ✅ | <sup>9</sup> |
| 게임 (Unreal) | ✅ | <sup>9</sup> |
| Kubernetes (YAML, 투구) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *해당 없음* | ✅ <sup>6</sup> |
| 모바일 (Cordova) | ✅ | ✅ <sup>1, 7</sup> |
| 모바일 (네이티브) | ✅ | <sup>9</sup> |
| 모바일 (네이티브에 반응) | ✅ | ✅ <sup>1, 8</sup> |
| 웹 앱/a p i (백 엔드) | ✅ | ✅ <sup>1</sup> |
| 웹 앱 (프런트 엔드) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| VS Code 확장 | | <sup>9</sup> |

<sup>1</sup> [공유 로컬 서버](../how-to-guides/vscode.md#share-a-server)를 통해<br />
<sup>2</sup> 디버깅은 게스트가 아닌 호스트의 브라우저에 대해 발생 합니다.<br />
<sup>3</sup> 백 엔드를 공유 합니다.<br />
<sup>4</sup> 공유 터미널을 통해 지원 됩니다.<br />
<sup>5</sup> 데이터베이스 저장 프로시저 디버깅은 현재 지원 되지 않습니다. <br />
<sup>6</sup> "미리 보기"를 통해 그러나 이미지는 알려진 문제 때문에 표시 되지 않습니다. [투표 (👍)](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> Cordova 앱은 "브라우저" 플랫폼을 통해 공유할 수 있습니다.<br />
<sup>8</sup> 응답 네이티브 앱은 예기치 않은 o 및 [공유 서버](../how-to-guides/vscode.md#share-a-server)를 통해 공유할 수 있습니다.<br />
<sup>9</sup> Live Share는 현재 windows/화면 공유를 지원 하지 않습니다. [투표 (👍)](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

대부분의 언어에는 일부 단일 파일 Intellisense 지원이 있지만 아래에 설명 된 몇 가지 주의 사항이 있습니다. 모든 언어/플랫폼은 공동 편집을 지원 합니다. 목록의 나머지 부분에는 현재 완전 한 지원 없이 현재 고급 기능이 포함 되어 있습니다.

### <a name="languages"></a>언어

| 언어 | 단일 파일 언어 서비스 | 프로젝트 전체 언어 서비스 | 공동 디버깅 |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅<sup>1</sup> | | ✅ |
| LOGIN.ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *해당 없음* | <sup>2</sup> |
| CSS | ✅ | *해당 없음* | *해당 없음* |
| JavaScript/TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *해당 없음* | *해당 없음* |
| PowerShell | ✅ | *해당 없음* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *해당 없음* | <sup>4</sup> |
| SQL/T-SQL | ✅ | *해당 없음* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *해당 없음* | ✅ |

<sup>1</sup> 간격: CSHTML, VBHTML 및 ASPX에는 지정 된 코드 숨김이 C# C#지원 되지 않음 (전체 intellisense가 구현 되지 않아 해당 파일이 확인 되지 않음)과 관련 하 여 알려진 문제가 있습니다. [CSHTML/VBHTML에 투표 (👍) 합니다.](https://github.com/MicrosoftDocs/live-share/issues/59) [여기에는 ASPX에서 투표 (👍) 합니다.](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup> 클라이언트 디버깅을 수행할 때 HTML의 포함 된 JavaScript가 지원 됩니다.<br />
<sup>3</sup> 노드 또는 브라우저의 JavaScript/TypeScript 디버깅<br />
<sup>4</sup> XAML 자체를 디버깅 하는 것은 기술적으로 N/A입니다. 디버그 코드 숨김이 지원 됩니다.<br />
<sup>5</sup> 간격: 조인 시 게스트 쪽에서 R 언어 서비스 오류, 모든 줄 바꿈 이후 지원되지 않음 [투표 (👍)](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>플랫폼

| 앱/플랫폼 유형 | 공동 디버깅 | 앱 공유 |
|-------------------|--------------|-------------|
| 웹 앱/a p i (백 엔드) | ✅ | ✅ <sup>1</sup> |
| 웹 앱 (프런트 엔드) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Azure Functions | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Azure Dev Spaces](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| Databases | <sup>4</sup> | ✅ <sup>5</sup> |
| 콘솔/CLI | ✅ | ✅ <sup>6</sup> |
| 데스크톱 (WinForms) | ✅ | |
| 데스크톱 (WPF) | ✅ | |
| UWP | ✅ |  |
| VS 확장 | ✅ |  |

<sup>1</sup> [공유 로컬 서버](../how-to-guides/vs.md#share-a-server)를 통해 ASP.NET Web Apps [자동 웹 앱 공유](../how-to-guides/vs.md#automatic-web-app-sharing)를 사용할 수도 있습니다.<br />
<sup>2</sup> 디버깅은 게스트가 아닌 호스트의 브라우저에 대해 발생 합니다.<br />
<sup>3</sup> 백 엔드를 공유 합니다.<br />
<sup>4</sup> 디버깅 데이터베이스 저장 프로시저는 현재 지원 되지 않습니다. <br />
<sup>5</sup> Via [공유 로컬 서버](../how-to-guides/vs.md#share-a-server). <br />
<sup>6</sup> 공유 터미널을 통해 부분적으로 지원 됩니다.<br />
<sup>?</sup> 아직 확인 되지 않았습니다.

## <a name="see-also"></a>참조

- [확장 지원](extensions.md)
- [Live Share 연결 요구 사항](connectivity.md)
- [Live Share의 보안 기능](security.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
