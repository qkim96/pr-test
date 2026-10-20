# pr-test

- Step 1. 현재 브랜치 확인하기

`git branch`

- 원격 저장소의 브랜치까지 확인

`git branch -a`

- Step 2. 새로운 브랜치 만들기

`git switch -c feature/login`

이 명령어는 두 가지를 한 번에 해.

    feature/login이라는 브랜치를 생성한다.

    생성한 브랜치로 이동한다.

    git checkout -b feature/login도 사용할 수 있지만, 처음 배운다면 역할이 명확한 git switch를 추천해

- Step 3. 코드 수정 후 저장하기

```
git status
git add .
git commit -m "feat: add login feature"
```

- Step 4. GitHub에 브랜치 올리기

`git push -u origin feature/login`

이 명령어를 실행하면 feature/login 브랜치가 GitHub 원격 저장소에 올라가.

    origin: 일반적으로 GitHub 저장소를 가리키는 원격 저장소 이름

    feature/login: 업로드할 브랜치 이름

    -u: 이후 같은 브랜치에서 git push, git pull을 편하게 사용하도록 연결 설정

    여기서 -u는 로컬 브랜치와 원격 브랜치를 연결하는 옵션이야. 한 번 연결해 두면 이후에는 보통 다음만 입력하면 돼. git push

여러 원격 저장소가 있다면?

예를 들어 내 GitHub 저장소와 원본 프로젝트 저장소를 동시에 연결할 수도 있어.
bash

git remote add origin https://github.com/me/project.git  
git remote add upstream https://github.com/team/project.git  

    origin: 내가 작업하는 저장소

    upstream: 원본 프로젝트 저장소

git remote -v

결과 예시:
text

origin  https://github.com/user/project.git (fetch)  
origin  https://github.com/user/project.git (push)

- Step 5. Pull Request(PR) 만들기

GitHub 저장소에 접속하면 방금 올린 브랜치로 Pull Request를 생성할 수 있어.

- Step 6. 병합 후 브랜치 정리하기

```
git switch main
git pull origin main
git branch -d feature/login


Git의 브랜치는 폴더를 복사하는 기능이 아니라, 특정 커밋을 가리키는 포인터에 가까워.