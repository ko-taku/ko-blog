# 20250211 TIL 

## 버전 관리 시스템 (Version Control System)

**버전 관리 시스템** : 작업한 내용을 보존하고, 과거 상태로 돌아갈 수 있는 도구입니다. 이를 통해 다음과 같은 기능을 제공한다:

- 파일이 변경되면 변경 이력을 저장
- 이전 버전으로 돌아갈 수 있다
- 어떤 변경 사항이 발생했는지 쉽게 알 수 있다

### Commit 단위로 관리
- 관리된 파일은 **GitHub**, **GitLab**, **Bitbucket**과 같은 원격 저장소를 활용해 안전하게 백업하고, 팀원들과 효율적으로 협업할 수 있다

## Git

**Git** : 개발자 코드를 효율적으로 관리하기 위해 만들어진 분산형 버전 관리 시스템

- Git은 날짜별로 어떤 파일이 어떤 내용으로 변경되었는지를 기록
- **스냅샷**: 특정 시점의 상태를 저장
- **Commit**: 스냅샷을 생성하는 작업
- Git의 **commit** 기능을 통해 변경 사항을 추적하고, 과거의 상태로 되돌릴 수 있다

## Git 호스팅 서비스

**Git 호스팅 서비스** : Git의 기본 기능(버전 관리)을 바탕으로 협업과 프로젝트 관리 도구를 통합한 플랫폼. **GitHub**가 대표적

### 주요 기능
- **원격 저장소(Remote Repository) 제공**  
  - Git 저장소를 클라우드에 호스팅하여 팀원들이 파일을 공유하거나 협업할 수 있도록 지원
  - 모든 변경 사항과 버전을 중앙에서 관리

- **협업 도구**
  - **Pull Request / Merge Request**: 팀원이 작업한 내용을 저장소에 병합하기 전, 리뷰 및 승인 과정을 거침
  - **코드 리뷰**: 팀원들이 변경된 코드에 대해 댓글을 달거나 개선점을 제안할 수 있다
  - **이슈 트래킹**: 프로젝트에서 발생한 버그나 추가해야 할 기능을 관리하고 작업 우선순위를 정할 수 있는 도구

- **프로젝트 관리 기능**
  - **칸반 보드**(Trello와 유사): 작업 상태(진행 중, 검토 중, 완료)를 시각적으로 관리
  - **이슈 연결**: 특정 작업(Pull Request 등)과 관련된 이슈를 연결해 작업 진행 상황 추적
  - **CI/CD (Continuous Integration / Continuous Deployment)**: 자동 빌드, 테스트, 배포 프로세스를 설정하여 개발 생산성 향상
  - **보안 및 권한 관리**: 저장소 접근 권한을 팀원별로 설정 가능(읽기/쓰기/관리 권한)

## Git과 GitHub의 차이

- **Git**: 소스 기록을 관리하고 추적할 수 있는 분산 버전 관리 시스템
- **GitHub**: Git 저장소를 호스팅하는 클라우드 기반 플랫폼

Git을 사용해 버전을 관리하는 폴더를 GitHub를 통해 여러 사람이 공유하고 접근할 수 있다

## 오픈 소스 (Open Source)

**오픈 소스**는 소프트웨어의 소스 코드가 공개되어 누구나 열람, 수정, 배포할 수 있는 소프트웨어 개발 방식

ex) **비트코인**은 오픈 소스로 개발

## 중앙 집중형 버전 관리 시스템 (CVCS)

- 모든 데이터(코드, 변경 이력 등)를 **중앙 서버**에 저장
- 모든 사용자가 동일한 **중앙 서버**를 이용하므로 변경 사항 추적이 명확
- **중앙 서버**에 문제가 생기면 데이터 복구가 어렵다

## 분산형 버전 관리 시스템 (DVCS)

- 모든 개발자가 **로컬 저장소**에 전체 데이터(코드, 변경 이력 등)를 복사
- **중앙 서버**가 손상되더라도 각 로컬 저장소에 데이터가 복제되어 있어 복구가 용이
- 여러 개발자가 작업을 병합하기 전까지 **로컬 저장소 간 데이터**가 불일치할 수 있다

## Git 설치

- **macOS**는 기본적으로 **Git**이 설정되어 있다
- 하지만 맥에서 제공되는 Git은 **Xcode Command Line Tools**에 포함되어 있으므로 **Git**을 사용하려면 Xcode 명령줄 도구를 설치해야 한다

## Git 워크플로우

### 1. Working Directory (작업 디렉토리)
- 현재 로컬에서 작업 중인 실제 파일들이 위치하는 공간
- 파일이 수정되면 **Git**은 이를 추적하지만 아직 Git 저장소에 반영되지 않은 상태

### 2. Staging Area (스테이징 영역)
- **commit**하기 위해 준비된 파일들이 임시로 저장되는 공간
- **Git add** 명령으로 수정된 파일을 스테이징 영역에 추가

### 3. Repository (저장소)
- **Git**이 관리하는 데이터베이스
- **Git commit** 명령으로 스테이징 영역의 파일이 저장소에 반영되고 변경 이력이 기록

## Git 워크플로우 기본 흐름

1. **작업 디렉토리에서 파일 작성 및 수정**
    - 파일 상태는 **Untracked**(Git에서 관리하지 않는 파일) 또는 **Modified**(수정된 파일)로 표시

2. **변경된 파일을 스테이징 영역에 추가**
    - 변경된 파일을 **commit** 준비 상태로 만든다
    - **Git add** 명령어를 사용하여 스테이징 영역에 추가

3. **커밋하여 저장소에 반영**
    - 스테이징 영역에 있는 변경 사항을 저장소에 기록
    - **Git commit** 명령으로 변경 사항과 함께 메시지를 작성

4. **원격 저장소에 푸시**
    - 원격 저장소에 변경 사항을 업로드하여 팀원과 공유
    - **Git push** 명령으로 원격 저장소에 반영

## Branch

### 독립적인 작업 공간
- 브랜치를 생성하면 **메인 코드**(main or master)와 별개로 독립적인 복사본에서 작업을 진행
- 이로 인해 기존 코드에 영향을 주지 않고 새로운 작업을 수행

### 경량화된 포인터
- **Git**에서 브랜치는 특정 **commit**을 가리키는 포인터
- 새로운 **commit**이 추가되면 브랜치는 자동으로 해당 **commit**을 가리키도록 이동

### 기본 브랜치와 병렬 브랜치
- **기본 브랜치**: 일반적으로 프로젝트의 주요 작업은 **main** 또는 **master** 브랜치에서 이루어진다
- **병렬 브랜치**: 기능 개발(feature), 버그 수정(fix), 실험 작업 등 다양한 목적을 위해 별도의 브랜치를 생성하여 사용

## Git 태그

- **tag**는 Git의 특정 커밋을 가리키는 읽기 전용 참조
- 태그는 릴리스 버전을 표시하기 위해 사용

### Git 태그의 주요 특징
- **특정 커밋에 고정**: 태그는 특정 커밋을 가리킨다
- **읽기 전용**: 
  - 태그는 수정되지 않으며, 삭제 후 다시 만들어야 한다
- **버전 관리**: 
  - 소프트웨어 주요 버전이나 핫픽스 버전을 표시하는데 사용

### Git 태그 유형
1. **Annotated Tag (주석 태그)**  
   - 태그에 작성자, 날짜, 주석 메시지를 포함할 수 있다
   - Git DB에 저장되면 서명(GPG)도 가능
   - 생성 명령어:  
     ```bash
     git tag -a v1.0.0 -m "Initial release"
     ```

2. **Lightweight Tag (경량 태그)**  
   - 주석 없이 commit을 가리키는 단순한 태그
   - 브랜치처럼 동작, 메타데이터가 포함되지 않는다
   - 생성 명령어:  
     ```bash
     git tag v1.0.0
     ```

### 태그 사용법
- **태그 생성**  
  - Annotated 태그
    ```bash
    git tag -a v1.0.0 -m "First release"
    ```
  - Lightweight 태그
    ```bash
    git tag v1.0.0
    ```

- **태그 확인**  
  - 모든 태그 보기  
    ```bash
    git tag
    ```
  - 특정 패턴에 해당하는 태그 보기  
    ```bash
    git tag -l "v1.*"
    ```

- **태그 삭제**  
  - 로컬 태그 삭제  
    ```bash
    git tag -d v1.0.0
    ```
  - 원격 태그 삭제  
    ```bash
    git push origin --delete v1.0.0
    ```

- **태그 푸시**  
  - 특정 태그 푸시  
    ```bash
    git push origin v1.0.0
    ```
  - 모든 태그 푸시  
    ```bash
    git push origin --tags
    ```

- **태그로 체크아웃**  
  - 태그를 기준으로 commit 상태를 확인 
    ```bash
    git checkout v1.0.0
    ```
    
### 버전 관리를 위한 태그 활용
- 태그 이름에 **시멘틱 버전(Semantic Versioning)**을 따르는 것이 일반적  
  - 형식: `major.minor.patch` (예: `v1.2.3`)
    - **Major**: 호환되지 않는 변경 사항
    - **Minor**: 새로운 기능 추가
    - **Patch**: 버그 수정

- **릴리스 관리**:  
  - 주요 릴리스, 핫픽스, 베타 버전 등에서 태그를 붙여 릴리스 관리를 체계적으로 수행

---

## GitHub로 프로젝트 관리 실습

### 1. Git Repository 생성
- 깃허브에서 **New** 버튼을 클릭하여 repository의 이름을 정하고 생성

### 2. 로컬 저장소로 복제(Clone)
- Repository 주소를 복사
- 터미널을 실행하고 폴더를 선택 (cd로 이동)
- 복사한 주소를 붙여넣어 **git clone (복사한 주소)** 실행

### 3. VSCode에서 로컬 작업
- **VSCode**를 실행시켜 해당 레포지토리를 연다 (`Command + O`)
- 파일이 아닌 **폴더**를 선택 후 열기
- VSCode의 터미널을 이용하여 **public.txt**와 **private.txt** 파일 생성
- **Touch .gitignore** 명령어를 실행
- `.gitignore` 안에 Git이 관리할 필요 없는 파일을 설정
- `Command + S`로 저장

### 4. Git을 이용해 클라우드 저장소에 보내기
- 어떤 **Staging Area**에 저장할 것인지 확인
- **Git status**로 어떤 파일이 저장되지 않았는지 확인
- **add**로 파일을 스테이징 영역에 올리기
    - `git add (파일 이름)`, `git add .` (모든 파일을 한번에 올리는 방법)
- Add 후 **git status**로 스테이징 영역에 저장이 잘 되었는지 확인
- **config user.name**, **config user.email** 확인과 설정
- **Add** 되어있다면 `git commit -m ‘(메세지 내용)’`으로 **commit** 진행
- **Git push origin main** (브랜치 이름)으로 **Push**한다
- Repository에 저장 완료

### 5. 충돌
- **GitHub** 페이지에서 **public.txt**를 수정하여 **Commit Changes**로 **Commit** 진행
- 로컬의 **public.txt** 내용도 변경
- **Add**, **Commit**, **Push** 진행
- **Push** 시 경고 메시지가 표시됨 (원격 저장소와 로컬이 달라서 경고)
- 이를 해결하기 위해 원격 저장소와 로컬의 내용 동기화가 필요
    - `git fetch --all` 또는 `git pull origin main`으로 원격 저장소의 내용을 가져온다
    - `git fetch --all`: 모든 원격 저장소 최신화
    - `git pull origin main`: 원격 저장소 origin의 main 브랜치 코드 가져오기
    - **Git pull** 시 로컬 코드와 다르다고 안내
    - `git pull origin main --no-rebase`로 수정
    - 수정에 맞는 부분을 선택 후 저장 (`resolve in merge editor` -> `complete merge`)
    - **Git status**로 **public.txt**가 수정된 상태로 **commit**을 기다리고 있는 것을 확인
    - **Commit**, **Push** 진행

### 6. 브랜치
#### 구조 설정
- **main**: 실제 서비스가 구동되는 브랜치
- **dev**: **main**에 **merge**하기 전에 테스트하는 브랜치
- **feature#1, feature#2**: 각 개발자들이 작업하는 브랜치

#### 브랜치 관리
- **Main** 브랜치를 최신 상태로 업데이트 (fetch, pull)
- **Dev** 브랜치를 만들어준다: `git checkout -b dev`
- **Main** -> **dev**로 브랜치 변경 후 **Push**로 원격 저장소에 올린다
- `git checkout -b feature#1` 브랜치 생성 후 **Push**로 원격 저장소에 만들어준다
- `git checkout dev`로 **dev** 브랜치로 이동
- **feature#2** 브랜치 생성: `git checkout -b feature#2`
- **Push** 진행 후 **GitHub** 페이지에서 새로고침하여 브랜치 확인

### 7. PR(Pull Request) 진행하기
- **feature#1**, **feature#2** 내용 변경 후 **Add**, **Commit** 진행
- **Push** 진행: `git push origin feature#1, feature#2`
- **GitHub** 페이지에서 **Pull requests** 탭에 들어가서 **New pull request** 클릭
- **feature#1**을 **dev**로 **merge**: **Create Pull request** 버튼을 눌러 PR 생성
- **Create pull request** -> **Merge pull request**를 통해 **Merge**
- **feature#1** 코드가 **dev** 브랜치로 머지

### 8. 브랜치 충돌 해결하기
- **feature#2** 브랜치에서 PR 진행
- 자동 머지가 되지 않는 경고가 뜨지만 **PR**을 생성하여 처리
- **Conflict**를 해결하고 진행
    - **VSCode**에서 **dev** 브랜치로 이동 후 원격 저장소의 최신 코드를 받아온다
    - **feature#2**로 이동 후 **dev** 코드를 **Merge**
    - **Conflict** 처리 후 **feature#2** 작업을 채택
    - **Commit**, **Push** 진행 후 원격 저장소에 올린다
    - **GitHub PR** 페이지에서 **Merge** 버튼 활성화 후 **Merge** 진행
    - 마지막으로 **main <- dev** 브랜치로 완료된 코드를 PR 생성하여 완료

---
