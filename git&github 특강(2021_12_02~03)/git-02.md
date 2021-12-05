# Git&Github 2 day

## 혼자 작업시 conflict 해결하기

2개 이상의 컴퓨터에서 같은 원격 저장소 사용시(예, 강의장 컴퓨터 & 본인 노트북)

1. `$ git add .`

2. `$ git commit -m '메세지'`

3. `$ git push origin master`

   1. 된다  => 8번으로

   2. 안된다  => 4번으로

      ```
      hint: Updates were "rejected" because the tip of your 
      current branch is behind
      hint: its remote counterpart. Integrate the remote changes (e.g.
      hint: '"git pull" ...') before pushing again.
      hint: See the 'Note about fast-forwards' in 'git push --help' for details.
      ```

4. `$ git pull origin master`

   1. 자동 병합(auto merge)이 일어난다 => 8번으로

      - `$ git status` 에 아무런 알림이 없다.

   2.  자동 병합에 실패 => 5번으로

      ```
      ...
      Automatic merge failed; fix conflicts and then commit the result.
      ...
      ```

5. `vsvode` 에서 직접 빨간 불 들어온 파일을 수정한다.

   - 같은 파일, 같은 라인 등에 충돌하는 내용이 있는 경우임

   - 해결책

     - 둘 중 하나 택일

     - 둘 다 택하기

     - 아예 새로 코드 짜기

6. `$ git add .`

7. `$ git commit -m '충돌 해결'`

   - 'Merge is completed' <= 아칸 합체시 나오는 말..ㅋㅋ

8. `$ git psh origin master`



## branch 혼자 사용하기

1. `$ git branch <branch-name> ` 으로 새로운 브랜치 생성

2. `$ git switch <branch-name>` 으로 브랜치 변경

   1. `$ git switch -c <branch-name>` 으로 한 번에 새로운 브랜치 생성 및 변경 가능

3. 작업 및 `add` & `commit`

4. `$ git switch master` 로 브랜치 변경

5. `$ git merge <branch-name> 으로 병합`

   1. Fast Forward => 9번으로
   2. Auto Merge => 9번으로
   3. Confilct => 6번으로

   ```
   ...
   Automatic merge failed; fix conflicts and then commit the result.
   ...
   ```

6. `vscode` 에서 직접 빨간 불 들어온 파일을 수정한다.
7. `$ git add .`
8. `$ git commit -m '충돌 해결'`
9.  종료
10. `$ git branch -d <branch-name>` 으로 수명이 다한 브랜치 삭제



## branch 협업 하기

1. github remote에서 리포 생성
2. collabrator 추가
3. 팀원들 각자 자신의 컴퓨터(로컬 저장소)에 `clone` 
4. `$ git switch -c <my-branch>`로 작업할 브랜치 생성 및 브랜치 변경
   - 이 때 생성할 브랜치 이름은 회사 메뉴얼에 주어진다.
   - 브랜치 이름 작성에 관한 참조
     - Github Flow ([tech-interview-for-developer/Git vs GitHub vs GitLab Flow.md at master · gyoogle/tech-interview-for-developer](https://github.com/gyoogle/tech-interview-for-developer/blob/master/ETC/Git vs GitHub vs GitLab Flow.md))

5. 작업 => `add` => `commit` => 반복...
6. `$ git push origin <my-branch>`
7. 리모트에서 PR(pull request) 생성
8. 팀원들끼리 코드 리뷰 및 최종 merge 결정(github 상에서 진행됨)
   1. Auto merge 가능(초록색) => 진행
   2. Conflict 발생(빨간색) => github에서 수동으로 수정 후 merge 진행
9. 로컬 `master` 브랜치에서 `$ git pull origin master` 
10. 작업 반복