# 다단 증폭기 잡음지수 계산기

입력에서 출력으로 연결된 여러 단의 전력 이득과 잡음지수를 Friis 식으로 결합.

- ID: E146
- App: https://nanalab.kr/eng-cascade-noise-figure/
- Repository: https://github.com/NaNaCompany/eng-cascade-noise-figure
- Formula: F_total = F₁ + Σᵢ₌₂ⁿ (Fᵢ−1)/(G₁…Gᵢ₋₁); NF = 10 log₁₀F_total

## Model and data

행을 입력단에서 출력단 순으로 추가하세요. 각 행의 전력 이득과 잡음지수는 모두 dB입니다. 이득 0 dB는 선형 이득 1이며, 음수는 감쇠입니다. 동일 주파수와 동일한 290 K 잡음 기준, 정합된 단 사이 연결과 비상관 부가잡음을 가정합니다. 잡음지수는 0 dB 이상입니다. 임피던스 부정합·역방향 결합·발진·압축과 주파수 변환기의 측파대 관례 차이는 제외합니다.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
