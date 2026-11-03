# Hindi and Bhojpuri Stop Words for NLP

Stop-word lists of 100 words each for **Hindi** and **Bhojpuri**, written in Roman (Latin) letters and transliterated from Devanagari, for use in Natural Language Processing (NLP) text preprocessing.

**Author:** Aditya Kumar

**Semester:** Monsoon Semester 2026

**Affiliation:** Department of Humanities and Social Sciences, Indian Institute of Technology (Indian School of Mines), Dhanbad

**Project webpage:** https://adityakumar190.github.io/hindi-bhojpuri-stopwords/

## Research question

How do the stop words of Hindi and Bhojpuri differ in their postpositions, pronouns and auxiliary verbs, and what do these differences mean for building a stop-word list for each language?

## What are stop words?

Stop words are very frequent function words, such as conjunctions, pronouns, postpositions and auxiliary verbs, that add little to the meaning of a sentence (for example, Hindi *aur* "and" and *hai* "is"). Removing them during preprocessing reduces vocabulary size and noise, so that tasks like text classification, information retrieval and topic modelling can focus on content words.

## Repository contents

| File | Description |
|---|---|
| `hindi_stopwords.py` | Python list `hindi_stopwords` with 100 words |
| `bhojpuri_stopwords.py` | Python list `bhojpuri_stopwords` with 100 words |
| `index.html` | Project webpage (published with GitHub Pages) |
| `README.md` | This file |

## How the lists were prepared

1. **Selection.** Common function words were chosen from six groups: conjunctions, pronouns, postpositions, auxiliary verbs, interrogatives, and negations and quantifiers.
2. **No overlap.** A word common to both languages is placed in the Hindi list only; the Bhojpuri list uses its own distinctive form.
3. **Romanisation.** Words use commonly seen Roman spellings. Frequent variants (for example, *nahi* and *nahin*) are both included.
4. **Verification.** Each list has exactly 100 entries, with no repeats within a list and no word shared between the two lists.

## Usage

Clone or download the repository, keep the two `.py` files in your project folder, and import them:

```python
import re
from hindi_stopwords import hindi_stopwords
from bhojpuri_stopwords import bhojpuri_stopwords

stop = set(hindi_stopwords) | set(bhojpuri_stopwords)   # combined list

text = "mera gaon Bihar mein hai"
tokens = re.findall(r"[a-z]+", text.lower())
print([t for t in tokens if t not in stop])             # ['gaon', 'bihar']
```

Use one list alone (for example `set(hindi_stopwords)`) when processing text in a single language. Use the combined set for text that mixes both.

## Limitations

- The lists are illustrative, not exhaustive. A larger list can be built by counting word frequencies in a text corpus.
- Roman spelling is not standardised, so a word may appear in other forms than those listed.
- Bhojpuri is spoken across several regions, and some forms differ between speakers.
- Testing stop-word removal for each task is important because negations can carry meaning in tasks like sentiment analysis.

## Citation

Kumar, A. (2026). *Indic Language Stop Words for Natural Language Processing: Hindi and Bhojpuri*. Department of Humanities and Social Sciences, IIT (ISM) Dhanbad.
