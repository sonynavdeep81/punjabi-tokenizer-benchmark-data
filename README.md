# Punjabi Tokenizer Fertility Benchmark: Corpus and Results

Data release for the paper *Domain Matters: Tokenizer Fertility and Downstream Performance across Gurmukhi Punjabi Domains*.

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

## Sources and attribution

Every text unit is derived from one of the sources below. We **modified** all source texts: we selected Gurmukhi-only units, applied length filters, removed duplicates, sampled 10,000 units per domain, and (agricultural domain) filtered by keyword. No source author endorses this corpus.

| Domain | Source and creator | License | Link |
|---|---|---|---|
| News | L3Cube-IndicNews (Punjabi), L3Cube Pune (Mirashi et al., ICON 2023), commit `6c825e7` | [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/); released "for research purposes only" | https://github.com/l3cube-pune/indic-nlp |
| Religious | `gurbani-sehajpath`, by Surinder Singh (HuggingFace `surindersinghssj`), revision `0ed6fbd` | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/); underlying scripture (Sri Guru Granth Sahib) is public domain | https://huggingface.co/datasets/surindersinghssj/gurbani-sehajpath |
| Web, Agricultural | Sangraha (Punjabi, verified split), AI4Bharat (Khan et al., ACL 2024), revision `8b813c3` | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | https://huggingface.co/datasets/ai4bharat/sangraha |
| Literature | Bhai Vir Singh (1872 to 1957): *Sundri* (1898), *Satwant Kaur* (1900), *Baba Naudh Singh* (1917 to 1921); OCR text from the Internet Archive; body narrative only | Public domain (India: author's life + 60 years, expired 2018; US: published before 1930) | https://archive.org/details/SundriBhaiVirSinghPunjabi, https://archive.org/details/satwant-kaur-bhai-vir-singh-punjabi, https://archive.org/details/baba-naudh-singh |

The news and web texts were originally published by third-party websites; their inclusion here relies on the licenses granted by the dataset publishers above.

## Takedown

If you hold rights in any text in this corpus and want it removed, open an issue in this repository and we will remove it in the next release.
