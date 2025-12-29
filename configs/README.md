# Configs 폴더 안내

`configs/` 폴더는 **Config Server에서 사용할 설정 파일**을 저장하는 곳입니다.

각 서비스별로 폴더를 만들어, **서비스 이름을 기준으로 config를 관리**합니다.

```
configs/
├─ service-a/
│  ├─ application.yml         # 기본(default) 설정
│  └─ application-local.yml   # local profile 전용 설정
├─ service-b/
│  ├─ application.yml
│  └─ application-local.yml
└─ service-c/
   ├─ application.yml
   └─ application-local.yml
```

⚠️ **중요:**
- 각 서비스 폴더 이름은 반드시 **클라이언트의 `spring.application.name`과 동일**해야 합니다.
  - 예: `service-a` 클라이언트 → `configs/service-a/`

- 각 설정 파일 이름은 **profile과 일치**해야 합니다.
  - 예: `spring.profiles.active=local` → `application-local.yml`

이 규칙을 지켜야 Config Server가 각 서비스별, profile별 설정을 올바르게 제공할 수 있습니다.