# AI Narrative Dictionary Supplement

This directory provides the AI keyword dictionary and stop-word list accompanying the Chinese annual-report text analysis described in the manuscript. The files can be browsed and downloaded directly from GitHub.

## Contents

- `AI_keyword_dictionary.csv`: 218 unique Chinese keyword entries, with IDs, category labels in English and Chinese, and English glosses.
- `stopwords_zh.txt`: 746 stop-word entries, including Chinese words, punctuation, and numeric tokens, with one entry per line.
- `requirements.txt`: the recorded Jieba dependency version, with Python version information in comments.

The CSV and stop-word list use UTF-8 encoding.

## Keyword dictionary

`AI_keyword_dictionary.csv` contains the following five columns:

| Column | Description |
|---|---|
| `id` | Sequential entry identifier, from 1 to 218 |
| `category` | Category label in English |
| `category_zh` | Category label in Chinese |
| `keyword_zh` | Chinese keyword entry used for matching |
| `keyword_en` | English gloss for readers |

Each value in `keyword_zh` occurs once. English glosses are explanatory labels and are not used for segmentation, filtering, or keyword matching.

The dictionary covers four categories:

| Category | Number of terms |
|---|---:|
| AI Hardware Platform | 28 |
| General AI Technologies | 55 |
| Key AI Technologies | 119 |
| AI Application Fields | 16 |

The CSV is a structured reference table, not a file that can be loaded directly with `jieba.load_userdict()`.

## Python dependency

From this directory, install the documented segmentation dependency with:

```bash
python -m pip install -r requirements.txt
```

`requirements.txt` specifies `jieba==0.42.1`. The `jieba.posseg` module is included in Jieba and requires no separate installation. Python `3.9.25` is noted in the comments as the version recorded in the notebook metadata; the Python interpreter must be installed separately. The dependency file records the available version information rather than a complete historical environment.

## Preprocessing description

The preprocessing described for the study uses Jieba part-of-speech segmentation. After segmentation, non-Chinese characters are removed, stop words are removed using `stopwords_zh.txt`, and one-character tokens are excluded. The AI keyword entries are provided in the `keyword_zh` column of `AI_keyword_dictionary.csv`.

The denominator used for the reported keyword frequency is the number of retained tokens after these filters.

This supplement provides dictionary resources and dependency information. Annual-report source texts and preprocessing code are not included.
