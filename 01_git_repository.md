# 원격 저장소(remote repository)

## 기본 설정

1. 로컬 git 저장소 준비
2. git hub repository 생성
3. Repository default branch 변경
   - 다 master라는 이름으로 따라 가도록 되어있었는데, 현재는 main이라는 이름으로 따라가게 되는데, 원격 저장소와 컴퓨터의 이름이 달라서 일치시켜줘야한다
   - github 프로필->settings -> repositories->'main'을 'master'로 변경
   - TIL(today I learned)

## 명령어

### 원격 저장소 주소 추가

```bash
# git아, 원격 저장소 주소 origin(첫 파일 이름 관례적) 이라는 추가 할건데, 주소는 이거야
$ git remote add origin https://github.com/kickandfit/github_study.git
```

### 원격 저장소 목록 

``` bash
#git아 원격 저장소 목록들 보여줘
$ git remote -v
```

### 원격 저장소 삭제

```bash
$ git remote rm origin
# git 아 원격 저장소 origin 지워줘
```

### 원격 저장소에 업로드(push)

```bash
# git아 업로드 할건데 origin이라는 이름으로 저장해둔 원격 저장소에 master 브랜치의 commit 내역들을 업로드 할거야
$ git push -u origin master
```

- commit 내역이 없으면 업로드 불가능

