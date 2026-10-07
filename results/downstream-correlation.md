# Downstream Correlation: Fertility <-> Classification Performance

**Date:** 2026-10-06
**Task:** 5-domain Punjabi text classification
**Model:** Embedding(128) -> mean-pool -> MLP (trained from scratch per tokenizer)
**Split:** 80/20 stratified, seed 42, epochs=5

## §5.7 Fertility-Performance Correlation

### Tokenizer-level results (n = 9)

| Group                 | Tokenizer    |   Mean Fertility |   Macro-F1 |
|:----------------------|:-------------|-----------------:|-----------:|
| Domain-matched        | corpus-bpe   |           1.2137 |     0.9024 |
| Indic-specialized     | muril        |           1.5769 |     0.9026 |
| Indic-specialized     | punjabi-bert |           1.5769 |     0.9013 |
| Indic-specialized     | indic-bert   |           1.6733 |     0.8632 |
| Indic-specialized LLM | sarvam-1     |           1.8347 |     0.894  |
| General multilingual  | xlm-r        |           1.8953 |     0.8815 |
| General multilingual  | mbert        |           2.687  |     0.8409 |
| English-centric LLM   | gpt-4o       |           2.7318 |     0.8481 |
| English-centric LLM   | llama-3      |           7.7422 |     0.6778 |

| Level | n | Pearson r | p | Spearman ρ | p |
|---|---|---|---|---|---|
| Tokenizer | 9 | -0.986 | 0.0000 *** | -0.904 | 0.0008 *** |
| Tokenizer (distinct, n=8) | 8 | -0.987 | 0.0000 *** | -0.881 | 0.0039 ** |
| Tokenizer (no llama-3, n=8) | 8 | -0.876 | 0.0043 ** | -0.862 | 0.0059 ** |
| Tokenizer (distinct, no llama-3, n=7) | 7 | -0.871 | 0.0106 * | -0.821 | 0.0234 * |
| Domain × tokenizer | 45 | -0.528 | 0.0002 *** | -0.167 | 0.2719 (n.s.) |

**Interpretation:** At the domain × tokenizer level (n = 45), fertility and per-class F1
show a negative correlation (Pearson r = -0.528 ***,
Spearman ρ = -0.167 (n.s.)).

**Robustness:** The strong tokenizer-level correlation is not an artifact of the
llama-3 outlier (mean fertility ~7.7): removing it leaves Pearson r = -0.876
(**), and the cleanest set (distinct tokenizers, no outlier, n = 7)
gives Pearson r = -0.871 (Spearman ρ = -0.821).

### Per-domain F1 by tokenizer

| Tokenizer    |   agricultural |   literature |   news |   religious |   web |
|:-------------|---------------:|-------------:|-------:|------------:|------:|
| corpus-bpe   |          0.852 |        0.949 |  0.923 |       0.969 | 0.818 |
| gpt-4o       |          0.729 |        0.944 |  0.888 |       0.974 | 0.706 |
| indic-bert   |          0.791 |        0.928 |  0.888 |       0.958 | 0.751 |
| llama-3      |          0.454 |        0.76  |  0.727 |       0.938 | 0.509 |
| mbert        |          0.729 |        0.942 |  0.86  |       0.977 | 0.698 |
| muril        |          0.85  |        0.959 |  0.915 |       0.98  | 0.81  |
| punjabi-bert |          0.847 |        0.959 |  0.914 |       0.979 | 0.807 |
| sarvam-1     |          0.828 |        0.953 |  0.914 |       0.979 | 0.796 |
| xlm-r        |          0.808 |        0.955 |  0.899 |       0.977 | 0.768 |

---
See also: [[full-benchmark]] | [[t3-section5-results]] | [[t3-section6-discussion]]
