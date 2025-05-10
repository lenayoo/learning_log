# 🌅 4AM_CODE.md

"라이브러리"보다 "실제 잘 만든 오픈소스"를 읽자!  
React / Vue / TypeScript 기반으로, 구조와 설계가 잘 되어 있어 코드 리딩에 적합한 깃허브 프로젝트들을 정리합니다.

---

## ✅ React 기반 추천 프로젝트

| 프로젝트           | 설명                                   | 기술스택                               | 링크                                                         |
| ------------------ | -------------------------------------- | -------------------------------------- | ------------------------------------------------------------ |
| **Hashnode Clone** | 블로그 플랫폼 클론 (GraphQL + Next.js) | Next.js, GraphQL, TypeScript, Tailwind | https://github.com/unicoderguy/hashnode-clone                |
| **cal.com**        | Calendly 오픈소스 대안, 실무급 규모    | Next.js, Prisma, Tailwind, trpc        | https://github.com/calcom/cal.com                            |
| **Nhost Example**  | Firebase 대체 구조, 백엔드 통합        | React, GraphQL, Hasura, Auth           | https://github.com/nhost/nhost/tree/main/examples/with-react |
| **Formbricks**     | 오픈소스 타입폼, 폼 생성기             | React, TypeScript, Tailwind, Prisma    | https://github.com/formbricks/formbricks                     |

---

## ✅ Vue 기반 추천 프로젝트

| 프로젝트                   | 설명                                       | 기술스택                         | 링크                                            |
| -------------------------- | ------------------------------------------ | -------------------------------- | ----------------------------------------------- |
| **Vuestic Admin**          | Vue 3 + Composition API 기반 어드민 템플릿 | Vue 3, TypeScript, Pinia         | https://github.com/epicmaxco/vuestic-admin      |
| **GitHub Profile Summary** | 깃허브 프로필 요약기, API 활용 예시 풍부   | Vue 3, Composition API, Chart.js | https://github.com/tipsy/github-profile-summary |
| **Fume**                   | 전자책 독서 추적 앱                        | Nuxt 3, Supabase, Tailwind       | https://github.com/patrickfust/fume             |
| **Haku UI**                | Vue UI 컴포넌트 라이브러리 (구조 참조용)   | Vue 3, Tailwind, TypeScript      | https://github.com/haku-ui/haku-ui              |

---

## ✅ TypeScript 기반 실전 예제

| 프로젝트             | 설명                        | 기술스택                      | 링크                                       |
| -------------------- | --------------------------- | ----------------------------- | ------------------------------------------ |
| **SaaS Boilerplate** | 다국어/다계정 SaaS 기반     | TypeScript, Next.js, Supabase | https://github.com/async-labs/saas         |
| **Plane**            | 오픈소스 프로젝트 관리 도구 | TypeScript, React, PostgreSQL | https://github.com/makeplane/plane         |
| **TypeBot**          | 챗봇 빌더 플랫폼            | TypeScript, tRPC, Zustand     | https://github.com/baptisteArno/typebot.io |

---

## 🧠 학습 방법 팁

- `components/`, `hooks/`, `store/`, `pages/` 구조 집중해서 보기
- 비즈니스 로직 분리, 상태관리 흐름, API 호출 구조 분석
- `README.md`의 실행 방법 → 실제 로컬 실행 → 코드 리딩
- 클론 → `devtools`, `console.log`, `debugger`로 흐름 추적

---

## ✍️ 예시 정리 템플릿

```md
### 📅 2025-05-11

#### 📁 프로젝트: cal.com

- **메인 관심**: 예약 생성 흐름, 캘린더 동기화 구조
- **폴더 구조 요약**:
  - `apps/web`: Next.js 프론트엔드
  - `packages/db`: Prisma ORM
  - `packages/trpc`: API 연동
- **인사이트**:
  - Monorepo 구조 + 모듈 분리 방식 참고
  - 폴더 구조가 확장 가능한 형태로 설계되어 있음
```
