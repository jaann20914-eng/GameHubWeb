<div align="center">

# 🕹️ GameHubWeb — 회원 기능 워밍업

**F5 팀이 본 프로젝트에 들어가기 전, 하루 동안 함께 만든 회원 기능 연습 프로젝트**

Servlet · JSP · Oracle로 회원가입부터 탈퇴까지 한 바퀴 돌려 보고,<br>
팀의 Git 협업 방식(fork → Pull Request)을 맞춘 저장소

</div>

<br>

## 0. 담당 파트

> **회원가입 화면**과 **아이디 중복 확인**, DAO 싱글턴 구성을 맡았습니다.

| 기능 | 한 일 |
| :--- | :--- |
| **회원가입 화면** | `joinform.jsp` 입력 폼 |
| **아이디 중복 확인** | `idcheck.member` 컨트롤러와 DAO 조회 |
| **DAO 구성** | `MemberDAO.getInstance()` 싱글턴, Gson 의존성 추가 |

<br>

## 1. 프로젝트 소개

| 항목 | 내용 |
| :--- | :--- |
| 기간 | 2025.08.25 (1일) |
| 인원 | 5명 (F5 팀) |
| 다음 프로젝트 | 이 구조를 키워 2주 동안 만든 [**F5 — 미니게임 허브 웹**](https://github.com/jaann20914-eng/F5) |

<br>

## 2. 기능

| 주소 | 기능 |
| :--- | :--- |
| `register.member` | 회원가입 |
| `idcheck.member` | 아이디 중복 확인 |
| `login.member` · `logout.member` | 로그인 · 로그아웃 |
| `update.member` | 연락처 · 이메일 · 주소 수정 |
| `delete.member` | 회원 탈퇴 |

- 비밀번호는 `SecurityUtil` 의 **SHA-256** 해시로 저장하고, 로그인할 때 같은 해시로 비교합니다.
- DB 연결은 톰캣 JNDI DataSource에서 받아 씁니다.

<br>

## 3. 구조

```text
SG/src/main
├── java
│   ├── controller/MemberController.java   *.member 요청 처리
│   ├── dao/MemberDAO.java                  싱글턴 DAO
│   ├── dto/MemberDTO.java
│   └── util/SecurityUtil.java              SHA-256
└── webapp
    ├── index.jsp · login.jsp · joinform.jsp
    ├── member/idCheck.jsp                  아이디 중복 확인 팝업
    ├── assignout.jsp                       회원 탈퇴
    └── error.jsp
```

<br>

## 4. 기술 스택

| 분류 | 기술 |
| :--- | :--- |
| **Backend** | Java, Servlet, JSP, Maven |
| **Database** | Oracle Database, JNDI DataSource |
| **Library** | Gson |
| **Server** | Apache Tomcat |

<br>

## 5. 팀원

| 이름 | 담당 |
| :-: | :--- |
| [박지원](https://github.com/jaann20914-eng) | 회원가입 화면, 아이디 중복 확인, DAO 싱글턴 |
| [Ju-S](https://github.com/Ju-S) | 저장소 관리 · PR 병합, 공통 Util 정리 |
| [pwrmin](https://github.com/pwrmin) | 회원 탈퇴, 에러 페이지 |
| [장영서](https://github.com/jangyeongseo) | 마이페이지(정보 수정) |
| [gijun123](https://github.com/gijun123) | 로그인 화면 · 로그인 기능 |

> 이 저장소는 팀 원본 저장소를 fork한 것입니다. 코드는 그대로 두고 README만 정리했습니다.
