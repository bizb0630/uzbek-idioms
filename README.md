---
language:
- uz
license: cc-by-nc-4.0
task_categories:
- text-generation
- text-classification
tags:
- uzbek
- idioms
- fine-tuning
- nlp
- phraseology
pretty_name: Uzbek Idioms
size_categories:
- 1K<n<10K
---

# Uzbek Idioms

Structured dataset of Uzbek idiomatic expressions extracted from *O'zbek tili frazeologik lug'ati* (2022). Made it for fine-tuning since no machine-readable version of this dictionary existed, so here's one.

**4,408 entries.** Each row is one meaning of one idiom.

---

## Fields

| Field | Description |
|---|---|
| `idiom` | The idiomatic expression |
| `syntax_markers` | Argument slots: `kim?`, `nima? kimga?`, etc. |
| `meaning_uz` | Definition in Uzbek |
| `meaning_number` | For polysemous entries (`1`, `2`, `3` …) |
| `homonym_number` | For homonyms (`I`, `II`) |
| `variants` | Variant forms of the same idiom |
| `synonyms` | Synonymous idioms |
| `antonyms` | Antonymous idioms |
| `register_note` | Usage restrictions if any |
| `example_uz` | Literary example sentence |
| `source_author` | Author of the example |
| `source_work` | Title of the source work |

---

## Quick look

```
idiom:          AFSUS YEMOQ
syntax_markers: kim?
meaning_uz:     afsuslanmoq, achinmoq, o'kinmoq, pushaymon bo'lmoq.
example_uz:     Shu o'tirishga borganligimdan afsus yedim, bilmasdan borib qolibman.
source_author:  Mushtum.
```

```
idiom:          AYOL BOSHI BILAN
meaning_uz:     ojiz, mungli, mushtupar holida.
variants:       xotin boshi bilan
example_uz:     Ayol boshim bilan deganingiz mungli, mushtiparman deganingizmi?
                Endi xotin boshi bilan Marg'ilonga murojaat qilsinmi?
source_author:  A.Qodiriy
source_work:    O'tkan kunlar
```




---

## Load

```python
from datasets import load_dataset
ds = load_dataset("bizb0630/uzbek-idioms")
```

```python
import pandas as pd
df = pd.read_csv("uzbek_idioms.csv")
```

---

## Notes

- Apostrophes normalized to U+2019 (`'`) across all fields
- Polysemous idioms appear as multiple rows with the same `idiom` value and different `meaning_number`
- Cross-reference entries from the original dictionary are stored as `variants` of their main entry

---

## Source

Sh.Rahmatullayev, N.Mahmudov, Z.Xolmanova, I.O'razova, K.Rixsiyeva.
*O'zbek tili frazeologik lug'ati*. Toshkent: G'afur G'ulom nomidagi
nashriyot-matbaa ijodiy uyi, 2022. 636 b. ISBN 978-9943-8835-4-3.

## License

[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) - non-commercial use only. Please cite the original dictionary if you use this dataset.
