# Financial analysis lessons

Jupyter notebook lessons that build up a small financial-analysis toolkit in Python: parsing raw statement text, then structured CSVs, then pandas.

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate   # on Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook            # or: jupyter lab
```

## Data

`statement.csv` is a sample bank statement used by every lesson. Keep it in the same folder as the notebooks — each one opens it by filename, so moving it will cause a `FileNotFoundError`.

## Lessons

Work through these in order; each one builds on ideas from the last.

1. **`01_regex_lesson.ipynb`** — the regex toolkit (`compile`, `match`, `search`, `findall`, capture groups) for pulling fields out of messy, unstructured statement text.
2. **`02_csv_lesson.ipynb`** — loading a real, structured CSV by hand: parsing amounts and dates, grouping spend by category, reconciling daily balances, and a couple of classic data traps (missing merchant names, near-duplicate transactions).
3. **`03_pandas_lesson.ipynb`** — the same exercises from lesson 2, redone with pandas, to see directly what the library buys you over plain Python, plus a first chart.
