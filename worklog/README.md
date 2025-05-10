# 🛠 Work Log

---

## 📅 2025-05-11 (토)

### 🐞 Debugged

- Vue `v-btn`에서 ripple 효과가 적용되지 않던 문제 → `overflow: hidden` 필요 확인
- Pinia에서 상태 초기화가 안되던 문제 → `store.$reset()` 호출 누락

### 📘 Learned

- `router.query`를 사용한 컴포넌트 상태 전달은 `$route.fullPath` key 활용이 유용
- Vue3 + Vuetify에서 유효성 체크는 `formRef.value.validate()` 결과값으로 제어

### 🔖 Referenced

- [Vuetify Button Docs](https://vuetifyjs.com/en/api/v-btn/)
- [Pinia 공식 문서 - Store Reset](https://pinia.vuejs.org/core-concepts/state.html#resetting-the-state)

### ⏳ To Review Later

- Vue에서 `watch`가 `$route.path`를 인식 못하는 상황 → `watch(() => route.fullPath)`로 대체?
- 로그인 화면의 유효성 처리와 API 요청 타이밍 재검토 필요
