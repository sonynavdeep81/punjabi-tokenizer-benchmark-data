# Punjabi Tokenizer Fertility Benchmark: Corpus and Results

Data release for the paper *Per-Domain Tokenizer Fertility Benchmark for Gurmukhi Punjabi*.

This repository contains the evaluation corpus and the benchmark results. It does not contain code.

## Corpus

The corpus is attached to the [`corpus-v1` release](../../releases/tag/corpus-v1) as `punjabi-5domain-corpus.parquet`.

- 50,000 Gurmukhi Punjabi text units, 10,000 per domain.
- One Apache Parquet file with two columns: `text` and `domain`.

| Domain | Units | Median words | Mean words | Source |
|---|---:|---:|---:|---|
| News | 10,000 | 47 | 100 | L3Cube-IndicNews (Punjabi) |
| Religious | 10,000 | 6 | 7 | `surindersinghssj/gurbani-sehajpath` |
| Literature | 10,000 | 14 | 18 | Bhai Vir Singh novels (Internet Archive OCR) |
| Web | 10,000 | 296 | 484 | `ai4bharat/sangraha` (Punjabi) |
| Agricultural | 10,000 | 393 | 611 | `ai4bharat/sangraha` (Punjabi, keyword-filtered) |

Load it with pandas:

```python
import pandas as pd
df = pd.read_parquet("punjabi-5domain-corpus.parquet")
```

## Results

The `results/` folder holds the benchmark outputs (9 tokenizers × 5 domains × 5 metrics):

| File | Content |
|---|---|
| `corpus-stats.*` | Per-domain corpus statistics |
| `full-benchmark.*` | All metric values per tokenizer and domain |
| `significance-tests.*` | Statistical significance tests |
| `downstream-correlation.*` | Fertility vs. classification Macro-F1 correlation |
| `benchmark-heatmap.png` | Fertility heatmap |
| `fertility-vs-f1.png` | Fertility vs. Macro-F1 plot |

Each table is available as `.csv` (machine-readable) and `.md` (human-readable).

## License

The corpus and results are released under [CC BY-NC-SA 4.0](LICENSE), for research and non-commercial use.

The news domain (L3Cube-IndicNews) is licensed CC BY-NC-SA 4.0; its NonCommercial-ShareAlike terms apply to the whole corpus. The other domains are license-compatible: the literature texts are in the public domain, and the religious, web and agricultural sources are CC BY 4.0.
