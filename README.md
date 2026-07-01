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

## Contributing

Notebooks are noisy in git: run outputs (execution counts, printed values, images) differ machine to machine and version to version, and they aren't meaningful diffs anyway. This repo uses [`nbstripout`](https://github.com/kynan/nbstripout) to strip outputs from `.ipynb` files automatically on commit, so only real code changes show up in `git diff`.

After `pip install -r requirements.txt` (which includes `nbstripout`), run once per clone:

```bash
nbstripout --install --attributes .gitattributes
```

This is a local git config change (not itself version-controlled), so every contributor needs to run it once. `.gitattributes` is committed and tells git *which* files to filter; the install command wires up *how*.
