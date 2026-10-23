# 국내상장 해외ETF vs 미국 직투 세후 비교 계산기 · 똑재TV

일반계좌에서 국내상장 미국 ETF와 미국 주식·ETF 직접 투자 중 어느 쪽이 세후로 더 남는지 보유 기간 전체로 비교합니다. 배당세·매매차익 15.4% vs 양도세 22%·250만원 공제, 금융소득종합과세·건보료까지 2026년 기준.

- 사이트(배포 후): https://ttokjaetv.github.io/etf-vs-direct/
- 단일 HTML 계산기 (index.html). 외부 의존: Pretendard·Chart.js(jsDelivr)
- 수정 후 GitHub Desktop에서 Commit → Push
- 제도 숫자는 허브의 `rules/v2026.2/rules.js`(전역 `TTOKJAE_RULES`), 세금·건보료 계산식(누진세·금융소득종합과세·건보료·재산 점수·피부양자 요건·해외주식 양도세)은 허브의 공용 계산 엔진 `rules/calc-v2.js`(전역 `TTOKJAE_CALC`, 2026-10-23부터 — 표준세액공제에 소득세법 제61조② 한도)에서 온다. index.html의 '세금 엔진' 블록은 엔진을 부르는 얇은 껍데기(옛 함수 이름·결과 그대로)이며 fin-income-tax와 글자까지 같게 유지한다.
- 계산 테스트: `node tests/engine.test.js` — index.html에서 세금 엔진 블록을 꺼내 실행(rules·calc-v*는 위쪽 폴더의 허브 clone, 없으면 고정 주소). 자동 검사(rules-guard)가 부른다.
