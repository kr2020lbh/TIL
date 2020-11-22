### 11/19  완료한 것

- 계정 만들기 signup
- 계정 로그인 login
- 영화 review  crud



### 11/20 해야할 것

- 영화 review 댓글
- 영화 review 좋아요
- 기본적인 디자인



### 11/20 새로 사용한 것

- `    this.$router.go(this.$router.currentRoute)` : 새로고침처럼 사용 (댓글 작성 시  댓글 목록이 바로 바뀌지 않아서 추가했음)

  

- ```html
  {
      path: '/community/movie_review_detail/:review_id',
      name: 'movie_review_detail',
      component: MovieReviewDetail,
  }, 
  ```

  path를 django에서 variable routing 했던 것 처럼 사용할 수 있다.
   path 에서 :(변수명) 이렇게 ! 이 변수는 어디서 오냐면.. 라우팅을 요청할 컴포넌트 혹은 페이지에서 다음과 같이 요청한다
  this.$router.push({name : 'movie_review_detail', params : {review_id:review.id}})

  


### 11/20 발생한 문제

- username이 아닌 user_id로 나오는것... 댓글과 게시물 등등 작성자 이름을 입력해야하는데 이거 어떻게 해결하지??
  - 내가 생각한 해결책 
  - 1. 로그인할 떄 토큰을 로컬스토리지에 넣은것처럼 username을 로컬스토리지에 저장한다 ->  ***해결***

- axios.post는 무조건,, 데이터를 넘겨줘야해 첫번 째 인자가 데이터이기 때문에 인증오류난다... 원래는 첫번째 인자에 토큰을 넣어줫었느데,, 그거로 시간날림 ,, 내 생각에 like에서 해당 유저가 있는지 확인하고 없으면 추가하기 때문에 post라 생각했고 굳이 데이터를 안넘겨주고 request.user를 사용하려 했기 떄문에 데이터를 쓸 생각 안해서 계속해서 인증오류가 났음
- 도대체 object를 json으로 변환할 수 없다.......뭔소리일까 key값에 넣은것도 아니고 value값으로 object가 안되는 겅가



### 11/21 해야할 것

- 기본 디자인
- 페이지 상속 구조 바꾸기



### 11/21 새로 사용한 것

- querySelector, createElement, appendChild를 이용해 동적인 웹페이지 구현 (하지만 없던 요소가 생기다보니 페이지의 디자인이 뒤틀림 문제 해결방법 생각해 봐야함)
- 버튼 Hover할 때 하위 요소를 보여주는 스타일 적용



### 11/21 발생한 문제

- 동적인 웹페이지 구현할 때 없던 요소가 생기다보니 페이지의 디자인이 뒤틀림 문제 해결방법 생각해 봐야함
- 이미지 혹은 동영상에 window의 scroll event에 따라서 opcaity가 변화하는 css를 적용하려 했는데 잘안된다 img.style.opacity에서 오류가 발생하는데 해결 못하겠음



### 11/22 해야할 것

- 게시판 디자인
- 글 목록을 보여줄 때 최신글 인기글 순서 적용하기
- 게시글 디테일 디자인
- 검색창



### 11/22 새로 사용한 것

- 영화 리뷰 평점 등록할 때 mouserover, mouserout, 사용

- model에서 해당 모델이 foreignkey를 몇개나 가지고 있는지 반환하는 법, 새로운 컬럼을 만든다...

  ```python
  from django.db.models import Count
  annotate(num_likes=Count('like'))
  order_by('-num_likes')
  ```

- z-index를 이용해서 새로 생기는 element를 다른 element와 간섭이 안일어나게 했음



### 11/22 발생한 문제

- axios 비동기 요청에 의해서 브라우저 화면에 좋아요 개수 출력이 안된다.. -> 쿼리셋 자체를 바꾸는 방법



### 앞으로 해야할 것

- 영화 카드에 대한 CSS
- 검색 기능 -> 검색을 눌렀을 때 어떻게 할 것인가
- 내 정보 페이지
- 이미지 혹은 동영상에 window의 scroll event에 따라서 opcaity 변화

