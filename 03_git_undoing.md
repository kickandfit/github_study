# undoing

> 원상태로 돌리기

1. 폴더 undoing 생성

   ```bash
   $mkdir undoing
   ```

   

2. undoing 폴더 안으로 작업 위치 변경

   ```bash
   $cd undoing/
   ```

   

3. un.txt, doing.txt 생성

   ```bash
   $touch un.txt doing.txt
   ```

## 1. 파일 상태를 unstage로 변경하기

### 첫번째

```bash
$ git rm --cached {file name}
```

- 따로따로 커밋하려고했는데 실수로 git add . 를 입력했을때
- 그리고 최초로 add를 한 상황( 해당 파일들에 대한 commit이 없는 경우)

### 두번째

1. un.txt, doing.txt 둘 다 commit 남기기
2. 두 파일 모두 수정사항 만들기
3. 실수로 git add . 하기

```bash
$git restore --staged {file name}
```

### 2. Modified 파일 되돌리기

- commit 기록은 남아 있고, 새롭게 수정한 다음 아직 add하지 않은 working directory에 존재하는 파일을 수정사항을 되돌린다.

```bash
$ git restore {파일명}
```

- 주의사항
  - 수정 한 내역 전부를 과거로 돌리는 것이기 때문에 수정한 내용이 사라진다
  - 절대 복원 불가능
  - 진짜진짜 수정한 내용이 마음에 안들때만 쓴다

## 3-1 Commit Message 수정

> 마지막으로 커밋하고나서 수정한게 없는 상태일때 (커밋하자마자 바로 명령 실행할 때)
>
> 커밋 메시지만 수정

```bash
$ git commit --amend
#창 들어가서 수정해
```

 	1. vim 진입
 	2. 키보드 i 혹은 insert키 입력
     - --INSERT--상태로 전환
	3. 수정 하고자 하는 commit message 입력
	4. esc키 입력
    - --INSERT--상태 취소
	5. :wq ( 저장 후 종료 write quite)

※ bash 창에서 커서기준 앞 전부 지우기 : ctrl + u 

특수문자 입력 : ㅁ+한자, 이모티콘 : 윈도우키 + .

### 3-2 커밋 할 때 파일을 빼먹었다면...

```bash
$ touch foo.txt bar.txt
$ git add foo.txt
$ git commit -m "foo & bar"

# 실수로 bar.txt를 빼먹고 commit을 한다음....
$ git add bar.txt
$ git commit --amend

# 이 과정은 새커밋을 만드는게 아니라
# 가장 최신의 커밋을 재작성 하는 것이다.
```

