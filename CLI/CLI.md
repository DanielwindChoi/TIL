# Git&Github 1 day



## Git이란?

- 코드관리를 위한 분산 버전 관리 시스템

- 무료, 오픈소스로 배포되는 개발 프로그램

  - 최신버전은 2.34.1(2021_11_24)

   

## Github란?

- Git으로 작성한 문서를 공유할 수 있는 클라우드 공간
- 허브(hub)라는 개념은 물류에서 주요한 거점을 의미함
- GIthub에서는 Git을 활용한 문서를 게시할 수 있고 각 개발자들은 자신의 포트폴리오를 관리할 수 있다.
- 기업입장에서는 오픈 소스를 공유함으로써 기술혁신을 보다 빠르게 이끌어 낼 수 있는 장점이 있다.
- 최근 마이크로소프트사에 Github를 인수함에 따라 프라이빗 개발공간도 무료화되면서 많은 개발자들이 활용하고 있는 개발 플랫폼이다.



## Git 다운받기

- 공식홈페이지에서 다운 가능
- [Git (git-scm.com)](https://git-scm.com/)



## Git을 사용하는 이유

- 일반 유저들의 경우 windows 이용자가 많음
- 그러나 개발자들의 경우 unix기반의 OS인 리눅스와 Mac을 주로 이용함
- 윈도우 OS에서도 cmd을 사용하면 도스환경을 실행할 수 있으나
- unix기반의 운영체제와 명령어가 다름
- Git에서 명령어를 입력하면 윈도우즈 환경에서 동작하도록 번역해주는 과정이 수행됨
- 따라서  Git을 활용하면 운영체제가 다른 윈도우즈 환경에서도 개발작업이 수행가능함



## Git-Bash 실행하기

- 최초 화면 실행시 화면

  - user@DESKTOP-U5POMKP MiNGW64 ~

    $

    - '~'의 의미는 '홈 폴더'를 의미
    - 기본적으로 이 '홈 폴더'에서 작업을 수행할 수 있음

  

- 기본 명령어

  - touch : 파일을 생성하라.

    ```sh
    touch bbb.txt
    touch .a.txt
    touch .hidden.txt(.이 파일 앞에 기입되면 숨긴 파일로 생성됨)
    ```

    - 명령어를 쓰고 ' '  공백을 한 칸 띄어써야 명령어로 인식함

    

  - mkdir : make directory, 폴더를 생성하라.

    ```sh
     mkdir CLI
    ```

    - 'CLI'라는 이름의 폴더를 생성

    

  - mv : 파일을 이동하라

    ```sh
    mv bbb.txt CLI/
    ```

    - CLI폴더로 bbb.txt을 옮겨라

    

  - cd : change directory, 선택한 폴더로 이동하라

    ```sh
    cd CLI # CLI 폴더로 이동하라
    cd .. # 상위 폴더로 이동하라
      - 최상위 폴더는 루트(/)라고 부름
    cd # 홈 폴더로 이동하라
    ```

    

  - l(엘)s : 그 폴더 내의 파일을 보여라

    ```sh
    ls
    ls -a # 숨겨진 파일을 포함하여 모든 파일을 보여라
    ```

    

  - rm : 삭제하라

    ```sh
    rm aaa.txt
    rm *.txt # \*별표는 와일드카드라고 부름 확장자가 .txt인 모든 파일을 삭제하라 
    rm cli # (cli-대소문자 구별X), 삭제 안됨
    rm -r # cli 폴더 삭제됨
    rm -rf .git #.git 저장소 삭제
    ```
    
    

## vscode 설치

- 구글에서 검색해서 다운받기



## typora 설치

- 지금 작업중인 환경이 typora
- 명령어를 입력하면 즉각적으로 그 효과가 반영되는 것이 눈에 보임
- typora공식사이트에서 다운 받을 수 있다.
- 최신 버전은 현재 유료화 됨, 현재 이용하고 있는 파일은 메모버전의 파일



## vscode 환경설정

최초 설치시 환경을 설정해줘야 한다.

1. 홈 폴더에 하위 폴더 생성

```
git mkdir git-practice
```



2. 이동

```
git cd git-practice
```



3. (master)를 붙이기(정확한 명칭은 추후 업데이트)

```
git init
```

.git 파일 생성, 저장소가 만들어진 개념

(주의!) 홈 폴더에 git init를 하거나 이미 master가 되어있는 상태에서 하위폴더에 다시 master설정하면 안됨!

(코린이 단계에서는 해결 불가능)



4. README.md파일을 형성한다.

```
touch README.md
```

- md파일을 열어 기록사항을 남긴다.
- crtl + s로 저장한다(저장하지 않으면 수정 표시가 나타나지 않는다)
- git status로 상태를 확인해보면 이 단계에서는 README.md 파일이 '붉게' 표시된다.



5. 그 파일을 추가한다(스테이지에 올린다)

```
git add (파일이름)
git add . (변경된 모든 파일)
```

- 커밋하기 직전 단계
- git status로 상태를 확인해보면 이 단계에서는 README.md 파일이 '초록색'으로 표시된다.



6.  스테이징된 파일을 커밋한다.

```
git commit -m '메모내용'
git commit -m 'first commit'
```

- 커밋을 해보면 이메일과 이름을 등록하지 않은 경우에 커밋이 수행되지 않는다.
- 이메일과 닉네임을 등록해라는 안내문구가 나오는데 그대로 복사해서 내용만 수정하면 된다. 현재 구체적인 명령어는 기억이 안남



7. 그 밖의 중요한 명령어

```
git status
```

- 현재 상태 확인