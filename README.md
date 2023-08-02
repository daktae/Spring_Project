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

#### 커뮤니티
<img src="08. 화면캡쳐/클라이언트/게시판/6-1. 자유게시판.png" >

### 📘 관리자 기능
- 관리자는 로그인을 하게 되면, 관리자 전용 페이지로 이동한다.
- 관리자는 레벨에 따라서 계정 관리자, 직원으로 나뉘게 된다.
- 두 관리자의 공통 기능은 복지 프로그램 기능, 직원 정보 조회가 있고, 계정 관리자는 공통 기능, 계정에 관한 기능 외 다른 기능을 클릭시 관리자의 레벨을 확인하여 접근할 수 없게 설계하였다. 직원 관리자는 계정 관리자가 접근할 수 없는 기능과 공통 기능을 활용할 수 있다.

#### 계정 관리자 기능
- 관리자 계정 부여 기능
<img src="08. 화면캡쳐/관리자/계정관리자 전용/1-2. 관리자 계정부여.png">


<hr>

## ❗ 아쉬웠던 점
### 화면 설계에 대한 어려움
- 화면 설계를 하기 전에 협업 프로그램을 정하는데 어려움을 겪었다. 협업 프로그램에는 Figma와 Figjam이 후보로 올라왔다. Figma는 UI/UX 전문 툴로서, 익히는데 시간이 걸리는 만큼 결과물이 보장되었고, Figjam은 Figma와 같이 무거운 프로그램이 아니고 브레인 스토밍을 하는데 쓰이는 도구로서, 익히는데 어려움을 겪지 않는다는 점이 장점으로 다가왔다. 팀원들은 화면설계를 할 떄 제대로 해보자는 목표로를 가지고 Figma를 사용하기로 결정하였다. 하지만 Figma 툴을 익히는데, 너무 오랜 시간을 지체해버렸고, 시간을 투자한만큼의 결과물이 안나와서 너무 아쉬웠다.

## 💡 문제 해결을 위한 노력
### Git 활용 능력
- 초반에 관리자와 클라이언트 부분을 나눠서 팀 협업을 시작하였는데, 관리자 부분은 먼저 Git을 시작하고, 클라이언트 부분은 나중에 Git을 시작하여 서그래서 이 로 다른 기능을 병합할 때 충돌나는 일이 생겼었다. 충돌나는 이유는 관리자 기능 중 삭제하고 난 후 커밋을 하였는데, 이것이 삭제내역이 생겨서 다른 사람이 pull을 할 때, 삭제되어 pull을 하면 그 부분이 충돌나서 문제가 일어났던 것이다. 그래서 이 부분을 다시 분기점을 돌려서 이 문제점을 해결하였고, 이 때 느낀 교훈은 Git을 사용하고 커밋할 때, 신중히 해야겠다고 느꼈다.
