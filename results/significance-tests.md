# Significance Testing - Domain Effect on Fertility

**Date:** 2026-10-06

## Per-tokenizer one-way ANOVA (per-sentence fertility across 5 domains)

| tokenizer    |        F |         p |   eta2 |
|:-------------|---------:|----------:|-------:|
| indic-bert   |  1273.08 | 0         | 0.0924 |
| muril        | 11420.3  | 0         | 0.4775 |
| punjabi-bert | 11420.3  | 0         | 0.4775 |
| mbert        |  4806.35 | 0         | 0.2777 |
| xlm-r        |  5420.3  | 0         | 0.3025 |
| llama-3      |  1649.72 | 0         | 0.1166 |
| gpt-4o       |  2272.84 | 0         | 0.1539 |
| sarvam-1     |  3502.67 | 0         | 0.2189 |
| corpus-bpe   |   183.61 | 1.73e-156 | 0.0145 |

## Global Friedman test (domain as repeated factor across 9 tokenizers)

chi^2 = 13.689, p = 8.36e-03

## Mean fertility by domain (hardest last)

|              |     0 |
|:-------------|------:|
| literature   | 2.404 |
| agricultural | 2.454 |
| web          | 2.478 |
| news         | 2.558 |
| religious    | 2.846 |
