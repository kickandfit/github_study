# CLI

- -은 앞에 목록 형태를 나타 낼 수 있다.
- `백틱 3개는 코드 블락을 생성 할 수 있다.

## ls(list)

- ls 명령어는 현재 작업중인 위치에 존재하는 파일 혹은 폴더 목록을 보여준다.

```bash
moonwh@DESKTOP-PAH2QMK MINGW64 ~/Desktop/github_study
$ ls
text.txt test_folder/
```

## cd(change directory)

- 현재 작업중인 디렉토리(a.k.a. 폴더)를 변경한다.

```bash
moonwh@DESKTOP-PAH2QMK MINGW64 ~/Desktop/github_study
$ cd
moonwh@DESKTOP-PAH2QMK MINGW64 ~
$ cd Desktop/github_study/
moonwh@DESKTOP-PAH2QMK MINGW64 ~/Desktop/github_study
$ cd .. # 내 상위 폴더로 이동
```

- cd는 최상위 폴더로 이동

- 어느정도 이름만(des정도)만 치고 tab 누르면 자동완성됨
- ..은 내 상위 폴더를 나타내며 . 은 내 현재 위치를 나타낼때

##  mkdir(make directory)

```bash
moonwh@DESKTOP-PAH2QMK MINGW64 ~/Desktop/github_study
$ mkdir {directory name}
```

## touch

- 파일을 생성한다.

```bash
moonwh@DESKTOP-PAH2QMK MINGW64 ~/Desktop/github_study
$ touch {file name}.{확장자}
```

## rm

- 파일을 지운다.

```bash
moonwh@DESKTOP-PAH2QMK MINGW64 ~/Desktop/github_study
$ rm {name}
```

