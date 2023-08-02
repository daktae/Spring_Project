# Spring_Project
국내 여행 계획 프로그램 [DreamJourney]

# 프로젝트 소개
- 맛집, 액티비티, 교통, 숙소, 관광지를 한번에 예약한다.
- 클릭 한번으로 간편한 여행 계획한다.
- 마이페이지로 예약을 편리하게 관리할 수 있다.

# 개발기간
- 2023-06-23 ~ 2023-07-12

# 기술 스택
### Environment
<img src="https://img.shields.io/badge/Eclipse IDE-2c2255?style=for-the-badge&logo=EclipseIDE&logoColor=white"/> <img src="https://img.shields.io/badge/Github-181717?style=for-the-badge&logo=Github&logoColor=white"/> <img src="https://img.shields.io/badge/Git-f05032?style=for-the-badge&logo=Git&logoColor=white"/>
<img src="https://img.shields.io/badge/Visual Studio Code-007acc?style=for-the-badge&logo=VisualstudioCode&logoColor=white"/>

### Language & Framework
<img src="https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=java&logoColor=white"/>  <img src="https://img.shields.io/badge/JavaScript-f7df1e?style=for-the-badge&logo=JavaScript&logoColor=black"/> <img src="https://img.shields.io/badge/HTML5-e34f26?style=for-the-badge&logo=HTML5&logoColor=white"/> <img src="https://img.shields.io/badge/CSS-1572b6?style=for-the-badge&logo=CSS3&logoColor=white"/> <img src="https://img.shields.io/badge/BootStrap-7952b3?style=for-the-badge&logo=bootstrap&logoColor=white"/> <img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white"/> 

### Database
<img src="https://img.shields.io/badge/Oracle Database-f80000?style=for-the-badge&logo=Oracle&logoColor=white"/> 

### Server
<img src="https://img.shields.io/badge/Apache Tomcat-f8dc75?style=for-the-badge&logo=Apache Tomcat&logoColor=black"/> 

# 데이터 구조
<img src="03. ERD/spring_논리 (0709 1517).png">

<hr>

### 개요
1. Spring Framework를 이용하여 여행과 예약이 가능한 국내 여행 계획 프로그램
2. 편리한 예약 및 예매를 통해서 사용자는 편안한 환경에서 필요한 정보를 검색한다.
3. 원하는 교통, 숙소, 액티비티 예약이 가능하고, 프로그램은 다양한 선택지를 제공한다.
4. 가격과 예약 가능 여부를 확인할 수 있어 편의성을 제공한다.

# 화면 구성
### 📘 메인 화면

- 메인 화면은 로그인과 상세 기능으로 이루어져 있다.
- **예약/예매** : 교통, 숙소, 액티비티 예약이 가능하다.
- **추천여행지** : 회원이 등록한 여행일정을 공유할 수 있다.
- **커뮤니티** : 리뷰(여행, 맛집, 액티비티), 동행, 분실로 나뉘고 회원은 게시물을 등록할 수 있다.

<p align="center"><img src="04. 화면 설계/메인화면.png" width=500px;></p>

### 📘 로그인/회원가입
- 로그인/소셜 로그인 : 로그인은 회원로그인, 소셜 로그인으로 나뉘게 된다. 회원 로그인은 아이디와 비밀번호를 입력하여 로그인을 하게 되고, 소셜 로그인은 카카오 로그인 API를 사용하여 로그인 후 계정이 존재하지 않을 경우 회원가입으로 넘어가게 된다.
- 회원가입 : 회원가입 절차는 Ajax를 이용하여 중복검사 후 이메일API를 통해 인증번호 일치 확인을 하며, 본인인증에서는 입력한 이름과 반환된 이름 일치 여부를 검사하고, 중복된 전화번호 및 성인 여부도 본인인증(IAMPORT API)를 사용하여 확인 후 가입이 가능합니다.
- 아이디/비밀번호 찾기 : 아이디 찾기는 IAMPORT API를 사용하여 인증하여 찾기가 가능하고, 비밀번호 찾기는 이메일 API를 사용하여 발송된 인증번호를 입력하여 새로운 비밀번호를 설정할 수 있다.

### 📘 예약/예매
- 교통, 숙소, 액티비티 예약 : 교통/숙소/액티비티로 카테고리를 분류하여 원하는 카테고리를 선택하여 정보를 확인할 수 있다.
- 교통, 숙소, 액티비티 상세페이지 : 상품 상세 페이지 및 회원이 등록한 평점의 평균과 리뷰를 확인할 수 있다. 카카오맵 API를 활용하여 상품의 위치를 마커를 등록한다. Ajax를 활용해 즐겨찾기 추가/삭제가 가능하다. DatePicker 라이브러리를 통해 DB로부터 사용 가능한 날짜를 활성화 할 수 있다.
- 검색 : 숙소, 교통, 액티비티 카테고리 별로 날짜, 이름, 인원 등을 선택하여 검색할 수 있다. Mybatis를 활용하여 테이블에 저장된 데이터에서 이용자가 검색한 검색어를 기준으로 데이터를 가져와 해당 데이터를 화면에 출력한다.
- 결제 : 회원이 상세페이지에서 선택한 상품 정보, 날짜 및 인원, 가격 등의 데이터를 가져와 결제 방법 및 가격 확인 후 결제를 한다. 결제 API를 활용하여 실제 결제 화면을 구현하였다.

<p align="center">
  <img src="04. 화면 설계/예약/액티비티.png" width=300px; height=450px;>
  <img src="04. 화면 설계/예약/액티비티 상세보기.png" width=300px; height= 450px;>
  <img src="04. 화면 설계/예약/결제 전체화면.png" width=400px; height=450px;> 
</p>

### 📘 커뮤니티
- 리뷰 / 동행 / 분실 게시판 : MyBatis를 활용하여 ‘자유게시판’ 테이블에 저장된 데이터 중 말머리가 ‘리뷰’인 게시글 목록을 조회할 수 있다. 회원은 게시글을 등록/수정/삭제할 수 있다.
- 동행 채팅 : WebSocket을 활용하여 회원 간 여행 메이트를 구할 수 있다. 커뮤니티 게시판 중, 말머리가 ‘동행’ 인 게시글을 상세보기하면 해당 게시글 번호로 채팅방이 만들어지며 이곳에서 회원 간 채팅이 가능하다.
<p align="center">
  <img src="04. 화면 설계/커뮤니티/커뮤니티 글목록.png" height=500px;>
</p>
<p align="center">
  <img src="04. 화면 설계/커뮤니티/커뮤니티_동행채팅_회원1.png" width=500px; height=700px;>
  <img src="04. 화면 설계/커뮤니티/커뮤니티_동행채팅_회원2.png" width=500px; height=700px;>
</p>


### 📘 마이페이지
- 내 여행 관리 : DatePicker를 활용해 여행 시작일과 종료일을 등록하고, 카카오맵 API를 통해 여행 예정인 장소를 날짜별로 검색 및 등록할 수 있다. 여행 일정으로 등록된 장소는 카카오맵상 마커로 출력되고, 다중 장소가 등록될 시 마커가 등록된 순서대로 연결돼 여행 동선을 확인할 수 있다. 등록이 완료될 시 Ajax를 통해 DB에 등록된다.
- 내 예약 기록 관리 : 내가 예약한 숙소/교통/액티비티를 카테고리별로 조회할 수 있다. 상세 조회로 넘어가면 결제내역을 볼 수 있다. 예약 취소 버튼을 누르면 예약을 취소할 수 있다.
- 리뷰 관리 : 서비스 내 결제 기록이 있으나 리뷰가 작성되지 않은 결제건에 대한 리뷰를 작성할 수 있다. 별점과 내용을 작성해 등록할 시 Ajax를 통해 DB에 등록된다. 또한, Ajax를 통해 작성된 리뷰를 수정, 삭제할 수 있다.
<p align="center">
  <img src="04. 화면 설계/마이페이지/마이페이1지.png" width=500px; height=500px;>
  <img src="04. 화면 설계/마이페이지/마이페이2지.png" width=500px; height=500px;>
  <img src="04. 화면 설계/마이페이지/마이페이3지.png" width=500px; height=500px;>
  <img src="04. 화면 설계/마이페이지/마이페이4지.png" width=500px; height=500px;>
</p>


<hr>

## ❗ 아쉬웠던 점
### Spring Security & JPA
- Spring 수업과 프로젝트를 병행하여 진행하느라 좀 더 다양한 기능을 사용하는데 제약이 있었기에 아쉬움이 남았습니다. MyBatis 뿐만 아니라 Spring Security나 JPA등을 사용할 수 있었으면 더 기술적으로 탄탄한 프로젝트를 완성할 수 있었을 것 같습니다.

## 💡 문제 해결을 위한 노력
### 프론트엔드
- 저번 웹 프로젝트에서 화면 설계를 할 때, 시간이 너무 허비한 느낌이 있어서 이번에는 백엔드에 집중하고자 BootStrap 탬플릿을 활용하여 작업을 하였다. 확실히 프론트엔드 쪽에 시간을 허비하지 않고, 백엔드 쪽에 집중할 수 있어 기간 내에 프로젝트를 완료할 수 있었다. 허나 시간이 좀 더 있었더라면 프론트엔드 부분도 직접 건드려서 더욱더 만족스러운 프로젝트가 완성될 수 있었을 것 같다.

