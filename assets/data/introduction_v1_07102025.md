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

