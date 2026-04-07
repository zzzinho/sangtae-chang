# sangtae-chang

세션 정보, 컨텍스트 사용량, Git 상태, 레이트 리밋, 비용을 두 줄로 표시하는 Claude Code 플러그인입니다.

[English](docs/README.en.md)

```
🏷️  my-session  🤖 Opus (200K context)  ▰▰▰▰▰▰▱▱▱▱▱▱▱▱▱▱▱▱▱▱ 45K/200K (30%)  📔 ~/Code/my-project  🌿 main* (+42 -7)
🔋 5h ▰▰▰▰▰▰▱▱▱▱▱▱ 48% →14:30  🗓️  7d ▰▰▰▱▱▱▱▱▱▱▱▱ 25%  💰 Cost $1.23
```

## 표시 항목

**Line 1 — 환경**
- 세션 이름 또는 ID
- 모델명 및 컨텍스트 윈도우 크기
- 컨텍스트 사용량 프로그레스 바 (초록/노랑/빨강 색상)
- 토큰 사용량 (사용/최대)
- 작업 디렉토리
- Git 브랜치, 변경 여부(*), 코드 변경량 (+/-)

**Line 2 — 사용량**
- 5시간 레이트 리밋 바 및 리셋 시간
- 7일 레이트 리밋 바
- 세션 비용 (USD)

## 요구사항

- [jq](https://jqlang.github.io/jq/) — statusline 스크립트에서 JSON 파싱에 사용
- git (선택사항, 브랜치/변경 상태 표시용)

## 설치

### 1. Marketplace 등록 후 설치

```bash
# marketplace 등록 (최초 1회)
/plugin marketplace add zzzinho/sangtae-chang

# 플러그인 설치
/plugin install sangtae-chang@sangtae-chang

# statusline 설정
/sangtae-chang:setup
```

## 제거

```
/plugin uninstall sangtae-chang
```

## 라이선스

MIT
