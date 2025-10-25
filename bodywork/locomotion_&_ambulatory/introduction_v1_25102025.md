File: ...

# Locomotion and Ambulatory Bodywork: An Introduction #

...


I need help with a filetree and taxonomy structure for an 'ambulatory' first order directory in my bodywork repository. I am not set on ambulatory as the nomenclature. Indeed, I disfavour it. It is to hold my subsection directories on: running, jogging, sprinting, hiking, rucking, altitude training, etc., and all the protocols, etc., for same.

Directory purpose and design principles
- Purpose: store reproducible, versioned protocols, data, annotations, and artifacts for locomotor training and conditioning modalities such as running, jogging, sprinting, hiking, rucking, and altitude training.  
- Principles: clear semantic naming; reproducibility and provenance; minimal redundancy; extensible taxonomy; machine- and human-friendly metadata; consistent versioning and templating for protocols and tests.  
- Constraints assumed: POSIX-style repo, Git-based VCS, mixed content (text, CSV, images, video, sensor logs), multi-user contributions, archival-quality records required.

---

Nomenclature alternatives and recommended choice
| Option | Pros | Cons |
|---|---:|---|
| ambulatory | concise; medically familiar; groups all upright locomotion | feels clinical and abstract; you dislike it |
| locomotion | technically precise; covers gait and propulsion modes | slightly technical; may attract biomechanical content beyond scope |
| gait-systems | emphasizes biomechanics and kinematics | narrower, may exclude altitude and conditioning contexts |
| field-modes | evocative of outdoors and applied training | less standard, might confuse new contributors |
| stride-work | person-centered, practice-oriented | informal, may not suit archival tone |

Recommended: locomotion for first-order directory because it balances technical precision and inclusivity while remaining neutral and archive-friendly.

---

Top-level taxonomy proposal
Use a two-tier first-order structure: modality and axis folders. Keep each first-order folder small and discoverable.

- locomotion/  
  - 01_modalities/  
    - running/  
    - jogging/  
    - sprinting/  
    - hiking/  
    - rucking/  
    - trail-running/  
    - altitude-training/  
    - treadmill/  
  - 02_protocols/  
    - conditioning/  
    - speed-work/  
    - endurance/  
    - strength-transfer/  
    - recovery/  
    - acclimatisation/  
  - 03_measurements/  
    - physiological/  
    - biomechanical/  
    - subjective-scales/  
    - environmental/  
  - 04_artifacts/  
    - templates/  
    - consent-forms/  
    - calibration-logs/  
  - 05_data/  
    - raw/  
    - processed/  
    - analysis-notebooks/  
  - 06_refs/  
    - literature/  
    - standards/  
  - 07_tools/  
    - scripts/  
    - sensor-configs/  
  - 08_archive/  
    - deprecated/  
    - historical-versions/  

Naming rules: numeric prefixes for ordering and discoverability; kebab-case for folders; avoid spaces.

---

Example filetree for a single modality
locomotion/01_modalities/running/
- README.md with scope, canonical definition, and crosswalk to protocols.  
- metadata.yaml containing title; canonical-term; tags; created-by; created-date; version; provenance.  
- protocols/  
  - running-intervals_v1.md (templated protocol file)  
  - running-long-run_v2.md  
- sessions/  
  - 2025-10-10-beauford-intervals/  
    - sensors/accelerometer.csv  
    - gps.fit  
    - hr.csv  
    - notes.md  
- analyses/  
  - step-length-estimation.ipynb  
  - pace-power-regression.csv  
- media/  
  - video-20251010-intervals.mp4  
  - photo-gait.jpg  
- calibration/  
  - imu-cal-20250901.json

Protocol template (protocols/protocol-template.md)
- Title  
- Version  
- Purpose  
- Population  
- Preconditions  
- Equipment  
- Stepwise Procedure (numbered steps)  
- Outcome Measures (primary, secondary with units)  
- Data Capture Plan (files, sampling rates)  
- Analysis Pipeline (script names + params)  
- Safety Rules  
- Provenance (author, approvals)  
- Change Log

File naming conventions
- protocols: {modality}-{shortname}v{major}.{minor}.md e.g., running-intervalsv1.0.md  
- session folders: YYYY-MM-DD-{who}-{short-event} e.g., 2025-10-10-beauford-intervals  
- data files: sensor-type-subject-session.csv e.g., imu-beauford-20251010.csv

---

Operational rules governance and metadata
- Metadata schema (metadata.yaml fields)
  - title: human title  
  - canonical-term: controlled-vocabulary tag from top-level taxonomy  
  - tags: semicolon-separated tags; single-line  
  - version: SemVer style major.minor.patch  
  - authors: semicolon-separated names with ORCID optional  
  - created-date: ISO 8601 date  
  - status: draft; validated; deprecated; archived  
  - provenance: link or commit hash of source  
- Branching and version control
  - Protocol edits on feature branches named feature/protocol/{modality}/{shortname}  
  - Merge only with at least one reviewer sign-off and a short changelog entry  
- Provenance and immutable records
  - Sessions stored as immutable folders; changes use new folder with version suffix and reference to prior session in metadata  
- Access and permissions
  - Protect 08archive and 06refs from casual edits; use CODEOWNERS or branch protections  
- Tags and crosswalks
  - Use top-level tag list stored at locomotion/controlled-vocab.tsv for consistent tagging across modalities  
- Backups and export
  - Periodic export to zipped archival packages with manifest.yaml listing files and checksums

---

Quick next steps you can copy into repo
1. Create top-level directory named locomotion and add README.md describing scope.  
2. Add controlled-vocab file and metadata schema YAML in locomotion/ templates.  
3. Seed 01_modalities with empty modality folders and a README.md in each.  
4. Add protocol-template.md and commit on a branch feature/protocol-templates for review.  
5. Create a simple CI check or pre-commit hook to validate metadata.yaml presence and SemVer on protocol files.

--- 

If you prefer a different first-order name instead of locomotion I will convert the entire tree and metadata schema to that term and produce a ready-to-commit repo patch.

Short answer
No; pushbiking (cycling) is not strictly subsumed by locomotion as we defined it (upright, weight‑bearing gait and stride mechanics), but it can be included in the same first‑order area if you broaden the scope to cover human powered transport and propulsion.

---

Two practical options
- Include cycling in the same first‑order directory by broadening the canonical term to something like locomotion-and-propulsion or locomotion-plus; treat cycling as a sibling modality (cycling/) with its own protocols and measurement axes.  
- Keep cycling separate as a parallel first‑order directory (e.g., cycling/ or propulsion/) if you want to preserve a strict gait/ambulatory taxonomy and avoid conflating weight‑bearing gait protocols with wheeled‑transport mechanics.

---

Recommendation (archive‑friendly)
Use a single top level named locomotion only if you explicitly accept non‑gait propulsion modes. Prefer this minimal change: rename top level to locomotion-propulsion and add a controlled‑vocab entry for cycling (pushbike) so it appears in taxonomy, metadata, and crosswalks.

---

Minimal repo patch (thumbnail .md style; minimal, POSIX friendly)
- Top level: locomotion-propulsion/  
- Add controlled vocab line in locomotion-propulsion/controlled-vocab.tsv:
  - cycling;pushbike;non-weight-bearing;wheeled-propulsion  
- Example folder:
  - locomotion-propulsion/01_modalities/cycling/README.md (scope, canonical-term: cycling)  
  - locomotion-propulsion/01modalities/cycling/protocols/cycling-rucking-interopv1.0.md

---

Metadata tags to add for cycling entries
- canonical-term: cycling  
- tags: wheeled-propulsion;non-weight-bearing;power-duration;cadence;bike-fit  
- measurements: FTP;cadence;power;speed;HR;GPS

--- 

Choose whether you prefer a single inclusive namespace or strict gait-only separation and I will convert the full taxonomy, metadata schema, and examples to that choice.
