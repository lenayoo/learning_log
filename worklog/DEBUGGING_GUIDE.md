# 🐞 DEBUGGING_GUIDE.md

알 수 없는 버그를 만났을 때, 빠르게 원인을 파악하고 해결하기 위한 공통 디버깅 플로우입니다.  
프론트엔드, 백엔드, 네트워크 등 각 영역에서 사용할 수 있는 기본적인 점검 항목을 정리했습니다.

---

## ✅ 1. 프론트엔드 디버깅

### 🔹 디버깅 도구 활용

- `console.log`, `debugger`, 브라우저 DevTools 활용
- Vue 개발자 도구, React DevTools 등 사용

### 🔹 데이터 흐름 확인

- props / state / computed / ref 값이 올바른가?
- 조건부 렌더링 (`v-if`, `v-show`, `v-for`, `map`)이 잘 동작하는가?

### 🔹 네트워크 요청 확인

- DevTools → Network 탭에서 request/response 확인
- 요청 URL, 파라미터, 응답 형식 확인

### 🔹 에러 메시지 해석

- 브라우저 콘솔 오류 로그 확인 (warning vs error 구분)
- 스택 트레이스에서 오류 위치 추적

### 🔹 캐시 / 핫 리로드 문제 의심

- 강력 새로고침 (Cmd + Shift + R / Ctrl + Shift + R)
- 개발 서버 재시작

---

## ✅ 2. 백엔드 디버깅

### 🔹 로그 확인

- 서버 로그에서 에러 메시지, 스택 트레이스 분석
- 로그 레벨 (info, warn, error) 필터링

### 🔹 API 테스트

- Postman, curl 등을 사용해 직접 API 호출 테스트
- 요청 파라미터, 응답 값, 상태 코드 확인

### 🔹 DB 연동 확인

- 쿼리문 실행 확인 (예: SQL 로그, 직접 실행)
- WHERE 조건, JOIN, NULL 값 등 주의

### 🔹 의심 포인트

- 인증/권한 처리 누락
- 타입 불일치, null 처리 누락
- 환경변수 오류 (예: 잘못된 DB 접속 정보)

---

## ✅ 3. 네트워크 / 통신 디버깅

### 🔹 요청 경로 및 URL 확인

- 프론트 → 백엔드 API 경로 정확한지 확인
- BASE_URL 설정, 환경 분리(local/dev/prod)

### 🔹 CORS 오류 점검

- 브라우저 콘솔에서 CORS 관련 메시지 확인
- 백엔드에서 CORS 허용 설정 여부 점검

### 🔹 API 응답 이상 여부

- 4xx, 5xx 오류 상태 코드
- 응답 지연, 타임아웃

### 🔹 배포 환경 문제

- proxy 설정 오류
- SSL 인증서 만료 여부
- nginx, load balancer 설정 확인

---

## 🧩 공통 체크리스트

- [ ] 재현 가능한가? (재현 조건을 명확히)
- [ ] 최근 변경된 코드 확인 (git diff, git blame 등)
- [ ] 로컬 vs 운영 환경 차이 확인
- [ ] 다른 사람의 시점에서 테스트
- [ ] 가능한 최소 코드로 줄여서 테스트

---

## 📌 참고

- Vue Devtools / React Developer Tools
- Postman / Insomnia / curl
- 브라우저 DevTools (Chrome, Firefox)
