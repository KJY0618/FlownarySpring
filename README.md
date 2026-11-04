# 🌊 Flownary 소통 SNS

> 모든 세대가 쉽게 소통하는 SNS 소셜네트워크 플랫폼

📅 개발 기간 : [2024.04.16~2024.06.14] (총 8주)
👥 팀원 : 6명

<p align="center">
<img src="https://img.shields.io/badge/JAVA%2017-007396?style=flat-square&logo=openjdk&logoColor=white">
<img src="https://img.shields.io/badge/SPRING%20BOOT-6DB33F?style=flat-square&logo=springboot&logoColor=white">
<img src="https://img.shields.io/badge/MYBATIS-000000?style=flat-square">
<img src="https://img.shields.io/badge/MYSQL-4479A1?style=flat-square&logo=mysql&logoColor=white">
<img src="https://img.shields.io/badge/REACT-20232A?style=flat-square&logo=react&logoColor=61DAFB">
<img src="https://img.shields.io/badge/MUI-007FFF?style=flat-square&logo=mui&logoColor=white">
<img src="https://img.shields.io/badge/FIREBASE-FFCA28?style=flat-square&logo=firebase&logoColor=black">
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white">
</p>

* * *

## 📌 프로젝트 소개

**Flownary**는
세대 구분 없이 누구나 편하게 쓸 수 있는 **소통 중심 SNS 웹 서비스**입니다.

4060세대의 SNS 활동이 활발해지는 시대에, 다양한 연령층이 게시물을 가장 쉽고 단순하게 관리할 수 있도록 만들었습니다. 소통 단절로 소외될 수 있는 실버세대를 고려해, 어르신도 편하게 쓸 수 있으면서 트렌디한 UI에 초점을 맞췄습니다.

최우선 키워드를 **소통**으로 두고 채팅 위젯을 홈 화면에 배치했고, 본인이 올린 게시물의 사진만 모아 보는 **앨범**, 가족 단위로 묶이는 **패밀리**, 글 작성 중 공개 범위를 정하는 **공개 설정**을 제공합니다.

또한 웹소켓으로 채팅과 알림을 실시간으로 주고받을 수 있도록 구성했습니다.

* * *

## 💾 DB ERD

![ERD](images/erd.png)

| 논리명 | 물리명 | 설명 |
|---|---|---|
| 사용자 | User | 회원 정보 |
| 설정 | Setting | 테마, 폰트 크기, 계정 활성화, 차단 목록 |
| 게시물 | Board | 게시글 |
| 댓글 | Reply | 게시글의 댓글 |
| 대댓글 | Re_Reply | 댓글의 답글 |
| 좋아요 | Like_ | 좋아요 |
| 팔로우 | Follow | 플로우(팔로우) 관계 |
| 가족 | Family | 패밀리 |
| 가족유저 | FamilyUser | 패밀리 구성원 |
| 채팅방 | Chat | 1:1 채팅방 |
| 채팅유저 | ChatUser | 채팅방 참여자 |
| 채팅메세지 | DmList | 채팅 메시지 |
| 알림 | Notice | 알림 내역 |
| 할 일 | ToDo | 할 일 목록 |

* * *

## 📖 주요 기능

| 구분 | 핵심 기능 |
|---|---|
| 회원가입·로그인 | 입력값 유효성 검사, Firebase 인증, 로그인 성공 시 웹소켓 연결 |
| 홈 | 글 작성 위젯, 글 목록, 할 일, 채팅방 목록, 사이드바·상단바 |
| 게시글 | 글 상세(이미지, 내용, 작성자, 댓글), 댓글·대댓글, 좋아요, 공개/비공개 설정 |
| 앨범 | 내가 올린 이미지만 모아 보기, 연도별 선택 |
| 채팅 | 채팅방 목록, 채팅방 내부 실시간 대화 |
| 마이페이지 | 기본 정보와 프로필 사진, 작성한 게시물/좋아요한 게시물 전환 |
| 플로우(팔로우) | 플로워/플로잉 목록 모달, 타인 페이지에서 플로우 |
| 패밀리 | 가족 구성, 패밀리장의 구성원 내보내기 |
| 알림 | 알림 내역 확인, 클릭 시 해당 게시물로 이동 |
| 프로필 수정 | 프로필 이미지와 각종 정보 수정 |
| 관리자 | 통계 페이지, 유저 비활성화, 게시물·신고 관리 |

* * *

## 📖 사용 메뉴얼

### 1️⃣ 회원가입 · 로그인
1. 이메일, 비밀번호, 이름, 닉네임, 전화번호, 생년월일을 입력합니다.
2. 닉네임, 전화번호, 생년월일은 **확인** 버튼으로 각각 검증합니다.
3. **가입하기**를 누르면 인증 정보는 Firebase에, 생년월일 등 나머지 정보는 DB에 저장되고 로그인 화면으로 이동합니다.
4. 로그인에 성공하면 홈 화면으로 이동하고, 서버와 웹소켓이 연결됩니다.

### 2️⃣ 홈
1. 사이드바와 상단바에서 주요 메뉴로 이동합니다.
2. 글 작성 위젯에서 게시글을 작성하고, 아래 글 목록에서 다른 게시글을 확인합니다.
3. 할 일과 채팅방 목록이 함께 표시됩니다.

### 3️⃣ 게시글
1. 글을 누르면 이미지, 내용, 작성자, 댓글을 확인할 수 있습니다.
2. 댓글과 대댓글을 작성하고 좋아요를 누릅니다.
3. 글 작성 중 공개/비공개를 먼저 선택하고, 이후 마이페이지에서 관리합니다.

### 4️⃣ 앨범
1. 내가 올린 게시글의 이미지를 한 곳에서 확인합니다.
2. 연도를 선택해 해당 연도 이미지만 볼 수 있습니다.

### 5️⃣ 채팅
1. 채팅 목록에서 대화방을 선택합니다.
2. 채팅방 안에서 메시지를 주고받으면 상대에게 실시간으로 전달됩니다.

### 6️⃣ 마이페이지 · 플로우
1. 프로필을 누르면 마이페이지로 이동합니다.
2. 작성한 게시물과 좋아요한 게시물을 전환해 볼 수 있습니다.
3. 타인의 마이페이지에서는 **플로우** 버튼으로 플로우할 수 있습니다.
4. 플로워(나를 플로우한 사람), 플로잉(내가 플로우한 사람) 버튼을 누르면 목록 모달이 열립니다.

### 7️⃣ 패밀리
1. [기입: 패밀리 만들기·초대·가입 방법]
2. 패밀리장은 구성원 옆의 **내보내기** 버튼으로 구성원을 내보낼 수 있습니다.

### 8️⃣ 알림
1. 알림을 누르면 알림 내역이 표시됩니다.
2. 알림을 클릭하면 해당 게시물로 이동합니다.

### 9️⃣ 프로필 수정
1. 프로필 이미지와 각종 정보를 수정합니다.

### 🔟 관리자
1. 관리자 계정으로 로그인하면 관리자 메뉴를 사용할 수 있습니다.
2. **통계** 페이지에서 서비스 현황을 확인합니다.
3. **유저 페이지**에서 유저를 비활성화할 수 있습니다.
4. **게시물 관리 / 신고 페이지**에서 게시물과 신고 내역을 관리합니다.

* * *

## 🧩 사용 기술

- **Language:** Java 17, JavaScript, CSS
- **Backend:** Spring Boot 3.2.5, MyBatis 3.0.3, Lombok, Spring WebSocket(STOMP), jBCrypt
- **Database:** MySQL
- **Frontend:** React, MUI(Material UI), React Query, React Router DOM, Axios, SweetAlert2
- **인증·파일(프론트 연동):** Firebase(인증), Cloudinary(이미지)
- **외부 API:** OpenWeather
- **배포:** AWS (Amazon Linux)
- **협업 도구:** GitHub, Google Drive, 카카오톡

* * *

## 📂 프로젝트 구조

### 루트

| 경로 | 설명 |
|---|---|
| `pom.xml` | Maven 의존성 설정 |
| `mvnw`, `mvnw.cmd` | Maven Wrapper |
| `src/main/java` | 서버 소스 |
| `src/main/resources` | 설정 파일, MyBatis 매퍼 |
| `src/test/java` | 테스트 |

### Java 소스 (`src/main/java/com/example/flownary`)

| 경로 | 설명 |
|---|---|
| `controller` | REST 및 웹소켓 컨트롤러 (게시글, 댓글, 채팅, 알림, 팔로우, 패밀리 등) |
| `service` | 비즈니스 로직 (인터페이스 + Impl) |
| `dao` | MyBatis 매퍼 인터페이스 |
| `dto` | 요청·응답 객체 |
| `entity` | 도메인 엔티티 |
| `config` | WebSocket, MyBatis, CORS 설정 |
| `filter` | CORS 필터 |

### 설정 (`src/main/resources`)

| 경로 | 설명 |
|---|---|
| `application.properties` | 서버 포트, DB 연결, MyBatis 설정 |
| `mybatis/mapper` | MyBatis 매퍼 |

### 도메인별 구성

| 도메인 | 설명 |
|---|---|
| User, Setting | 회원, 개인 설정 |
| Board, Reply, Re_Reply, Like_ | 게시글, 댓글, 대댓글, 좋아요 |
| Follow, Family, FamilyUser | 플로우, 패밀리 |
| Chat, ChatUser, DmList | 채팅방, 참여자, 메시지 |
| Notice | 알림 |
| Todo, Schedule | 할 일, 일정 |
| Declaration | 신고 |

* * *

## ⚙️ 실행 환경 / 🚀 실행 방법

- Java 17, MySQL, 서버 포트 `8090`

1. 저장소를 클론합니다.
   ```bash
   git clone https://github.com/KJY0618/FlownarySpring.git
   cd FlownarySpring
   ```
2. MySQL에 `flownary` 데이터베이스를 만들고 ERD에 맞춰 테이블을 생성합니다.
3. `src/main/resources/application.properties`의 DB 접속 정보를 수정합니다.
4. 서버를 실행합니다.
   ```bash
   ./mvnw spring-boot:run
   ```
