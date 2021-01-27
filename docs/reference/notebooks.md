---
title: 노트북-Visual Studio Live Share | Microsoft Docs
description: 노트북 공동 작업에 Live Share를 사용 하는 방법에 대 한 자세한 정보
ms.date: 01/26/2021
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: simoncal
ms.workload:
- liveshare
ms.openlocfilehash: 40e30c77ebf3a1c339e1694c413eb8e744d576b9
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98887599"
---
# <a name="-notebooks"></a>📓 전자

노트북은 많은 개발자 및 데이터 과학자의 워크플로에 중요 한 부분이 됩니다. 풍부한 네이티브 노트 편집기를 제공 하는 Visual Studio Code을 통해 실시간 공동 작업 환경을 사용 하 여 팀과 교실에서 전자 필기장을 사용 하 고 Live Share 함께 사용 하도록 할 수 있습니다.

Live Share 노트북 환경은 현재 미리 보기로 제공 되므로 알아야 할 몇 가지 [사전 채용](#pre-requisites) 및 [알려진 문제가](#known-issues) 있습니다. 이 초기 미리 보기 릴리스를 신속 하 게 반복 하 여 평가 하는 동안 [질문/사용자 의견을 보내](http://github.com/microsoftdocs/live-share)주시기 바랍니다 주저. 👍<br />

<img width="800px" src="https://user-images.githubusercontent.com/116461/105928037-0d07a680-5ffa-11eb-8447-23bdb77fee9e.png" title="노트북 공동 작업" />

## <a name="pre-requisites"></a>필수 구성 요소

공동 작업 노트북을 시작 하려면 먼저이 미리 보기 릴리스의 일부로 다음 필수 구성 요소를 설치 해야 합니다.

| 필수 구성 요소 | Host-필요 한가요? | 게스트-필요 한가요? |
|-|-|-|
| Visual Studio 참가자 | ✅ | ✅ |
| Live Share v 1.0.3541 + | ✅ | ✅ |
| 필요한 노트북 확장 (예: Jupyter) | ✅ | 해당 _없음_ (Live Share는이 작업을 처리 합니다.) |

## <a name="getting-started"></a>시작하기

사용자와 참가자에 게 적절 한 필수 구성 요소가 있는 경우 다음 단계를 사용 하 여 Live Share 및 노트북 사용을 시작할 수 있습니다.

1. Visual Studio Code 내에서 노트북을 엽니다.
1. Live Share 세션 시작
1. 게스트가 조인 되 면 셀 편집을 시작 하 고 서로의 커서와 텍스트 강조 표시를 볼 수 있습니다.
1. 전자 필기장에 대 한 흥미로운 공동 작업을 합니다. 🎉 

## <a name="known-issues"></a>알려진 문제

다음 목록은 각각의 해결 방법과 함께 Live Share 및 노트북 experinece의 알려진 문제 집합을 나타냅니다. 

| 문제 | 해결 방법 | 
|-|-|
| "다음 모드"는 노트북 내에서 스크롤을 추적 하지 않습니다. | 전자 필기장에 대 한 적절 한 "따르기" 지원에 대해 노력 하 고 있지만, 그 동안에는 참가자와 공동 편집 하려는 올바른 노트북 셀로 수동으로 스크롤해야 합니다. |
| 참석자 간에 셀 추가/삭제/이동이 동기화 되지 않음 | 노트북 문서를 저장 하 고 모든 사람이 다시 열도록 합니다. 향후에는 노트북 수준 작업을 실시간으로 완전히 동기화 합니다. |
| 노트북 편집기는 읽기 전용 Live Share 세션을 준수 하지 않습니다. | 게스트가 노트북 셀을 편집할 수 있지만 실제로 디스크에 저장할 수는 없으며, 따라서 보안이 읽기 전용 세션으로 유지 됩니다. |
