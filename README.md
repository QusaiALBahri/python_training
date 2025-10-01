# 🚀 Python Training Journey — From Zero to Shipping (14 Sessions)

**Hands-on. Production-minded. Fun.**  
This repository powers a complete Python training path: from **basics** and **logic** to **OOP**, **data analysis**, **GUI/web**, **automation**, and **AI** — with real deliverables, ticket-driven debugging, and a professional GitHub workflow.

<p align="center">
  <a href="https://www.python.org/"><img alt="Python" src="https://img.shields.io/badge/Python-3.10%2B-blue"></a>
  <img alt="Style: PEP8" src="https://img.shields.io/badge/Style-PEP%208-informational">
  <img alt="Focus: Hands‑on" src="https://img.shields.io/badge/Focus-Hands--on-success">
  <img alt="Tracks" src="https://img.shields.io/badge/Tracks-Basics→OOP→Data→GUI→Web→AI-purple">
</p>

---

## 🧭 Table of Contents
- [Overview](#overview)
- [Roadmap (Sessions)](#roadmap-sessions)
- [Quick Start](#quick-start)
- [Directory Layout](#directory-layout)
- [Code Samples](#code-samples)
- [Tickets & Professional Workflow](#tickets--professional-workflow)
- [Deliverables](#deliverables)
- [Resources](#resources)

---

## Overview
- **Total Sessions:** 14 (each ~3h, last is 2h)  
- **Approach:** Create → Break → Fix → Harden.  
- **Mindset:** Write like an engineer: PEP 8, logging, tests, client proof, GitHub discipline.  
- **Outcomes:** Clean code, data skills, GUI/web apps, automation, and AI integration.

---

## Roadmap (Sessions)

| # | Hours | Focus | What You’ll Do |
|---|:----:|-------|-----------------|
| 1 | 3h | Print/Input, Comments, Variables, Operators, Data Types, Strings, Type Conversion, f-Strings | Playful CLI mini-exercises (Hello + Name, Age next year). Reinforce `type()` early. |
| 2 | 3h | Maths & Modulo, Errors, Functions, Conditionals, Logical Operators | Discount calculator, login check. Trigger errors (e.g., `10/0`) → catch & fix. |
| 3 | 3h | Loops, Loop Control, Lists, Built‑ins, Modules, OOP Intro, Dicts/Tuples/Sets, String Methods | Multiplication table, dice roll, student grades. One class with `__init__` + one method. |
| 4 | 3h | List Comprehensions, Error/File Handling, Custom Modules, Advanced Functions, Decorators, Generators, Date/Time, venv, Pythonic shorthand | Notes/logs writer, one‑liners for data cleaning, concept demos for decorators/generators. |
| 5 | 3h | Professional Workflow — Debugging “Revenue Leaks”, PEP 8, formatting, naming, imports, client verification | Simulate production bug (Shopify‑style). Fix, document, and push to GitHub. |
| 6 | 3h | Systems Engineering — GPA Calculator, File Resilience, Dict vs List at scale, Logging, Refactoring | Build grade system → fix bugs (#701–705). Ship **v1-naive** & **v2-hardened** branches. |
| 7 | 3h | OOP Advanced, Data Structures at Scale, File Mastery, System Refactor | Senior‑engineer refactor of “intern code”. Emphasize auditability + docstrings. |
| 8 | 3h | Agile Sprints + Libraries: `colorama`, `smtplib`, `faker`, `duckdb`, `playsound` | Five mini‑sprints with user stories + commits. Fix injected bugs (#801–805). |
| 9 | 3h | Data Analysis & Visualization (pandas, matplotlib, venv, git) | Clean `sales.csv` (NaNs/dupes), build 4 charts, add business notes. |
| 10 | 3h | Tkinter GUI — Widgets, Geometry (`pack/grid/place`), Events — Flask intro | Build a mini dashboard (multiple widgets). Understand event loop & layouts. |
| 11 | 3h | Flask → PyAutoGUI → AI APIs (OpenAI/DeepSeek/Groq/Google) → Local AI (LM Studio) → HF usage | Integrate APIs, local models, and automation into apps (safe keys/config). |
| 12 | 3h | Extra Resources — Teachable Machine, Automate the Boring Stuff, Hugging Face, W3Schools | Curated self‑learning directions with practical next steps. |
| 13 | 3h | Pandas & Matplotlib (Colab) — Clean → Describe → Pivot/Group → Visualize | Non‑specialist, all‑in‑one workshop. CSV → insights → decisions. |
| 14 | 2h | Logistic Regression — Sigmoid, Decision Boundary, Cost, Gradient Descent, scikit‑learn | First ML algorithm. Intuition + plots + thresholding. |

---

## Quick Start

```bash
# 1) Create & activate a virtual environment
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate

# 2) Install core dependencies
pip install -U pip
pip install numpy pandas matplotlib duckdb faker colorama playsound flask pyautogui scikit-learn

# 3) (Optional) Save exact versions
pip freeze > requirements.txt

# 4) Run a sample
python samples/hello.py
```

> **Note:** `tkinter` is part of standard Python on most systems (on some Linux distros, install `python3-tk`).

---

## Directory Layout

```
📦 python-training
├─ day01_basics/
├─ day02_logic_functions/
├─ day03_loops_structures/
├─ day04_power_user/
├─ day05_workflow_debugging/
├─ day06_systems_gpa/
├─ day07_refactor_oop/
├─ day08_agile_sprints_libs/
├─ day09_data_viz/
├─ day10_gui_tkinter/
├─ day11_web_flask_ai/
├─ day12_extra_resources/
├─ day13_colab_pandas_matplotlib/
├─ day14_logreg_ml/
└─ samples/
   ├─ hello.py
   ├─ discount.py
   ├─ grades_miniclass.py
   ├─ pandas_quickstart.py
   ├─ tkinter_min.py
   ├─ flask_min.py
   └─ logreg_sklearn.py
```

---

## Code Samples

### 1) Foundations — input, f-strings
```python
# samples/hello.py
name = input("Your name: ").strip()
age = int(input("Your age: "))
print(f"Hello, {name}! Next year you'll be {age + 1}.")
print("Type is:", type(name).__name__)
```

### 2) Logic & Errors — discount and division by zero
```python
# samples/discount.py
price = float(input("Price: "))
code = input("Coupon code (VIP10/None): ").strip().upper()
try:
    disc = 0.10 if code == "VIP10" else 0.0
    total = price * (1 - disc)
    print(f"Total: {total:.2f}")
    # force an error to learn try/except
    x = 10 / int(input("Divide 10 by: "))  # try 0
    print("Result:", x)
except ZeroDivisionError:
    print("⚠️ Can't divide by zero — fixed gracefully.")
```

### 3) Loops + OOP — tiny class and list usage
```python
# samples/grades_miniclass.py
class Student:
    def __init__(self, name, grades):
        self.name = name
        self.grades = grades

    def average(self):
        return sum(self.grades) / max(len(self.grades), 1)

s = Student("Lina", [80, 88, 92])
for g in s.grades:
    print("Grade:", g)
print("Average:", s.average())
```

### 4) Power User — list comprehension + file handling
```python
# samples/pandas_quickstart.py (part 1 — no pandas yet)
lines = ["  apple ", "banana", "  cherry  ", None, ""]
clean = [x.strip() for x in lines if x and x.strip()]
with open("notes.txt", "w", encoding="utf-8") as f:
    f.write("\n".join(clean))
print("Saved notes.txt:", clean)
```

### 5) Data Analysis — pandas + matplotlib
```python
# samples/pandas_quickstart.py (part 2)
import pandas as pd
import matplotlib.pyplot as plt

df = pd.DataFrame({
    "city": ["Amman", "Zarqa", "Irbid", "Amman", "Zarqa"],
    "revenue": [1200, 900, 700, 1500, 1100],
})
summary = df.groupby("city", as_index=False)["revenue"].sum()
print(summary)

summary.plot(kind="bar", x="city", y="revenue", title="Revenue by City")
plt.tight_layout()
plt.savefig("revenue_by_city.png")
print("Saved chart: revenue_by_city.png")
```

### 6) GUI — minimal Tkinter
```python
# samples/tkinter_min.py
import tkinter as tk

root = tk.Tk()
root.title("Mini App")
tk.Label(root, text="Hello GUI").pack(padx=10, pady=10)
tk.Button(root, text="Close", command=root.destroy).pack(pady=5)
root.mainloop()
```

### 7) Web — minimal Flask
```python
# samples/flask_min.py
from flask import Flask, render_template_string
app = Flask(__name__)

@app.get("/")
def home():
    return render_template_string("<h1>Hello, Flask!</h1>")

if __name__ == "__main__":
    app.run(debug=True)
```

### 8) ML — logistic regression (scikit‑learn)
```python
# samples/logreg_sklearn.py
from sklearn.datasets import make_classification
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

X, y = make_classification(n_samples=500, n_features=2, n_redundant=0,
                           n_informative=2, random_state=42)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.25, random_state=42)
clf = LogisticRegression().fit(X_train, y_train)
pred = clf.predict(X_test)
print("Accuracy:", accuracy_score(y_test, pred))
```

> All samples are intentionally short and readable — perfect for classroom demos and quick labs.

---

## Tickets & Professional Workflow

**Bug sets used in sessions:**  
- **#701–705:** GPA system issues (averaging bug, missing file resilience, wrong data shape, weak logging, non‑PEP8 names).  
- **#801–805:** Agile sprints problems (bad CLI UX, flaky email sender, fake data skew, DB insert edge case, blocking audio call).  

**Proof & Discipline:**  
- Use branches: `v1-naive` → `v2-hardened`  
- Open PRs with checklists: style, tests (if any), docs, before/after screenshots  
- Drop “client verification” messages in `docs/client_proof/` (text or markdown)

---

## Deliverables
- ✅ Cleaned CSVs (e.g., `sales_clean.csv`) and exported charts (PNG/SVG)  
- ✅ Mini GUI app, minimal Flask app  
- ✅ `requirements.txt` and venv hygiene  
- ✅ Branches for naive vs hardened implementations  
- ✅ Clear README and sample scripts

---

## Resources
- Python Docs — https://docs.python.org/3/
- Automate the Boring Stuff — https://automatetheboringstuff.com/
- Hugging Face — https://huggingface.co/
- W3Schools Python — https://www.w3schools.com/python/
- Pandas — https://pandas.pydata.org/
- Matplotlib — https://matplotlib.org/

---

### License
Educational materials — choose a license that matches your goals (MIT, Apache‑2.0, CC‑BY‑SA).

