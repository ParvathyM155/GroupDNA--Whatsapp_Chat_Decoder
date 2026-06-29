# GroupDNA — Your WhatsApp Group Chat, Decoded

> Analyse a WhatsApp group export and surface hidden patterns — who texts at 2 AM, who never replies, and what the group can't stop talking about.

---

## Screenshot

<img width="555" height="1013" alt="66a0a1b4e6d541a18ed185756d08b8c2" src="https://github.com/user-attachments/assets/e923d619-d886-4ccd-bf67-7911873b8517" />




---

## What it does

GroupDNA parses a raw WhatsApp `.txt` export and runs eight analytical features entirely in plain Python + NumPy — no pandas, no plotting libraries, no ML:

| # | Feature | What you learn |
|---|---------|---------------|
| 1 | **Chat Parser** | Cleans raw export into structured messages; counts system / media / deleted entries |
| 2 | **Group Overview** | Total messages, date range, per-person share (%), word counts, avg message length |
| 3 | **Busiest Day & Hour** | Single peak day and peak hour across the full dataset |
| 4 | **Activity Heatmap** | 6 × 24 NumPy matrix rendered as a terminal block-character heatmap |
| 5 | **Top Words** | Group-wide top 10 + per-person top 5 (stopwords filtered manually) |
| 6 | **Response Patterns** | Average reply-time gaps; fastest and slowest repliers |
| 7 | **Personality Archetypes** | Assigns each member one role: Spammer, Night Owl, Ghost, Storyteller, etc. |
| 8 | **Final Report** | Single consolidated printout combining all features above |

---

## How to run

**Requirements:** Python 3.8+, NumPy. Nothing else.

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/GroupDNA.git
cd GroupDNA

# 2. Install the only dependency
pip install numpy

# 3. Place your chat export in the same folder
#    Export from WhatsApp → ⋮ → More → Export chat → Without media
#    Rename the file to:
cp "WhatsApp Chat with Hostel Bois.txt" hostel_bois.txt

# 4. Open and run the notebook
jupyter notebook GroupDNA__Parvathy_M_.ipynb
```

Run all cells top-to-bottom. The final cell prints the complete GroupDNA Report.

---

## Constraint list

### You CAN use
- All Python fundamentals (variables, data types, conditionals, loops, functions, f-strings, `split`, `map`, `lambda`)
- Lists, tuples, sets, dictionaries
- NumPy (`np.zeros`, `np.ones`, `np.arange`, `np.full`, `np.eye`, `reshape`, indexing, slicing, `sum`, `mean`, `max`, `min`)
- `open()` and file reading — `readlines()` / `.read()`
- `datetime` module — only `datetime.strptime` and `timedelta`
- String methods: `split`, `strip`, `lower`, `upper`, `startswith`, `endswith`, `replace`, `isupper`, `isdigit`, `isalpha`, `count`, `find`
- List / dict comprehensions
- `sorted()` with `key=` and `reverse=`

### You CANNOT use
- `pandas` (no DataFrame, no `read_csv`, nothing)
- `matplotlib`, `seaborn`, `plotly` — visualisation is text-based only
- `collections.Counter` — built a manual dict counter instead
- `collections.defaultdict` — used `.get()` / `in` checks instead
- `re` (regex) — all pattern matching done with string methods
- Any pre-built WhatsApp chat analyser library
- Any AI / ML library (no scikit-learn, no nltk)
- Any external chat datasets — only `hostel_bois.txt` used for submission

---

## Seven-day build log

| Day | What I worked on |
|-----|-----------------|
| 1 | Read the project brief; sketched feature list; wrote and tested the chat parser (Feature 1) |
| 2 | Built Group Overview (Feature 2); handled edge cases for media-omitted and deleted messages |
| 3 | Added Busiest Day & Hour (Feature 3); debugged timestamp format differences |
| 4 | Built the 6 × 24 NumPy heatmap matrix and block-character renderer (Feature 4) — the core NumPy feature |
| 5 | Wrote Top Words (Feature 5) with a custom stopword list; tuned per-person top-5 output |
| 6 | Built Response Patterns (Feature 6), Silent Streaks, and all nine Archetype metrics (Feature 7) |
| 7 | Integrated everything into the Final Report (Feature 8); cleaned up output formatting; wrote README |

---

## Project structure

```
GroupDNA/
├── GroupDNA__Parvathy_M_.ipynb   # Main notebook — run this
├── hostel_bois.txt               # WhatsApp export (required, not tracked in git)
└── README.md
```

---

*Built by Parvathy M · June 2026*
