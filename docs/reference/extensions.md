---
title: 확장 및 에코 시스템 지원-Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live 공유에 대 한 확장 지원 간략히 설명 합니다.
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
ms.openlocfilehash: 57be1ffd58be1a752974d58407adecd0d51fe9f0
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640239"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="extensions-and-ecosystem-support"></a>확장 및 에코 시스템 지원

Visual Studio Live Share의 기본 목표 중 하나는 개발자가 그들이 즐겨 쓰는 편안 하 게 서로 협력할 수 있도록 하 고 [ **고도로 사용자 지정** ](https://marketplace.visualstudio.com/) 도구입니다. 이 이렇게 하면 임시 상호 작용 자주 발생할 수 있습니다 시각적으로 친숙 하 고 인체 하면서와 상관 없이 어떤 도움을 요청 사용 하 여. 이 작업을 수행 하는 것이 중요 참가자가 공동 작업 세션 내에서 지원 되는 모든 확장을 사용 하 여 계속할 수는 해당 [개인 기본 설정 및 워크플로](#user-specific-extensions) (예: 색/아이콘 테마, 키 바인딩, 편집기 생산성 범주별)입니다.

또한 작업으로 공동 작업 세션에 참가 하도록 항상-생산성을 유지 하면서 최대한 인스턴트 Visual Studio Live Share의 목표는 자동으로 해당 호스트가 공유 프로젝트 관련 도구를 활용 하 여 게스트를 사용 하도록 설정 하려면. 이 이렇게 하면 단순히 링크를 클릭, 선택한 도구를 시작 하 수 추가 설정 없이 공동 작업을 시작 합니다. 이 작업을 수행 하는 것이 중요 핵심 power는 해당 확장 [편집, 빌드 및 디버그 워크플로](#project-specific-extensions)게스트 호스트에서 투명 하 게 "원격" 같은 자동 완성를 정의로 이동 되도록 하 고는 디버깅 " "작동 합니다.

이 문서에서는 현재는 광범위 한 확장 에코 시스템에 대 한 상태와 앞에서 언급 한 목표에 대 한 "성과 기록표" 알려진를 설명 합니다. 이 조건에 맞지 이며 개인 워크플로에 중요 한 확장을 발생 하면 주십시오 [알려주세요!](https://github.com/MicrosoftDocs/live-share/issues/new)

## <a name="user-specific-extensions"></a>사용자 고유의 확장

사용자 고유의 사용자 지정을 지 원하는 확장 프로그램 **해야 합니다** 호스트에 대해 작동 하 고 **해야** 모든 게스트에 대해 작동 합니다. 호스트에 대 한 확장이 제대로 작동 하지 않으면는 회귀를 사용할 수 있고 Visual Studio Live Share의 버그 될 수 있습니다 (하세요 [문제를 제출](https://github.com/MicrosoftDocs/live-share/issues/new) 하나를 참조 하는 경우!). 확장을 게스트에 대 한 예상 대로 작동 하지 않습니다, 경우 필요할 수 있습니다 [자체의 확장에서 변경 내용을](#known-issues), 이러한 시나리오 주소/개선 하기 위해 에코 시스템을 사용 하 고 있습니다.

### <a name="visual-studio-code"></a>Visual Studio Code

| 범주 | 예제 | 게스트 지원 되나요? | 공동 작업? |
|-|-|-|-|
| 색 테마 | [하나의 어두운 Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme), [Colorizer 출력](https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer), [Rainbow 문자열](https://marketplace.visualstudio.com/items?itemName=wk-j.vscode-rainbow-string), [색이 지정 된 지역](https://github.com/jmihelcic/colored-regions), [강조 표시 하는 블록 들여쓰기](https://marketplace.visualstudio.com/items?itemName=byi8220.indented-block-highlighting), [ Todo 강조](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight), [대괄호 쌍 Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) | ✅ | *해당 없음* |
| 아이콘 집합 | [vscode 아이콘](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons), [Visual Studio 클래식 아이콘](https://marketplace.visualstudio.com/items?itemName=jez9999.vsclassic-icon-theme) | ✅ | *해당 없음* |
| 키 바인딩 | [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)하십시오 [IntelliJ IDEA Keybindings](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings), [Emacs 친숙 한 키맵](https://marketplace.visualstudio.com/items?itemName=lfs.vscode-emacs-friendly) | ✅ | *해당 없음* |
| 코드 조각 | [Angular v5 조각](https://marketplace.visualstudio.com/items?itemName=johnpapa.Angular2), [HTML 조각을](https://marketplace.visualstudio.com/items?itemName=abusaidm.html-snippets)합니다 [SVG 아이콘](https://marketplace.visualstudio.com/items?itemName=idleberg.svg-icons), [헤더 파일](https://marketplace.visualstudio.com/items?itemName=mikey.vscode-fileheader) | ✅ | *해당 없음* <sup>1</sup> |
| 조직 | [설정 동기화](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync), [프로젝트 관리자](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager)를 [동안](https://marketplace.visualstudio.com/items?itemName=smulyono.timeit)를 [검사점](https://marketplace.visualstudio.com/items?itemName=micnil.vscode-checkpoints)를 [TODO 파서](https://marketplace.visualstudio.com/items?itemName=minhthai.vscode-todo-parser), [즐겨찾기 ](https://marketplace.visualstudio.com/items?itemName=kdcro101.favorites) (❌) [책갈피](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) (❌) | ✅ <sup>2</sup> | *해당 없음* <sup>3</sup> |
| 생산성 | [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens), [자동 이름 바꾸기 태그](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)를 [개요 코드](https://github.com/patrys/vscode-code-outline)를 [강조 표시 색](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)를 [선택 증가](https://marketplace.visualstudio.com/items?itemName=albymor.increment-selection), [ Bracketeer](https://marketplace.visualstudio.com/items?itemName=pustelto.bracketeer), [미리 보기 이미지](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-gutter-preview), [JSON 도우미](https://marketplace.visualstudio.com/items?itemName=zhoufeng.json-helper) (마우스 포인터)를 [색 선택기](https://marketplace.visualstudio.com/items?itemName=anseki.vscode-color)를 [커서에서 Word 복사](https://marketplace.visualstudio.com/items?itemName=alefragnani.copy-word), [CodeMetrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics) (CodeLens) [Git 공동 작성자](https://github.com/rjimenezda/vscode-coauthor)를 [JavaScript 부스터](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster) (CodeActions) [터보 콘솔 로그](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log)합니다 [ Goto 다음/이전 멤버](https://marketplace.visualstudio.com/items?itemName=mishkinf.goto-next-previous-member)하십시오 [자동 스크롤](https://github.com/PejmanNik/vscode-autoScroll?files=1), [NPM 가져오기 버전](https://marketplace.visualstudio.com/items?itemName=axetroy.vscode-npm-import-package-version) (❌) [비용 가져오기](https://github.com/wix/import-cost) (❌) | ✅ <sup>2</sup> | ❌ <sup>3</sup> |
| 생산적인 | [REST 클라이언트](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)하십시오 [Runner 코드](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner), [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode), [R](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r) | ✅ <sup>4</sup> | ❌ <sup>3</sup>  |
| 리소스 관리자 | [mssql](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql), [ftp-simple](https://marketplace.visualstudio.com/items?itemName=humy2833.ftp-simple)를 [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions)를 [Docker](https://marketplace.visualstudio.com/items?itemName=PeterJausovec.vscode-docker), [Brew 서비스](https://marketplace.visualstudio.com/items?itemName=beauallison.brew-services) | ✅ <sup>5</sup> | ❌ <sup>3</sup>  |

<sup>1</sup> *경우가 아니면 사용자가 이미 친숙 한 코드 조각을 사용 하 여, 수, 기대 하지 않습니다. 따라서 공유 있도록 반드시은 적합 하지 않습니다.*

<sup>2</sup> *이러한 확장 범주는 다양 하므로, 말할 수는 모두 올바르게 작동 합니다. 그러나 이론적으로, 및 않은 키를 추적 하 게 했습니다.*

<sup>3</sup> *최종 사용자 피드백을 해야 하므로 및 공동 작업 환경에서 이러한 확장 범주 도움이 될 수 있습니다.*

<sup>4</sup> *게스트 런타임 도구가 설치 되어 (예: Node.js) 및 코드를 로컬로 실행 하 여 작업 해야 합니다.*

<sup>5</sup> *일종의 서버에 연결 하 여 작업 및 하거나 중앙 집중식된 서버, 서버 게스트가 공유를 작업할 수 있습니다.*

### <a name="visual-studio"></a>Visual Studio

개봉박두.

## <a name="project-specific-extensions"></a>프로젝트별 확장

호스트가 설치 확장을 핵심 편집, 빌드, 응용 프로그램의 디버깅을 지원 하 고 언어/플랫폼/라이브러리/SDK로 관련 된 어떤 항목도 설치 하도록 요구 하지 않고 게스트를 자동으로 사용할 수 있어야 합니다. 이 이렇게 하면 호스트 프로젝트의 생산성이 뛰어난 개발을 지원 하도록 해당 환경을 설정를 즉시 추가 필수 구성 요소 없이 조인 하면 해당 게스트를 허용 합니다. 프로젝트별 확장 주관적인 또는 어떤 방식으로든에서 개인가 아닌 때문에 명확 하 게 공유할 수 호스트-게스트에서 모든 사용자의 친숙 한 환경에 영향을 주지 않고 합니다.

또한 게스트에 설치 되어 있는 프로젝트별 확장 하지만 호스트를 지원 하기 위해 하지을 이상적으로 제공 하는지는 성능 저하, 아직 기능 환경 (예: 단일 파일 intellisense를 가져오는, 문서 형식 수).

| 범주 | 예제 | 공유? | 게스트 지원 되나요? |
|-------|----------|--------|-----|
| 문법 구문 강조 표시 / | [셸 낚시](https://marketplace.visualstudio.com/items?itemName=TeddyDD.fish), [Nginx](https://marketplace.visualstudio.com/items?itemName=shanoor.vscode-nginx), [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)를 [DotEnv](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv)를 [ES6 문자열 HTML](https://marketplace.visualstudio.com/items?itemName=hjb2012.vscode-es6-string-html)를 [Todo +](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-todo-plus), [Rainbow CSV](https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv) | ❌ | ✅ |
| 언어 서비스 | [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml), [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [ARM](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools) | ✅ <sup>1</sup>| ✅ <sup>2</sup> |
| JSON 스키마 | [Azure 기능](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions) | ✅ | ✅ |
| Linter | [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint), [Markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint), [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker), [PHPCS](https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs) | ✅ | ✅ <sup>2</sup>  |
| 포맷터 | [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode), [Beautify](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify) | ✅ | ✅ <sup>2</sup> |
| 디버거 | [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python), [Chrome 용 디버거](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) | ✅ <sup>3</sup> | ❌ <sup>4</sup> |
| 테스트 실행 기 | [Java Test Runner](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-test), [Mocha 사이드바](https://marketplace.visualstudio.com/items?itemName=maty.vscode-mocha-sidebar)합니다 [Postman Runner](https://marketplace.visualstudio.com/items?itemName=eridem.vscode-postman)를 [Runner Jest](https://marketplace.visualstudio.com/items?itemName=firsttris.vscode-jest-runner), [Neptune](https://marketplace.visualstudio.com/items?itemName=LambdaFactory.neptune) | ❌ <sup>5</sup> | ✅ <sup>2</sup> |
| 사용자 지정 파일 미리 보기 | [SVG 미리 보기](https://marketplace.visualstudio.com/items?itemName=cssho.vscode-svgviewer)하십시오 [GraphViz](https://marketplace.visualstudio.com/items?itemName=joaompinto.vscode-graphviz), [Markdown 이미지 크기](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-image-size) | ❌ |  ✅ |
| 파일/프로젝트 생성기 | [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions), [C/c + + 프로젝트 생성기](https://marketplace.visualstudio.com/items?itemName=danielpinto8zz6.c-cpp-project-generator) | ❌ | ❌<sup>6</sup> |
| 소스 제어 공급자 | [SVN](https://marketplace.visualstudio.com/items?itemName=johnstoncode.svn-scm), [Hg](https://marketplace.visualstudio.com/items?itemName=mrcrowl.hg) | ❌ | ❌ |

<sup>1</sup> *현재 C# 및 곧 지원 더 보기를 사용 하 여 JavaScript/TypeScript입니다.*

<sup>2</sup> *게스트가 로컬 파일 액세스가 없으므로 현재 활성 문서를 지원 합니다.*

<sup>그러나 3</sup> *디버깅 환경은 핵심 공유, 시작된 서버 자동으로 전달 되지 않습니다.*

<sup>4</sup> *게스트 앱의 로컬 복사본을 없고 따라서 실행 중인 앱 및 모든 디버그 세션 해야 호스트의 컴퓨터에서 시작 합니다.*

<sup>5</sup> *게스트를 사용 하 여 모든 결과 터미널, 출력 창 및 오류 공유도 된 테스트 실행의 출력 해야 합니다.*

<sup>6</sup> *Node.js를 사용 하는 이러한 거의 모든 `fs` 모듈 직접를 작동 하지 않습니다. 파일을 만듭니다.*

### <a name="visual-studio"></a>Visual Studio

개봉박두.

## <a name="known-issues"></a>알려진 문제

다음은 해당 해결 방법) (함께 공동 작업 세션의 컨텍스트 내에서 게스트에 대 한 작업에서 방해가 될 수 있으므로 영향을 줄 수는 워크플로 확장 현재 알려진된 문제입니다.

### <a name="visual-studio-code"></a>Visual Studio Code

| 문제 | 이유 | 해결 방법 |
|-|-|-|
| Node.js를 사용 하 여 `fs` 검색/read (예: 구성 파일의 경우) 파일 또는 디렉터리를 열거 하는 모듈 (및 언어 서비스 아닌). | 게스트는 로컬 파일 액세스를 권한이 없습니다. | 1. 사용자 환경에 적절 하 게 저하 *(가능한 경우).*<br /><br />2. 사용 된 `openTextDocument` 및 `findFiles` 작업 영역 Api 읽고 파일을 열거 합니다. |
| Node.js를 사용 하 여 `fs` 모듈 파일을 작성 하거나 생성 | *위와 동일* | *해당 없음* 사용할 수는 `openTextDocument(Uri)` API를 만들기는 `untitled` 수 있지만 파일을 저장할 수는 없습니다 특정 경로에서 파일 시스템에 직접. |
| 프로젝트 번들 라이브러리 또는 도구에 따라 | *위와 동일* | 1. 번들 확장을 사용 하 여 종속성의 버전을 대체 (fallback)<br><br> 2. 전역 설치를 명시적으로 설치 하도록 선택할 경우에 게스트를 차단 해제를 지원 합니다.<br><br> 3. 원격 호스트는 사용할 수 있는 올바른 종속성을 포함 하므로 가능한 경우 상태/동작입니다. |
| Node.js를 사용 하 여 `fs` 모듈 디렉터리를 만들려면 | *위와 동일* | *해당 없음* |
| 사용 하는 문서에 기능을 제한 합니다 `file` 구성표입니다. | 게스트의 쪽 사용 시 파일을 `vsls` 구성표입니다. | 에 대 한 지원 추가 `vsls` 문서 ([예제](https://github.com/CoenraadS/BracketPair/pull/73)) |
| 사용 하는 `Uri.file` 메서드 및/또는 `Uri.fsPath` / `TextDocument.fileName` serialize/구문 분석 Uri 멤버 | *위와 동일* | 사용 하 여 `Uri.parse` 하 고 `Url.toString()` 유지 관리는 및 파일 체계를 준수 하는 대신 ([예제](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| 사용 하는 `workspace.openTextDocument` 대신 파일 경로 사용 하 여 메서드를 `Uri` | *위와 동일* | 제공 된 `Uri` 원시 파일 경로 문자열 대신 인스턴스 ([예제](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| 사용 하는 `workspace.rootPath` 영역의 현재 상태를 검색 하는 속성 | 합니다 `workspace.rootPath` 속성 호출 `Uri.fsPath` 첫 번째 `workspaceFolder` 에 `workspace`, 위에서 언급 한 동일한 문제가 있는 | 사용 된 `workspace.workspaceFolders` 속성을 대신 작업 영역의 현재 상태를 검색 하 고 필요한 경우 살펴 `workspaceFolder`의 `Uri.scheme` 로컬 인지 여부를 확인 하려면 |
| 언어 서비스를 등록 하는 경우 문서 스키마를 지정 하지 않으면 (통해는 `LanguageClient`, 또는 `languages.register*` 메서드) | 게스트 호스트와 해당 로컬 확장명 언어 서비스 결과 수신 및 따라서 두 참가자가 설치 된 동일한 언어 서비스 확장을 게스트 나타납니다 (예: 자동 완성, 코드에는 특정 작업에 대 한 중복 항목 작업) | 만 언어 서비스 제한 `file` 하 고 `untitled` 구성표 ([예제](https://github.com/vuejs/vetur/pull/756/files)) |
| 문서를 확인 안 함 `Uri.scheme` 채우기 전에 `DiagnosticCollection` 에 대 한 | *위와 동일* | 생성할 `Diagnostics` 에 대 한 `documents` 인 `Uri.scheme`  ===  `file` ([예제](https://github.com/Huachao/vscode-restclient/pull/196)) |
| 확인할 수 없는 경우 작업 영역 체계에 대 한 반환 하는 경우 `Tasks` 사용자 지정 `TaskProvider`  | 게스트 모든 원격 및 로컬 작업을 표시 하 고 따라서 표시 중복 참가자 모두 동일한 확장이 설치 되어 있으면  | 만 반환 `Tasks` 에 대 한 `WorkspaceFolder`s 인 `Uri.scheme`  ===  `file` ([예제](https://github.com/Microsoft/vscode-eslint/blob/0fdb7c74b093cae9dc08355e7235582a254f24c2/client/src/tasks.ts#L42)) |

### <a name="visual-studio"></a>Visual Studio

개봉박두.

<!--

## Extensibility API

In addition to the core goals outlined in the beginning of this document, Live Share also wants to enable extension authors to enhance the default sharing experience in the following ways:

1. Contributing to the core collaborative feature set, based on behavior that only the extension would know about. In these scenarios, the host could have an extension installed, and potentially allow guests to benefit from it without also needing to have it installed

2. Enhancing their own experiences to be collaborative (e.g. syncing bookmarks between participants), by synchronizing any custom state and UI interactions. In these scenarios, only participants that had the custom extension installed would be able to take advantage of the added collaboratively.

This will require some form of API/SDK, which extensions can use to determine if/when the end-user is within a Live Share session, and if so, light up additional capabilities. The following represents a high-level overview of some of the extension points we've identified, and look forward to getting further feedback on:

| Shared Resource | Extensibility Point(s) |
|------------------|---------------------|
| User status | 1. Retrieving the list of participants within the current Live Share session (e.g. the [Git Co-Authors](https://marketplace.visualstudio.com/items?itemName=drrouman.git-coauthors) extension could use that to populate the host's commit message with)<br /><br /> 2. Updating a participant's location (outside of just editors), as well as allowing other participant's to jump to/pin to them as they move into custom extension UI (e.g. a participant is navigating a MongoDB database using the [Azure Cosmos DB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb) extension). |
| Workspace | *N/A* - Live Share can transparently share all files, edits, cursors and highlights, without requiring an extension to do anything extra if it modified the file system and/or cursor/highlight position. |
| Language Services | *N/A* - Long-term, Live Share can transparently remote all language services (e.g. go to definition, document formatting, CodeLens) to the guest, including those that are contributed via extensions (e.g. [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)) |
| Debugging Sessions | *N/A* - Live Share can transparently remote all debugging sessions, including those that are enabled by custom extensions (e.g. [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)) |
| Servers | 1. Sharing a server that an extension was responsible for starting, and then optionally specifying whether a browser should be launched on the guest's machine as well (e.g. a debug adapter that launched a web server).  |
| Custom | 1. Synchronizing arbitrary state and/or user interactions (e.g. the [Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) extension syncing CRUD operations across participants, the [Maven for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-maven) extension exposing the project-wide view to guests) |

-->

## <a name="see-also"></a>참고자료

- [언어 및 플랫폼 지원](platform-support.md)
- [Live Share 연결 요구 사항](connectivity.md)
- [Live Share의 보안 기능](security.md)
- [모든 주요 버그, 기능 요청 및 제한 사항](https://aka.ms/vsls-issues)
- [모든 기능 요청 및 제한 사항](https://aka.ms/vsls-feature-requests)

문제가 있으신가요? [문제 해결](../troubleshooting.md)을 참조하거나 [피드백을 제공](../support.md)해 주세요.
