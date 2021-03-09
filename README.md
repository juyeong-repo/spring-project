


# **Show me the movie**
##### 영화예매 사이트 
---
#### Index 
* 기능
* 설계 및 구현
---
##### 기능
메가박스를 벤치마킹하여 만든 영화예매 사이트
* 회원가입
* 영화페이지
* 예매내역
* 취소내역

##### 설계 및 구현
|name|role|
|------|---|
|signUp.jsp|회원가입화면|
|SignUpController.java |userIdCheck 메소드에서 int형의 결과를 리턴 받음, view에서 회원가입 버튼눌러 제출하 처리하는 컨트롤러|
| UserDAO.xml | select count를 사용해서,view에서 입력받은 userId가 user table에 있으면 1,없으면 0을 반환|
|MovieController.java|영화정보를 담는 movies list를 만들고 view table(moviePageList)에서 영화목록 가져옴|
|viewTableDAO.xml|누적관객수가 큰 순서대로  moviePageList 뷰테이블 만듦. Rank()함수 를 사용하여 movie테이블의 누적관객수 값이 큰 순서대로 order by|
|movie.jsp|담아온 영화 정보들을 반복문 foreach를 사용해서 li태그를 반복 출력하고 varStatus의 count 속성으로 순위 표시|
|myPage.jsp|foreach 문법을 사용하여 예매내역과 취소내역을 화면에 출력|
|BookingController.java|getMyPage() 메소드로 세션에서 유저 정보가져옴|
|viewTableDAO.xml|예매내역을 불러오기 위해 getBooking과 cancellation 뷰 테이블 생성|
|BookingDAO.xml|마이바티스 resultmap 사용|
|CancellationDAO.xml|취소일자,예매좌석 정보를 가져옴|
|user.js |ajax 사용하여 취소내역 보여줌|




