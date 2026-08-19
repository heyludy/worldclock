# 🇺🇸 🇨🇭 🇰🇷 우리 셋 시계

미국(필라델피아) · 스위스(취리히) · 한국(서울) 세 도시의 현재 시각을 한 화면에서 보는 페이지.

**👉 https://heyludy.github.io/worldclock/**

## 기능

- 세 도시 실시간 시계 (1초마다 갱신)
- 날짜 · 요일 · 어제/내일 표시
- 한국 기준 시차 표시
- 아침/낮/저녁/밤 상태 표시
- **약속 시간 맞춰보기** — 슬라이더로 ±24시간 이동하면 세 도시 시간이 같이 움직임
- 서머타임(DST) 자동 반영 — 브라우저 `Intl` API의 IANA 타임존 데이터를 사용하므로 별도 관리 불필요
- 모바일 대응, 다크/라이트 모드 자동

## 구조

`index.html` 파일 하나. 빌드 도구·의존성 없음. 브라우저에서 바로 열어도 동작함.

## 도시 바꾸기

`index.html` 안의 `ZONES` 배열만 수정하면 됨.

```js
var ZONES = [
  { key: "us", flag: "🇺🇸", city: "필라델피아", country: "미국 · 동부", tz: "America/New_York" },
  { key: "ch", flag: "🇨🇭", city: "취리히",     country: "스위스",      tz: "Europe/Zurich" },
  { key: "kr", flag: "🇰🇷", city: "서울",       country: "한국",        tz: "Asia/Seoul" }
];
```

`tz`는 [IANA 타임존 이름](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)을 쓴다.
시차 기준 도시는 바로 아래 `BASE` 값(`"kr"`)으로 정한다.

## 배포

`main` 브랜치에 push하면 GitHub Pages가 자동으로 반영한다.
