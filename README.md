# Frontend + Node.js API 연동 과제

이 프로젝트는 **Node.js(Express) 기반 백엔드 API**와 **HTML/CSS/JavaScript 프론트엔드**를 연동하여 실제 웹 서비스 흐름을 구현하는 과제입니다.  
JWT 인증을 포함해 회원가입, 로그인, 게시글 CRUD 기능까지 전부 연동되는 구조로 작성되었습니다.

---

## 📁 프로젝트 구조

project/
├── controller/ # 요청 처리 로직
├── data/ # DB 접근 및 모델 역할
├── db/ # DB 연결 설정
├── middleware/ # 인증 처리, 에러 핸들링 등
├── public/ # 프론트엔드 정적 파일 (HTML, CSS, JS)
├── router/ # 라우터 분리 (auth, posts 등)
├── app.mjs # Express 앱 초기 설정
├── config.mjs # 환경변수, 설정값 분리
├── package.json
└── package-lock.json

yaml
코드 복사

---

## 📝 기능

### 🔐 인증 (Auth)
- 회원가입
- 로그인 (JWT 발급)
- Authorization 헤더 기반 토큰 인증
- bcrypt로 비밀번호 암호화

### 📝 게시글 기능 (Posts)
- 게시글 생성(Create)
- 게시글 목록 조회(Read)
- 게시글 상세 조회
- 게시글 수정(Update)
- 게시글 삭제(Delete)
- JWT 기반 사용자 권한 검증

### 🖥 프론트엔드
- 순수 HTML/CSS/JavaScript로 작성
- fetch API로 Node.js API 연동
- 로그인 시 JWT를 localStorage에 저장 후 자동 로그인 처리
- 게시글 작성/수정/삭제 연동

---

## ⚙️ 실행 방법

### 1. 패키지 설치
npm install

bash
코드 복사

### 2. 환경변수 설정
`.env` 파일 생성

PORT=3000
DB_HOST=your-db-host
DB_USER=your-db-user
DB_PASSWORD=your-db-password
DB_DATABASE=your-db-name

JWT_SECRET=your-secret
JWT_EXPIRES_SEC=86400
BCRYPT_SALT_ROUNDS=10

shell
코드 복사

### 3. 서버 실행
npm start

shell
코드 복사

### 4. 접속
브라우저 열기 →  
http://localhost:3000

yaml
코드 복사

---

## 🛠 기술 스택

- Node.js + Express
- MySQL (또는 원하는 DB)
- JWT(JSON Web Token)
- bcrypt
- HTML / CSS / JavaScript

---

## 📌 기타 사항
- 서버와 프론트엔드를 완전히 분리하지 않고, Express 정적 서빙을 통해 `/public` 폴더에서 프론트엔드를 제공
- MVC 구조와 비슷하게 폴더 기반으로 역할을 분리하여 유지보수 용이성 강화
- 실제 서비스 흐름을 고려해 인증 → 게시글 → 상세 페이지 → 수정 페이지가 연결되도록 구성
