## 🧾 2. iOS 앱 릴리즈 체크리스트 (Flutter 기준)

### 🎯 필수 사전 조건

- ✅ **Apple Developer 계정 등록** (연 $99)
- ✅ **Mac + Xcode 설치** (빌드 및 시뮬레이터 필요)
- ✅ `flutter build ios` 시 정상 빌드 완료 확인

---

### 🛠️ 앱 개발 쪽 체크

| 항목                              | 설명                                                                           |
| --------------------------------- | ------------------------------------------------------------------------------ |
| ✅ 앱 이름, 아이콘, 스플래시 화면 | `pubspec.yaml`, `assets`, `flutter_native_splash`, `flutter_launcher_icons` 등 |
| ✅ 에러 없이 실행                 | 시뮬레이터 및 실제 기기 테스트 완료                                            |
| ✅ 최소 기능 명세                 | 예: 할 일 추가, 삭제, 완료 체크 등                                             |
| ✅ State 보존 여부                | 앱 껐다 켜도 데이터 유지? (SharedPreferences 등 사용?)                         |
| ✅ 개인정보 관련 요소 없는지      | 수집하는 데이터가 없으면 `No`로 명시하면 됨                                    |

---

### 🚀 앱스토어 등록 단계 (요약)

1. **Xcode에서 `.ipa` 빌드**
   - `flutter build ios --release`
   - `open ios/Runner.xcworkspace`
   - `Generic iOS Device` 선택 후 Archive
2. **App Store Connect 등록**
   - 앱 생성 (이름, 설명, 키워드 등 입력)
   - 스크린샷 등록 (5.5", 6.5", iPad 등)
   - 버전 정보 및 리뷰용 계정 입력
3. **TestFlight 테스트 (선택)**
   - 실제 기기에 설치해서 최종 점검 가능
4. **App Store 심사 제출**
   - 승인은 1~3일 걸림 (간단한 앱이면 더 빠를 수 있음)

---

## ✅ 간단 요약 리스트 (PDF처럼 보이게)

- [ ] Apple Developer 등록
- [ ] 앱 아이콘 / 스플래시 화면 구성
- [ ] 앱 정상 빌드 및 테스트 완료
- [ ] 최소 기능 충족 (예: 할 일 추가/삭제/완료)
- [ ] 데이터 저장 로직(선택)
- [ ] App Store Connect 등록
- [ ] Xcode Archive → Upload
- [ ] 스크린샷 및 앱 설명 등록
- [ ] TestFlight (선택)
- [ ] 심사 제출 → 승인
