# 후회제로 (Android)

Capacitor로 감싼 안드로이드 앱입니다. 알림은 기기 안에서 예약되는 로컬 알림이라 서버가 필요 없습니다.

## APK 만들기 (Android Studio 없이)
1. GitHub에 새 저장소를 만들고 이 폴더 전체를 업로드합니다 (.github 폴더 포함).
2. 저장소의 Actions 탭에서 build-apk를 실행합니다 (Run workflow).
3. 끝나면 Artifacts의 regretzero-apk를 내려받아 압축을 풉니다.
4. app-debug.apk를 폰으로 옮겨 설치합니다 (출처를 알 수 없는 앱 허용 필요).

## 내 PC에서 만들기
npm install && npx cap add android && npx cap sync android && npx cap open android
(AndroidManifest.xml의 application 태그 위에 POST_NOTIFICATIONS 권한을 추가하세요.)

## 알림 동작
- 기대 저장 시: 도착 예정일에 "도착했나요?", 그 2일 뒤 "아직 평가 전이에요"
- 수령 평가를 남기면 위 알림은 취소되고, 30일 뒤 "아직 쓰세요?"가 예약됩니다.
- 알림을 누르면 홈 화면이 열립니다.
