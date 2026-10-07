# Full Tokenizer Benchmark — Punjabi (5 Metrics × 9 Tokenizers × 5 Domains)

**Corpus:** 50,000 sentences (10 K × 5 domains)
**Date:** 2026-10-06

## Tokenizers

| ID | Model | Algorithm | Group |
|---|---|---|---|
| indic-bert | ai4bharat/indic-bert | — | Indic-specialized |
| muril | google/muril-base-cased | — | Indic-specialized |
| punjabi-bert | l3cube-pune/punjabi-bert | — | Indic-specialized |
| mbert | bert-base-multilingual-cased | — | General multilingual |
| xlm-r | xlm-roberta-base | — | General multilingual |
| llama-3 | NousResearch/Meta-Llama-3-8B | — | English-centric LLM |
| gpt-4o | o200k_base | — | English-centric LLM |
| sarvam-1 | sarvamai/sarvam-1 | — | Indic-specialized LLM |
| corpus-bpe | corpus-trained | — | Domain-matched |


## Results

### Fertility (↓ better)

| domain       |   indic-bert |   muril |   punjabi-bert |   mbert |   xlm-r |   llama-3 |   gpt-4o |   sarvam-1 |   corpus-bpe |
|:-------------|-------------:|--------:|---------------:|--------:|--------:|----------:|---------:|-----------:|-------------:|
| agricultural |        1.703 |   1.385 |          1.385 |   2.536 |   1.772 |     7.853 |    2.637 |      1.638 |        1.181 |
| literature   |        1.569 |   1.559 |          1.559 |   2.46  |   1.822 |     7.117 |    2.511 |      1.809 |        1.233 |
| news         |        1.762 |   1.415 |          1.415 |   2.711 |   1.801 |     8.075 |    2.841 |      1.798 |        1.2   |
| religious    |        1.608 |   2.119 |          2.119 |   3.152 |   2.315 |     7.782 |    3     |      2.272 |        1.242 |
| web          |        1.724 |   1.406 |          1.406 |   2.577 |   1.766 |     7.884 |    2.669 |      1.656 |        1.213 |
| macro-avg    |        1.673 |   1.577 |          1.577 |   2.687 |   1.895 |     7.742 |    2.732 |      1.835 |        1.214 |
### Byte-per-token (↑ better)

| domain       |   indic-bert |   muril |   punjabi-bert |   mbert |   xlm-r |   llama-3 |   gpt-4o |   sarvam-1 |   corpus-bpe |
|:-------------|-------------:|--------:|---------------:|--------:|--------:|----------:|---------:|-----------:|-------------:|
| agricultural |        7.525 |   9.302 |          9.302 |   5.062 |   7.269 |     1.632 |    4.866 |      7.872 |       10.882 |
| literature   |        7.509 |   7.65  |          7.65  |   4.777 |   6.53  |     1.625 |    4.683 |      6.76  |        9.558 |
| news         |        7.526 |   9.497 |          9.497 |   4.914 |   7.44  |     1.64  |    4.681 |      7.556 |       11.13  |
| religious    |        7.896 |   6.034 |          6.034 |   4.001 |   5.483 |     1.611 |    4.206 |      5.576 |       10.288 |
| web          |        7.48  |   9.241 |          9.241 |   5.015 |   7.356 |     1.635 |    4.839 |      7.867 |       10.69  |
| macro-avg    |        7.587 |   8.345 |          8.345 |   4.754 |   6.816 |     1.628 |    4.655 |      7.126 |       10.509 |
### OOV rate (↓ better)

| domain       |   indic-bert |   muril |   punjabi-bert |   mbert |   xlm-r |   llama-3 |   gpt-4o |   sarvam-1 |   corpus-bpe |
|:-------------|-------------:|--------:|---------------:|--------:|--------:|----------:|---------:|-----------:|-------------:|
| agricultural |        0     |   0.001 |          0.001 |   0.001 |       0 |         0 |        0 |          0 |            0 |
| literature   |        0.002 |   0.002 |          0.002 |   0.002 |       0 |         0 |        0 |          0 |            0 |
| news         |        0     |   0.001 |          0.001 |   0.003 |       0 |         0 |        0 |          0 |            0 |
| religious    |        0     |   0.001 |          0.001 |   0     |       0 |         0 |        0 |          0 |            0 |
| web          |        0     |   0.001 |          0.001 |   0.001 |       0 |         0 |        0 |          0 |            0 |
| macro-avg    |        0.001 |   0.001 |          0.001 |   0.001 |       0 |         0 |        0 |          0 |            0 |
### Token-char ratio (↓ better)

| domain       |   indic-bert |   muril |   punjabi-bert |   mbert |   xlm-r |   llama-3 |   gpt-4o |   sarvam-1 |   corpus-bpe |
|:-------------|-------------:|--------:|---------------:|--------:|--------:|----------:|---------:|-----------:|-------------:|
| agricultural |        0.336 |   0.274 |          0.274 |   0.5   |   0.35  |     1.55  |    0.52  |      0.324 |        0.234 |
| literature   |        0.341 |   0.339 |          0.339 |   0.535 |   0.396 |     1.553 |    0.546 |      0.39  |        0.269 |
| news         |        0.331 |   0.266 |          0.266 |   0.507 |   0.338 |     1.514 |    0.532 |      0.338 |        0.226 |
| religious    |        0.341 |   0.448 |          0.448 |   0.665 |   0.489 |     1.639 |    0.633 |      0.48  |        0.264 |
| web          |        0.338 |   0.276 |          0.276 |   0.505 |   0.346 |     1.545 |    0.523 |      0.325 |        0.238 |
| macro-avg    |        0.337 |   0.321 |          0.321 |   0.542 |   0.384 |     1.56  |    0.551 |      0.371 |        0.246 |
### RFR vs corpus-BPE (↓ better, 1.0 = reference)

| domain       |   indic-bert |   muril |   punjabi-bert |   mbert |   xlm-r |   llama-3 |   gpt-4o |   sarvam-1 |   corpus-bpe |
|:-------------|-------------:|--------:|---------------:|--------:|--------:|----------:|---------:|-----------:|-------------:|
| agricultural |        1.445 |   1.172 |          1.172 |   2.151 |   1.5   |     6.674 |    2.237 |      1.387 |            1 |
| literature   |        1.28  |   1.265 |          1.265 |   2.015 |   1.48  |     5.882 |    2.051 |      1.45  |            1 |
| news         |        1.479 |   1.18  |          1.18  |   2.273 |   1.507 |     6.809 |    2.384 |      1.497 |            1 |
| religious    |        1.318 |   1.731 |          1.731 |   2.588 |   1.892 |     6.394 |    2.457 |      1.86  |            1 |
| web          |        1.427 |   1.159 |          1.159 |   2.133 |   1.457 |     6.547 |    2.21  |      1.366 |            1 |
| macro-avg    |        1.39  |   1.301 |          1.301 |   2.232 |   1.567 |     6.461 |    2.268 |      1.512 |            1 |


## Notes

- **OOV = 0** for llama-3, gpt-4o: both use byte-level BPE — every byte is encodable, no UNK.
- **RFR = 1.0** for corpus-bpe (reference by definition).
- punjabi-bert replaces PunGPT2 (arXiv 2508.01918 has no public HF release).
