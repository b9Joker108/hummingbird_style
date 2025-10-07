# Introduction #

...


Yes, I remember the curricular matrix we built earlier — the lattice of functions (Assessment, Intervention, Integration, Safety) crossed with domains (MSK, Neurological, Cardiopulmonary, Pathology, Exercise, Biomechanics), with each of the six dominant physiotherapy textbooks mapped into their strongest cells.  

Since you want a source of truth in JSON, here’s a structured representation you can drop into /assets/data/physiotherapytextbookmatrixv107102025.json. This format is designed to be both human‑readable and machine‑parsable, so you can regenerate SVGs, PDFs, or Markdown tables from it later without losing fidelity.

```json
{
  "title": "Curricular Matrix of Dominant Physiotherapy Textbooks",
  "version": "v1",
  "date": "2025-10-07",
  "axes": {
    "functions": ["Assessment", "Intervention", "Integration", "Safety"],
    "domains": ["MSK", "Neurological", "Cardiopulmonary", "Pathology", "Exercise", "Biomechanics"]
  },
  "textbooks": [
    {
      "id": "magee",
      "title": "Orthopedic Physical Assessment",
      "authors": ["Magee, D.J."],
      "publisher": "Elsevier",
      "coverage": {
        "Assessment": ["MSK"],
        "Safety": ["MSK"]
      }
    },
    {
      "id": "kisner_colby",
      "title": "Therapeutic Exercise: Foundations and Techniques",
      "authors": ["Kisner, C.", "Colby, L.A."],
      "publisher": "FA Davis",
      "coverage": {
        "Intervention": ["MSK", "Neurological", "Cardiopulmonary", "Exercise"]
      }
    },
    {
      "id": "neumann",
      "title": "Kinesiology of the Musculoskeletal System",
      "authors": ["Neumann, D.A."],
      "publisher": "Elsevier",
      "coverage": {
        "Assessment": ["Biomechanics"],
        "Integration": ["MSK", "Exercise"]
      }
    },
    {
      "id": "goodman_fuller",
      "title": "Pathology: Implications for the Physical Therapist",
      "authors": ["Goodman, C.C.", "Fuller, K.S."],
      "publisher": "Elsevier",
      "coverage": {
        "Intervention": ["Pathology", "MSK"],
        "Safety": ["Pathology"]
      }
    },
    {
      "id": "osullivan",
      "title": "Physical Rehabilitation",
      "authors": ["O’Sullivan, S.B.", "Schmitz, T.J.", "Fulk, G.D."],
      "publisher": "FA Davis",
      "coverage": {
        "Integration": ["MSK", "Neurological", "Cardiopulmonary"]
      }
    },
    {
      "id": "kendall",
      "title": "Muscles: Testing and Function with Posture and Pain",
      "authors": ["Kendall, F.P.", "McCreary, E.K.", "Provance, P.G."],
      "publisher": "Lippincott Williams & Wilkins",
      "coverage": {
        "Assessment": ["MSK", "Biomechanics"]
      }
    }
  ]
}
```

---

🔑 Why this JSON works
- Axes defined explicitly → you can regenerate any grid or matrix.  
- Coverage stored as function → domain arrays → easy to render into a table, SVG, or heatmap.  
- Metadata (title, version, date) → ensures archival reproducibility.  
- IDs → stable handles for styling or color‑coding in diagrams.  

---

Would you like me to also draft a Markdown + JSON dual‑protocol scaffold (so every time you add a new matrix, you automatically have both the human‑readable .md and the machine‑readable .json in sync)? That would give you a reproducible workflow for your /assets hierarchy.

Excellent — let’s go back to first principles and treat JSON as what it really is: a serialization format for structured data. If you want to use a \*.json file as the source of truth for your curricular matrices (or any other assets), here’s what you need to know.

---

📖 JSON from First Principles

- What it is:  
  - JavaScript Object Notation (JSON) is a plain‑text format for representing structured data.  
  - It encodes objects (key–value pairs), arrays (ordered lists), and scalars (strings, numbers, booleans, null).  
  - It is language‑agnostic: every modern language can parse and generate JSON.

- Why it works as a source of truth:  
  - Human‑readable: you can open it in any editor.  
  - Machine‑parsable: every tool (Python, shell, GitHub Actions) can consume it.  
  - Diff‑friendly: changes are line‑based, so Git can track revisions.  
  - Future‑proof: you can regenerate tables, diagrams, or PDFs from the same JSON without loss.

---

🖥️ POSIX Shell Basics

You can query JSON in shell pipelines using jq, which is POSIX‑friendly.

```sh

Print all textbook titles from the JSON
jq '.textbooks[].title' assets/data/physiotherapytextbookmatrixv107102025.json

List all domains covered by Goodman & Fuller
jq '.textbooks[] | select(.id=="goodmanfuller") | .coverage' assets/data/physiotherapytextbookmatrixv1_07102025.json
```

This makes JSON a living database you can interrogate directly from the command line.

---

🐍 Canonical Python Usage

Python has a built‑in json module:

```python
import json
from pathlib import Path

Load JSON
data = json.loads(Path("assets/data/physiotherapytextbookmatrixv107102025.json").read_text())

Example: list all textbooks and their domains
for tb in data["textbooks"]:
    print(tb["title"], "→", tb["coverage"])
```

You can then render this into Markdown, SVG, or LaTeX automatically.

---

🔄 GitHub Process Flows

- Store JSON in /assets/data/ with versioned filenames.  
- Use GitHub Actions to regenerate derived artifacts (Markdown tables, SVG diagrams, PDFs) whenever the JSON changes.  
  - Example workflow step:

```yaml
on:
  push:
    paths:
      - 'assets/data/*.json'

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Generate Markdown tables
        run: python scripts/render_tables.py
```

- Keep JSON as the single source of truth; everything else (tables in .md, diagrams in .svg, PDFs in /tables) is generated.

---

🧭 Archival Protocol

1. JSON = canonical (source of truth).  
2. Markdown = accessible (screen readers, GitHub rendering).  
3. SVG/PDF = visual/archival (for fidelity and citation).  
4. README.md in /assets/data/ documents schema, versioning, and generation pipeline.  

---

👉 In short: JSON is your atomic, reproducible record. Shell (jq) lets you query it, Python lets you transform it, and GitHub Actions lets you automate regeneration.  

Would you like me to draft a minimal JSON schema definition (with required keys, types, and constraints) so you can validate any future matrix files and guarantee they remain consistent across your repo?
