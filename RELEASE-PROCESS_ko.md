# Release Process

이 문서는 본 프로젝트의 Release Process에 대해 설명하며, QA 검증 및 Release 버전 관리를 원활하게 수행하는 절차에 대해 설명한다.

## Versioning

프로젝트는 "X.Y.Z" 형식의 버전 규칙을 따른다.

- X (Major): 하위 호환이 되지 않는 주요 변경 사항
- Y (Minor): 하위 호환이 유지되는 새로운 기능 추가
- Z (Patch): 하위 호환이 유지되는 버그 수정 및 소규모 개선 사항

> Major 버전이 업데이트되면 Minor와 Patch는 0으로 초기화된다.
> <br>
> Minor 버전이 업데이트되면 Patch는 0으로 초기화된다.

## 새로운 버전을 위한 Release 절차

1. Change Log 검토  
   [CHANGE LOG](CHANGELOG.md) 페이지를 확인하여 이번 Release에 포함될 변경 사항이 모두 기록되어 있는지 검토한다.

2. Release 브랜치 생성  
   QA 검증을 위해 아래의 절차로 GitHub 페이지에서 "release/QA-VX.Y.Z" 브랜치를 생성한다. (ex: release/QA-V1.0.0)
   - 저장소의 메인 페이지에서 브랜치 드롭다운 메뉴를 클릭하고 현재 "develop" 브랜치를 선택한다.
   - develop 브랜치로 변경되면 브랜치 드롭다운 메뉴를 클릭하여 "Find or create a branch" 입력란에 "release/QA-VX.Y.Z"를 입력한다.
   - 나타나는 "Create branch: release/QA-VX.Y.Z from develop" 옵션을 클릭하여 브랜치를 생성한다.

3. QA 검증  
   Release 브랜치에서 QA 검증을 수행하고, QA 검증 중 발견된 이슈에 대해 수정사항을 반영한다. QA 검증이 끝나면 Release를 승인한다.

4. main 및 develop 브랜치에 병합  
   QA 검증 완료한 release/QA-VX.Y.Z 브랜치의 버전을 main 및 develop 브랜치에 병합한다.

5. GitHub Action을 통한 Release  
   main에 release 버전이 병합되면 CI/CD 파이프라인이 트리거되어 해당버전으로 태깅 후 아래 항목을 포함하여 자동으로 GitHub에 Release를 게시한다. 
   - 버전명(태그)
   - 변경 로그 요약
   - 소스 코드 압축본
   - 배포 파일
