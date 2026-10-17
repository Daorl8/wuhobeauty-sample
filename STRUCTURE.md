# STRUCTURE · wuhobeauty-sample

```
wuhobeauty-sample/
├─ index.html                 단일 파일 (CSS·JS 인라인)
├─ wrangler.toml              name = wuhobeauty-sample → wuhobeauty-sample.lgt3232.workers.dev
├─ .assetsignore              img/·feedback_1/·feedback_2/·문서·index_*.html·미사용 webp 9장 배포 제외
├─ wh-gilda.woff2             영문 제목 (Gilda Display)
├─ wh-interop-400/500.woff2   한글·본문 (Interop · 사용 글자만 → 글자 추가 시 재생성)
├─ wh-owner.webp              원장 증명사진 480×640 (PC 히어로 프로필 카드)
├─ wh-owner-lg.webp           원장 사진 900×1125 (모바일 히어로 `.m-portrait`, 화면엔 최대 240px)
├─ wh-wed1~4.webp             웨딩 슬라이더 사진 800×1000 (feedback_2 원본)
├─ wh-*.webp                  사용 중: hero·ba·strip(히어로 크로스페이드) · wedding · cooling · owner
├─ feedback_1/ · feedback_2/  사장님 피드백 자료 (배포 · 깃허브 업로드 제외)
├─ favicon.png                연분홍 그라데이션 + W
├─ og-wuho.jpg                공유 썸네일 1200×630
├─ img/                       다올 제공 원본 131장 (배포 제외)
└─ CHANGELOG.md / STRUCTURE.md
```

## 섹션 순서
(v0.2) 헤더 → 히어로(원장 프로필 카드 `.profile` + `#slides`) → `#pro`(이력 6칸 `.creds`) → `#signature`(글 카드 3, 분홍 면) → `#reviews`(네이버 리뷰 흐르는 띠 `#rv-track`) → `#menu`(토글 2, 분홍 면) → `#wedding`(그라데이션 면, 구성 표기 + 사진 슬라이더 `#ws-track`) → `#curriculum`(STEP 01~05 토글 `.cur` + 마무리 `.cur-close`) → `#academy`(소개 + 사진 + 수강 코스 3) → `#visit`(주소 · 영업시간 · 출입 안내 + 버튼 5 + 구글 지도) → 푸터.

## 모바일 전용 (899px 이하)
- `.m-portrait`: 히어로 맨 위 원장 사진(가운데 작게). PC에선 display:none.
- 599px 이하: 히어로 Hard · Soft · Sugaring · Sugar paste를 4칸 한 줄로.
- `#float-cta`: 하단 고정 예약 바. 히어로 `.cta`가 화면 위로 지나가면 `.on`(setInterval 150ms 검사).

## 리빌
`.reveal` 요소는 윗변이 화면 78% 선을 넘을 때 `.in`이 붙음(setInterval 120ms 검사, 스크립트 맨 아래). 더 일찍 보이게 하려면 `window.innerHeight*0.78`의 숫자를 키우면 됨(1 = 화면 맨 아래에 닿자마자).
토글 JS는 `.acc details, .cur details` 둘 다 처리.

## 가격 수정
`.price` 안 `<div class="row"><dt>영문<small>한글</small></dt><dd>금액<small>원</small></dd></div>`. 시그니처 표시는 dt 안 `<span class="tag">Signature</span>`. 시그니처 3 카드 가격은 `#signature .pr`, 웨딩은 `.wed-list`에도 있으니 함께 수정.

## 색
`--grad` 그라데이션이 포인트. 글자색으로 분홍은 쓰지 않음(대비 부족).

## 폰트 재생성
`pyftsubset … --name-IDs='*' --name-languages='*' --name-legacy` (LESSONS §24).

## 리뷰 추가 · 수정
`#rv-track` 안 `<article class="rv-card">` 한 개 = 리뷰 1개. 닉네임은 앞 2글자 + * 처리. JS가 카드 묶음을 자동 복제해 끊김 없이 반복하므로 원본만 고치면 됨. 새 글자가 들어가면 Interop 서브셋 재생성.

## 웨딩 슬라이더 사진 추가
`#ws-track` 안에 `<img>` 추가(4:5 비율 권장). 점(dot)은 JS가 사진 수만큼 자동 생성.
