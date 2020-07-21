# Git

>  Git은 분산 버전관리시스템이다.

## 준비하기

윈도우에서 Git을 활용하기 위해서 [git bash](https://git-scm.com/downloads)를 설치한다.

초기 설치를 완료한 이후에, 계정 설정을 진행한다.

```sh
$git config --global user.email {email@address}
$git config --global user.name {username}
```



# 로컬 저장소 활용하기

## 1. 저장소 초기화

> 이제부터 이 디렉토리를 git으로 관리하겠다! (변경 이력을 감시하겠다)

```sh
$ git init
```

- `.git`디렉토리가 생성되며, 여기에 git과 관련된 모든 정보가 저장됩니다.
- 초기화를 하고나면 git bash에 `(master)`라고 표시가 되는데, 이는 이 디렉토리는 이미 git이 관리하고 있다는 뜻으로 생각할 수 있다.
- 이미 초기화 한 repository에서는 다시 `git init`을 하지 않는다.



## 2. add(무대에 오르기)

> working directory 작업공간에서 변경된 사항을 이력으로 관리하기 위해서는 반드시 staging area를 거쳐야 한다. (사진을 찍기 위해서 무대위로 올라가야한다.)

```sh
$ git add {file to stage}
# 디렉토리의 모든 파일 올리기
$ git add . 
```

## 3. Commit(사진 찍기)

> 이력을 확정 짓는, 즉 기록을 남기는 명령어

```sh
$ git commit -m 'commit message'
```

commit log를 확인하고 싶다면, 아래의 명령어를 참고

```sh
$ git log
```

## 4. Status

> git을 쓰면서 가장 많이 사용해야 하는 명령어. 현재 상황을 확인할 수 있다.

```sh
$ git status
```

# 원격 저장소 활용하기

> 여러 서비스 중, [github](https://github.com/)을 기준으로 설명한다.

## 1. 준비사항

- github에 회원가입 후, 빈 reposiory를 만들어 둔다.

## 2. 원격 저장소 등록

- 로컬 저장소와 원격 저장소를 연결하는 일이다.

  ```sh
  $ git remote add origin { github repository url}
  ```

- 원격 저장소(remote)를 등록할건데, `origin`이라는 이름으로 원격 저장소를 등록하겠다는 의미

- 원격 저장소 등록 현황을 확인하려면 아래의 명령어를 참고해야한다.

  ```sh
  $ git remote -v
  ```

### 3. 원격 저장소에 파일을 업로드하기

- 파일을 업로드 하는 방법은 다음과 같다.

  ```sh
  $ git push origin master
  ```

  

### 4. 원격 저장소 삭제

- 등록된 원격 저장소를 삭제하려면 아래의 명령어를 참고해야한다.

  ```sh
  $ git remote rm origin
  ```

### 5. 원하는 로컬 저장소에 다운로드하기

-  Github이나 Gitlab의 원격 저장소에서  파일을 다운로드 하기 위해서는 repo url를 가지고  명령어를 입력해야한다.

  ```sh
  $ git clone {https:\\url}
  ```

  

  

