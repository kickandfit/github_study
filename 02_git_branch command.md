# branch command

`-` if, branch login을 만들었다면, login 이라는 작업환경에서만 작업가능

`-` branch master를 건드리지 않음

`-` 같은 파일을 동시에 수정하고 올릴때 충돌이 발생하는 것을 방지해줌

- branch 생성
  - branch 생성 시기의 모든 자료는 가지고옴
  - 상황 
    1. master라는 branch에 작업내용이 있었음
    2. branch login을 만들었음
    3. master의 작업내용이 login branch에 들어있음

```bash
$ git branch {branch name}
```

- branch 목록

```bash
$ git branch
```

- branch 이동

```bash
# git checkout 까지만 입력한 상태에서
# tab*2 -> checkout 가능한 브랜치명 확인 가능 
# 내부+repository의 모든 목록
$ git checkout {branch name}
(branch name) $
```

```bash
$ git log --oneline
7a34c4d (HEAD -> master, origin/master, origin/HEAD) 210625 | updated_command_word_pull
#head는 현재 위치를 나타냄
# $ git log --all --oneline 은 모든 branch log를 보여줌

```

```bash
$ git log --all --graph --oneline
# '/' login branch가 생성된 시점 (가지로 보여줌)
# '|' master brach가 수정하고 있는 내역을 보여줌
```

- branch 생성+이동

```bash
$ git checkout -b {branch name}
```

- branch 병합
  - 'i' 키를 누르면 수정 상태로 바뀜
  - 'esc'키를 누르면 종료가됨
  - '#' 주석처리
  - ':wq' 저장후 종료( 하단 insert가 없어진 상태에서) , ':q' 종료

```bash
(master) $ git merge {branch name}
# (master)$ git merge login
# (master에서)git아 합쳐줘 {branch name}에 있는 수정사항을
# 뜨는 창 맨 윗 줄이 commit message
```

​	반드시 master 브랜치에 브랜치를 병합

- 브랜치 삭제
  - 작업 완료후 삭제를 해줘야 관리하기 편함

```bash
$ git branch -d {branch name}
```

- 브랜치 강제 삭제
  - merge가 되지 않은 브랜치는 강제로 삭제해야 함

```bash
$ git branch -D {branch name} 
```

## 3가지 병합 상황

### 1. fast-foward

"다른 브랜치 생성 한 후, master 브랜치에 변경 사항이 없을 때"

- 생성된 브랜치에는 작업을하고
- 기존 master 브랜치에서 작업을 하지 않았을 때 나타남

### 2. 3-way Merge

"현재 브랜치(master)가 가르키는 커밋이 Merge 할 브랜치의 조상이 아니라면 깃은 현재 브랜치와 머지할 브랜치의 커밋 2개와 두 브랜치의 공통조상 하나를 사용한다."

#### 1. 새로운 브랜치 signup 생성

#### 2. signup 브랜치에서 signup.py 생성

- git add, commit 잊지 말기

#### 3. master 브랜치에서 new folder 생성

#### 4. master 브랜치와 signup 브랜치 병합

#### 5. signup 브랜치 삭제

### Merge Conflict

"두 개의 브랜치가 동일한 파일의 동일한 위치를 수정하고 merge 하려고 할 때 발생하는 현상

단, 동일 파일을 수정했다고 하더라도 서로 다른 영역을 수정한다면 merge conflict는 발생하지 않는다"

- git이 자동으로 병합하지 못하는 상황

1. 새로운 브랜치 hotfix 생성
2. hotfix 브랜치 b.txt에 새로운 내용 입력
   - git add, commit
3. master 브랜치에서 b.txt에 새로운 내용 입력
   - git add, commit
4.  master 브랜치와 hotfix 브랜치 병합

