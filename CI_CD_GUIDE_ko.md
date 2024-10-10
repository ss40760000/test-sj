# CI/CD 파이프라인 가이드

이 문서는 Github Actions를 사용하여 CI/CD 파이프라인을 설정하는 방법을 설명한다. CI는 프로젝트 빌드와 테스트 실행에 중점을 두고, CD는 JAR 파일 패키징과 배포를 처리한다. 이 파이프라인은 Pull Request가 승인된 후에 자동으로 실행된다.

## 사전 준비

파이프라인을 설정하기 전에 다음 사항을 확인한다:
1. Github에 프로젝트 리포지토리가 준비 되어 있어야 한다.
2. 프로젝트에 테스트와 빌드 프로세스가 정의되어 있어야 한다.
3. Github Actions를 설정할 수 있는 권한이 있어야 한다.

## Github Actions 생성 및 수행 프로세스

### 1단계: CI GitHub Action 생성

1. 리포지토리 내에 `.github/workflows/ci.yml` 경로에 새로운 GitHub Actions workflow 파일을 생성한다.
2. 이 파일에 Pull Request가 생성될 때 트리거되는 CI 파이프라인을 정의한다.

### 2단계: CD GitHub Action 생성

1. 리포지토리 내에 `.github/workflows/cd.yml` 경로에 또 다른 workflow 파일을 생성한다.
2. 이 파일에 Release 버전이 생성되고 main 브랜치에 병합될 때 트리거되는 CD 파이프라인을 정의한다.

### 3단계: Pull Request 제출 시 CI 프로세스

1. Pull Request 생성
   - 변경 사항을 `develop` 브랜치로 병합하기 위해 Pull Request를 생성한다.

2. 자동 CI 수행
   - Pull Request가 제출되면 GitHub Actions가 자동으로 CI 프로세스를 트리거한다.
   - Gradle을 사용하여 프로젝트를 빌드하고, 정의된 테스트 케이스를 실행하며 결과를 출력한다.

3. Pull Request 승인
   - 팀원이 PR을 리뷰하고 승인한다. 이 단계에서 코드 품질과 기능이 적절한지 확인한다.

### 4단계: Release 버전을 위한 CD 프로세스

1. QA 검증을 위한 Release 브랜치 생성
   - QA 검증을 위한 Release 브랜치를 생성하고, 해당 브랜치에서 QA 검증을 수행한다.

2. 자동 CD 수행
   - QA 검증이 완료된 Release 브랜치가 `main` 브랜치로 병합될 때 CD 프로세스가 자동으로 시작된다.
   - 최종 배포 파일을 생성하고, 새로운 Release를 자동으로 생성하여 Release Note와 함께 버전 정보를 기록한다.
   - 생성된 배포 파일을 GitHub Releases에 업로드한다.

이 설정은 각 PR 병합 후 코드가 자동으로 테스트되고 배포되는 프로세스를 보장한다. workflow는 Github Actions를 사용하여 CI/CD를 수행하며, 배포 파일을 Github Releases에 자동으로 업로드한다. 이를 통해 개발자는 보다 효율적으로 코드를 관리하고 배포할 수 있다.
