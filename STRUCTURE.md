# STRUCTURE · wuhobeauty-sample

```
wuhobeauty-sample/
├─ index.html                 단일 파일 (CSS·JS 인라인)
├─ wrangler.toml              name = wuhobeauty-sample → wuhobeauty-sample.lgt3232.workers.dev
├─ .assetsignore              img/·문서·index_*.html·미사용 wh-mist.webp 배포 제외
├─ wh-gilda.woff2             영문 제목 (Gilda Display)
├─ wh-interop-400/500.woff2   한글·본문 (Interop · 사용 글자만 → 글자 추가 시 재생성)
├─ wh-*.webp                  사진 13장 (hero·ba·strip = 히어로 크로스페이드)
├─ favicon.png                연분홍 그라데이션 + W
├─ og-wuho.jpg                공유 썸네일 1200×630
├─ img/                       다올 제공 원본 131장 (배포 제외)
└─ CHANGELOG.md / STRUCTURE.md
```

## 섹션 순서
헤더 → 히어로(`#slides`) → 강조 띠 `.hl`(5칸) → `#signature`(3) → `#quick` → `#technique`(4 + `#prenatal` 박스 + 사진 4) → `#menu`(토글 2 + 365 이벤트) → `#wedding`(그라데이션 면) → `#pro`(이력 6) → `#academy`(카드 3) → `#visit`(버튼 6 + 지도) → 푸터.

## 가격 수정
`.price` 안 `<div class="row"><dt>영문<small>한글</small></dt><dd>금액<small>원</small></dd></div>`. 시그니처 표시는 dt 안 `<span class="tag">Signature</span>`. 시그니처 3 카드 가격은 `#signature .pr`, 웨딩은 `.wed-list`에도 있으니 함께 수정.

## 색
`--grad` 그라데이션이 포인트. 글자색으로 분홍은 쓰지 않음(대비 부족).

## 폰트 재생성
`pyftsubset … --name-IDs='*' --name-languages='*' --name-legacy` (LESSONS §24).
