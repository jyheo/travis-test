# travis-test
test repository for travis.org 



* 2명 이상 조를 구성,
* 조장이 github 저장소 생성
* 각 팀원을 collaborator로 추가

* 조장은 github 저장소에 develop 브랜치 만듬.
* 모두 로컬 컴퓨터로 github 저장소를 clone

* 조장이 우선 main.c에 main() 만들고 commit
* main()에서 팀원들이 만들 함수 team1.c/team1(), team2.c/team2(), team3.c/team3() 등을 호출하게 만들고 commit
* push develop

* 각자 feature 브랜치 생성하여 자신의 함수를 위한 파일을 만들고 함수 만들고 commit
* feature를 develop으로 머지
* develop을 push
* feature 삭제

* 조장은 .travis.yml을 만듬
* 각 팀원들의 feature가 완료되면 develop을 master로 머지
* master에 태그(버전 번호는 적당히!)

* 조장은 master push

* Travis 결과 확인
참고로 gcc main.c team1.c team2.c team3.c 이렇게 하면 모두 컴파일 하고 링크하여 a.out을 만들게 됨
.travis.yml
language: c
script:
  - gcc main.c team1.c team2.c team3.c
  - ./a.out
