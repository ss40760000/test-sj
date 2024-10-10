# Contribution Guidelines
여러분의 기여를 환영합니다! 이 프로젝트에 기여하는 과정을 최대한 쉽고 투명하게 만들고자 한다. 기여할 수 있는 방법은 다음과 같다.

- 버그 보고
- 코드 상태 논의
- 수정 사항 제출
- 새로운 기능 제안

## We Develop with GitHub
GitHub을 통해 코드 호스팅, 이슈 및 기능 요청 관리, 그리고 풀 리퀘스트를 수락한다.

## 문서 작성 및 관리 가이드라인

### 문서 작성 도구
대부분의 설계 문서는 마크다운(Markdown; *.md) 형식을 사용한다.
마크다운 문서를 작성하기 위해 사용한 도구목록은 아래와 같다.
| 도구 | 용도       | 비고                   |
| ------- | ---------- | ------------------------- |
| Visual Studio Code  |  마크다운, PlantUML 편집 및 PDF 빌드 |            |
| PlantUML  | UML 다이어그램 작성 |       |
| yEd  | UML 외 다양한 다이어그램 작성 |          |


### 다이어그램 작성 방법

**- PlantUML 사용**
<br>
마크다운 내에 PlantUML 다이어그램을 삽입하는 방법은 다음의 두 가지가 있다.
1. 별도의 파일(*.puml)로 UML을 작성하고, 이미지로 export한 다음 마크다운에 이미지로 import
2. 마크다운 내에 코드 직접 작성

<br>

**- yEd 사용**
<br>
PlantUML이 코딩하는 것과 같이 텍스트로 다이어그램을 그리는 것인 반면, yEd는 파워포인트와 같이 여러 도형과 선을 마우스로 편집하여 다이어그램을 그리는 방식이다. yEd로 작성한 다이어그램은 svg, png, jpg 등 다양한 형식의 이미지로 출력하여 마크다운 문서에 삽입할 수 있다.


### 문서 구조

Repository는 docs의 각 디렉토리명에 해당하는 문서가 md파일로 작성되어 있고
하위 디렉토리에는 다음과 같이 구성되어 있다.

```
XXXX.md
 - /graphml - yEd로 작성한 .graphml 파일
 - /images - yed, puml로 작성한 다이어그램을 이미지로 변환한 png, svg등 파일
 - /plantuml - PlantUML로 작성한 .puml 파일
```
* md 파일에 삽입되는 이미지는 graphml과 plantuml에서 작성한 파일의 이력관리를 위하여
동일한 파일이름으로 export하여 사용한다.
즉 하나의 이미지는 하나의 graphml이나 plantuml 파일과 매칭된다.


### 문서 수정 예시

docs/architecture의 Software Architecture.md의 수정사항이 발생하는 경우
 1. 4.8 Notification Service의 내용 작성
 2. yEd로 Notification Service의 구성도 작성 추가 (graphml/308.component_notification_service.graphml)
 3. .graphml을 svg로 export하여 추가 (images/308.component_notification_service.svg)
1. md 파일에 해당 내용 작성 및 이미지 삽입 

```
### 4.8. Notification Service
notification service에 대한 설명 작성 // 내용 작성
![](images/308.component_notification_service.svg) // 이미지 삽입
```
<br>

## We Use Gitflow, So Code Development Follows a Structured Process
우리는 [Gitflow](https://nvie.com/posts/a-successful-git-branching-model/)를 사용하여 개발을 관리한다. 모든 코드 변경 사항은 풀 리퀘스트를 통해 통합되며, `develop`, `feature`, `release`와 같은 여러 브랜치를 사용한 개발 워크플로를 따릅니다. 기여하는 방법은 다음과 같다.

1. 원격 레포지토리의 `develop` 브랜치에서 내 계정의 레포지토리로 **Fork** 한다.
2. **기능을 개발**하고, 코드가 테스트되었는지 확인한다.
3. 필요하다면 **문서**를 업데이트하여 변경 사항을 반영한다.
4. 모든 테스트가 통과하고, 코드가 우리의 코딩 스타일 및 린팅 규칙을 준수하는지 확인한다.
5. 작업이 완료되면, `develop` 브랜치로 **pull request**를 제출한다.
6. pull request를 작성할 때 적절한 **reviewer**를 지정하여 코드 변경 사항을 검토받는다.  
   **reviewer**는 코드베이스에 익숙한 사람을 선택하는 것이 좋으며, 그들이 피드백을 제공할 수 있는 시간을 고려해 선택한다.
7. 또한 **assignees**를 지정하여 작업의 책임을 명확하게 한다.  
   **레포지토리의 모든 maintainer**를 pull request의 **assignees**로 지정하여 변경 사항에 대한 책임과 리뷰 프로세스의 원활한 진행을 보장해야 한다.

> **참고**: Assignees는 pull request가 적절히 리뷰되고 병합될 수 있도록 책임을 진다. 모든 maintainer를 assignees로 지정하는 것은 변경 사항을 인지하고 신속하게 대응할 수 있도록 하는 중요한 절차이다.

## Reporting Bugs Using GitHub Issues
우리는 GitHub 이슈를 통해 버그를 추적한다. [새 이슈 열기](issues)를 통해 쉽게 버그를 보고할 수 있다.

### Writing a Good Bug Report
**좋은 버그 보고서**에는 다음 사항이 포함되어야 한다.
- 문제에 대한 간단한 요약 또는 배경 설명.
- 버그를 재현할 수 있는 단계 (구체적이고 자세히 설명).
- 기대했던 결과와 실제 결과.
- 문제를 식별하는 데 도움이 될 수 있는 추가 정보 또는 참고 사항.

## 기여자 라이선스 계약 (CLA)
풀 리퀘스트를 수락하기 전에, 최초 한번 CLA를 제출해야 한다. CLA 전문은 여기서 확인 할 수 있다. [기여자 라이선스 계약](CLA.md).

## Coding Style
우리의 코딩 스타일은 [OpenDID 코딩 스타일](https://github.com/OmniOneID/did-doc-architecture/blob/main/docs/rules/coding_style.md)을 따른다. 이를 준수하면 코드가 일관되고 읽기 쉬우며 유지 보수가 용이해진다.

## Commit Message Guidelines
우리의 커밋 메시지는 [OpenDID 커밋 규칙](https://github.com/OmniOneID/did-doc-architecture/blob/main/docs/rules/git_code_commit_rule.md)을 따른다. 명확한 커밋 메시지는 변경 사항의 의도를 파악하는 데 도움을 주며 코드 히스토리를 쉽게 탐색할 수 있도록 한다.

## License
Copyright 2024 RaonSecure
