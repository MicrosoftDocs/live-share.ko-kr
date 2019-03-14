---
title: 플랫폼 및 언어 지원-Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live 공유에 대 한 플랫폼 및 언어 지원의 개요입니다.
ms.custom: ''
ms.date: 04/25/2018
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
ms.openlocfilehash: 5c8429779bcfe39842ba298c3b6371daa1cf7fe4
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255938"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>언어 및 플랫폼 지원

Visual Studio Live Share의 기능은 언어 및 응용 프로그램 플랫폼의 다양 한 환경에서 작동 하기 위해서입니다. 그러나 변형 수가 너무 많아 들어 일부 플랫폼 및 언어는 다른 항목 보다 더 완료. 이 문서에서는 현재 알려진 다양 한 인기 있는 언어 및 현재 지원 되는 기능에 대 한 플랫폼의 상태를 설명 합니다.

언어 또는 플랫폼 해야 표시? 이 표시 되지 않는 하나를 추가 하 시겠습니까? [여기에 응답 합니다.](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

모든 언어 / 플랫폼 동일한 파일 intellisense (해당 확장이 설치 된 경우) 뿐만 아니라 색 지정 및 공동 편집을 지원 합니다. 완전 한 범용 지원은 현재 기능을 다룹니다 고급 아래 나열 됩니다.

### <a name="languages"></a>언어

| 언어 | 공유 언어 서비스 | 디버깅 공유 |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *해당 없음* |
| Ballerina | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *해당 없음* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *해당 없음* <sup>4</sup> |
| [Crystal](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *해당 없음* <sup>4</sup> |
| CSHTML | *해당 없음* <sup>1</sup> | ✅ |
| CSS | *해당 없음* | *해당 없음* |
| Dart | ✅ | ✅ |
| Docker | ✅ | *해당 없음* |
| 퀘스트 액 | ✅ | ✅ |
| Elm | ✅ |  *해당 없음* <sup>4</sup> |
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
| JavaScript / TypeScript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *해당 없음* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *해당 없음* | *해당 없음* <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *해당 없음* |
| MATLAB |  ✅ | *해당 없음* <sup>4</sup> |
| Objective-C | ✅ | *해당 없음* <sup>4</sup> |
| Pascal | ✅ | *해당 없음* <sup>4</sup> |
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
| SQL / T-SQL | *해당 없음* | *해당 없음* <sup>4</sup> |
| [스타일러스](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *해당 없음* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *해당 없음* <sup>4</sup> |
| Swift | ✅ | *해당 없음* <sup>4</sup> |
| Terraform | ✅ | *해당 없음* <sup>4</sup> |
| XML | ✅ | *해당 없음* <sup>4</sup> |
| YAML | ✅ | *해당 없음* <sup>4</sup> |

<sup>1</sup> 에 없는 CSHTML 지원 C# 확장 합니다.<br />
<sup>2</sup> HTML에 포함 된 JavaScript가 클라이언트측 디버깅을 수행 하는 경우 지원 합니다.<br />
<sup>3</sup> JavaScript / TypeScript 노드 또는 브라우저에 대 한 디버깅 합니다.<br />
<sup>4</sup> VS Code에 대 한 해당 확장 디버깅를 현재 지원 하지 않습니다. 이 즉시 조사 하겠습니다 공동 디버깅 지원 추가. <br />

### <a name="platforms"></a>플랫폼

| 앱/플랫폼 유형 | 디버깅 공유 | 앱 공유 |
|-------------------|--------------|-------------|
| Arduino | ✅ | *해당 없음* |
| Azure App Service | ✅ | *해당 없음* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure 함수 (로컬 및 원격) | ✅ | ✅ <sup>1</sup> |
| 블록 체인 (Ethereum) | ✅ | ✅ <sup>1</sup> |
| 콘솔 / CLI | ✅ | ✅ <sup>4</sup> |
| Databases | <sup>5</sup> | ✅ <sup>1</sup> |
| 데스크톱 (전자/네이티브) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| 게임 (Unity) | ✅ | <sup>9</sup> |
| 게임 (Unreal) | ✅ | <sup>9</sup> |
| Kubernetes (YAML, Helm) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *해당 없음* | ✅ <sup>6</sup> |
| 모바일 (Cordova) | ✅ | ✅ <sup>1,7</sup> |
| 모바일 (네이티브) | ✅ | <sup>9</sup> |
| 모바일 (React Native) | ✅ | ✅ <sup>1,8</sup> |
| 웹 앱 / API (백 엔드) | ✅ | ✅ <sup>1</sup> |
| 웹 앱 (프런트 엔드) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| VS Code 확장 | | <sup>9</sup> |

<sup>1</sup> 를 통해 [공유 로컬 서버](../use/vscode.md#share-a-server)합니다.<br />
<sup>2</sup> 디버깅 호스트의 브라우저 보다는 게스트에 대해 발생 합니다.<br />
<sup>3</sup> 백 엔드를 공유 하 여 합니다.<br />
<sup>4</sup> 공유 터미널을 통해 지원 합니다.<br />
<sup>5</sup> 데이터베이스 저장 프로시저를 디버깅 합니다. 현재 지원 되지 않습니다 <br />
<sup>6</sup> "preview"를 통해. 그러나 이미지 알려진된 문제로 인해 표시 되지 않습니다. [투표 (👍) 같습니다.](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> "브라우저" 플랫폼을 통해 Cordova 앱을 공유할 수 있습니다<br />
<sup>8</sup> Expo 통해 react Native 앱을 공유할 수 있습니다 하 고 [공유 서버](../use/vscode.md#share-a-server)합니다.<br />
<sup>9</sup> live Share 현재 windows/화면 공유를 지원 하지 않습니다. [투표 (👍) 같습니다.](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

대부분의 언어가 일부 단일 파일 Intellisense 지원 하지만 몇 가지 주의 사항이 아래에 설명 합니다. 모든 언어/플랫폼 공동 편집을 지원 합니다. 목록의 나머지 전체, 범용 지원은 현재 고급 기능에 설명 합니다.

### <a name="languages"></a>언어

| 언어 | 단일 파일 언어 서비스 | 프로젝트 전체 언어 서비스 | 공동 디버깅 |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅  <sup>1</sup> | | ✅ |
| ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *해당 없음* | <sup>2</sup> |
| CSS | ✅ | *해당 없음* | *해당 없음* |
| JavaScript / TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *해당 없음* | *해당 없음* |
| PowerShell | ✅ | *해당 없음* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *해당 없음* | <sup>4</sup> |
| SQL / T-SQL | ✅ | *해당 없음* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *해당 없음* | ✅ |

<sup>1</sup> 간격: CSHTML, VBHTML, ASPX 있고 알려진 문제 약 포함 된 C#코드 숨김 지정 /VB 지원 C#구현 되지 않은 완전 한 intellisense 인해 /VB 파일 확인 되지 않습니다. [투표 (👍) CSHTML/VBHTML 여기 있습니다.](https://github.com/MicrosoftDocs/live-share/issues/59) [투표 (👍) ASPX 여기 있습니다.](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup> HTML에 포함 된 JavaScript가 클라이언트측 디버깅을 수행 하는 경우 지원 합니다.<br />
<sup>3</sup> JavaScript / TypeScript 노드 또는 브라우저에 대 한 디버깅 합니다.<br />
<sup>4</sup> 해당 없음 기술적으로 자체 XAML 디버깅, 코드 숨김 디버깅 지원 됩니다.<br />
<sup>5</sup> 간격: 조인에 모든 줄 바꿈 후 게스트 우변 R 언어 서비스 오류입니다. 지원되지 않습니다. [투표 (👍) 같습니다.](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>플랫폼

| 앱/플랫폼 유형 | 공동 디버깅 | 앱 공유 |
|-------------------|--------------|-------------|
| 웹 앱 / API (백 엔드) | ✅ | ✅ <sup>1</sup> |
| 웹 앱 (프런트 엔드) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Azure Functions | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Azure 개발 공간](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| Databases | <sup>4</sup> | ✅ <sup>5</sup> |
| 콘솔 / CLI | ✅ | ✅ <sup>6</sup> |
| 데스크톱 (WinForms) | ✅ | |
| 데스크톱 (WPF) | ✅ | |
| UWP | ✅ |  |
| VS 확장 기능 | ✅ |  |

<sup>1</sup> 를 통해 [공유 로컬 서버](../use/vs.md#share-a-server)합니다. ASP.NET 웹 앱을 이용할 수 있습니다 [자동 웹 앱 공유](../use/vs.md#automatic-web-app-sharing)합니다.<br />
<sup>2</sup> 디버깅 호스트의 브라우저 보다는 게스트에 대해 발생 합니다.<br />
<sup>3</sup> 백 엔드를 공유 하 여 합니다.<br />
<sup>4</sup> 데이터베이스 저장 프로시저를 디버깅 합니다. 현재 지원 되지 않습니다 <br />
<sup>5</sup> 를 통해 [공유 로컬 서버](../use/vs.md#share-a-server)합니다. <br />
<sup>6</sup> 공유 터미널을 통해 부분적으로 지원 합니다.<br />
<sup>?</sup> 유효성이 검사 되지 않습니다.

## <a name="see-also"></a>참고자료

- [확장 지원](extensions.md)
- [Live Share 연결 요구 사항](connectivity.md)
- [Live Share의 보안 기능](security.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
