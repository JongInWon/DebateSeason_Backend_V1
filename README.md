# 토론철 백엔드 (DebateSeason Backend)

## ✅ 목차

[1. 프로젝트 소개](#-프로젝트-소개)  
[2. 기술 스택](#-기술-스택)  
[3. 프로젝트 구조](#-프로젝트-구조)   
[4. 주요 기여](#-주요-기여)     


## 📋 프로젝트 소개

토론철(DebateSeason)은 다양한 커뮤니티의 사용자들이 모여 여러 주제에 대해 실시간 채팅을 통해 토론을 할 수 있는 플랫폼입니다. 토론철은 “결국 대화를 통해 서로를 이해하고, 갈등을 해결할 수 있다”는
신념으로 서비스를 만들고 있습니다.

## 🛠 기술 스택

<img src="https://img.shields.io/badge/Language-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/java-%23ED8B00?style=for-the-badge&logo=openjdk&logoColor=white"><img src="https://img.shields.io/badge/17-515151?style=for-the-badge">
</br>
<img src="https://img.shields.io/badge/Framework-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/springboot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white"><img src="https://img.shields.io/badge/3.3.5-515151?style=for-the-badge">
</br>
<img src="https://img.shields.io/badge/Database-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white"><img src="https://img.shields.io/badge/11.4.4-515151?style=for-the-badge">
</br>
<img src="https://img.shields.io/badge/ORM-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=for-the-badge&logo=spring&logoColor=white"><img src="https://img.shields.io/badge/3.1.0-515151?style=for-the-badge">
</br>
<img src="https://img.shields.io/badge/Security-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=spring-security&logoColor=white"><img src="https://img.shields.io/badge/6.1.0-515151?style=for-the-badge"><img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white"><img src="https://img.shields.io/badge/0.12.3-515151?style=for-the-badge">
</br>
<img src="https://img.shields.io/badge/Communication-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/WebSocket-010101?style=for-the-badge&logo=socket.io&logoColor=white"><img src="https://img.shields.io/badge/STOMP-000000?style=for-the-badge"><img src="https://img.shields.io/badge/2.3.3-515151?style=for-the-badge">
</br>
<img src="https://img.shields.io/badge/Documentation-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black"><img src="https://img.shields.io/badge/2.2.0-515151?style=for-the-badge">
</br>
<img src="https://img.shields.io/badge/Auth-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/OIDC-2671E5?style=for-the-badge&logo=openid&logoColor=white"><img src="https://img.shields.io/badge/Kakao_&_Apple-515151?style=for-the-badge">
</br>
<img src="https://img.shields.io/badge/Build-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/Gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white"><img src="https://img.shields.io/badge/8.4-515151?style=for-the-badge">
</br>
<img src="https://img.shields.io/badge/Container-%23121011?style=for-the-badge"><img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"><img src="https://img.shields.io/badge/24.0.5-515151?style=for-the-badge">

## 🏗️ 프로젝트 구조

```plaintext
src/main/java/com/debateseason_backend_v1/
├── common/             # 공통 모듈 (예외 처리, 응답 객체 등)
├── config/             # 애플리케이션 설정
├── domain/             # 도메인별 로직
│   ├── chat/           # 채팅 관련
│   ├── chatroom/       # 토론방 관련
│   ├── issue/          # 이슈 관련
│   ├── profile/        # 사용자 프로필 관련
│   └── user/           # 사용자 인증 관련
├── security/           # 보안 관련 (JWT 등)
└── DebateSeasonBackendV1Application.java
```

## 📜 주요 기여

### AWS 인프라 및 CI/CD 파이프라인 구축
<img width="1041" alt="스크린샷 2025-05-20 오후 6 26 55" src="https://github.com/user-attachments/assets/33a1c474-d8af-441d-b046-4dda366c80ed" />


- 운영/개발 환경 분리(`PROD_CICD.yml`, `DEV_CICD.yml`)
  - 개발 환경: develop 브랜치에 코드가 병합되면, 빌드&테스트 후 개발 서버에 자동 배포
  - 운영 환경: main 브랜치에 코드가 병합되면, 빌드&테스트 후 운영 서버에 자동 배포

### 기여한 API 목록
- **User**
  - POST /api/v2/users/login (로그인)
  - POST /api/v1/users/logout (로그아운)
  - POST /api/v1/users/withdraw (회원탈퇴)
- **Profile**
  - POST /api/v1/profiles (프로필 등록)
  - Patch /api/v1/profiles (프로필 수정)
  - GET /api/v1/profiles/me (내 프로필 조회)
  - Get /api/v1/profiles/nickname/check?query={} (닉네임 검사)
- **Community**
  - GET /api/v1/communities (커뮤니티 목록 조회)
  - GET /api/v1/communities/search?query={} (커뮤니티 검색)  
- **Terms**
  - GET /api/v1/terms (이용약관 목록 조회)
  - POST /api/v1/terms/agree (이용약관 동의)
  - GET /api/v1/terms/agree (내가 동의한 이용약관 목록 조회)
- **Auth**
  - POST /api/v1/auth/reissue (Refresh&Access Token 재발급)
- **App**
  - GET /api/v1/app/version/check?versionCode={} (앱 버전 검사)


### OIDC 인증 기반 id token 검증 로그인(Kakao, Apple)

<img width="552" alt="스크린샷 2025-03-14 오후 4 16 23" src="https://github.com/user-attachments/assets/083ba45f-d724-46ff-b626-1b3dae109448" />

- 전략 패턴을 이용해 여러 소셜 로그인을 대응할 수 있게 설계

### JWT 기반 인증
- 서버 인증을 담당하는 JWT 인증 구축
