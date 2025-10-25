---
title: "Bodywork-Groundwork: An Introduction"
canonical-term: bodywork-groundwork
short-description: "Archival specification for barefoot-only bodywork and floorwork practiced on naturally occurring terrestrial substrates, emphasizing sensory integration, transition continuity, and substrate-driven progression."
purview-summary: >
  Documents practice, pedagogy, protocols, and provenance for barefoot bodywork performed
  exclusively on natural, non-synthetic ground (e.g., grass, soil, sand, rock, pebbles, humus).
  Excludes aquatic, aerial, synthetic-floor, and shod modalities. Focus: in-situ continuous
  movement, featherfoot mechanics, balance, levers, vinyasa-informed sequencing, and mobility
  adapted to natural substrate complexity.
status: draft
created-date: 2025-10-25
license: "CC-BY-4.0"

taxonomy:
  domain: somatic-practices
  branch: bodywork-groundwork
  hierarchy:
    - id: BWG.01
      label: Surface-Type
      terms:
        - grass
        - soil
        - sand
        - rock
        - pebble
        - humus
    - id: BWG.02
      label: Modality-Family
      terms:
        - balance-proprioception
        - floorwork-groundwork
        - calisthenic-lever-work
        - vinyasa-adapted-sequencing
        - mobility-active-stretching
        - ecological-locomotion
        - featherfoot-technical-gait
    - id: BWG.03
      label: Loading-Interface
      terms:
        - barefoot-primary
        - no-external-implements
    - id: BWG.04
      label: Progression-Axis
      terms:
        - substrate-complexity
        - transition-density
        - hold-duration
        - movement-amplitude
    - id: BWG.05
      label: Risk-Control
      terms:
        - substrate-inspection
        - clinical-screening
        - deload-to-simpler-surface
        - stop-on-acute-injury

controlled-vocabulary:
  canonical-tags:
    - barefoot
    - natural-surface
    - featherfoot
    - flow
    - lever
    - vinyasa
    - proprioception
    - mobility
    - substrate-complexity
    - no-implements
  ontological-relations:
    - broader: somatic-practices
    - narrower:
      - balance-proprioception
      - calisthenic-lever-work
    - related:
      - forest-bathing (contextual, not practice-equivalent)
      - earthing/grounding (overlap in substrate contact)

operational-scope:
  allowed-surfaces: grass; soil; sand; rock; pebble; humus
  excluded-surfaces: synthetic-mats;artificial-turf;paved-surfaces;indoor-mats
  footwear-policy:
    canonical: barefoot-only
    exceptions: "documented clinical necessity (bandage/tape) with provenance and justification"
  permitted-equipment: none
  excluded-equipment: shoes;boards;mats;synthetic-protective-gear

program-qualifiers:
  primary-loading: bodyweight
  continuity-model: continuous-flow-with-micro-recoveries
  session-length-typical-minutes: 20-120
  exemplar-session-intent: skill-integration;balance-chaining;lever-transitions;mobility-integration

progression-and-progression-gates:
  progression-levers:
    - substrate-complexity
    - transition-count
    - hold-duration_seconds
    - transition-amplitude
  gate-rule: "Advance when practitioner achieves three consecutive clean instances of the target transition/hold under the same substrate conditions across two sessions."
  regression-rule: "Deload by lowering substrate complexity first, then by reducing transition density or hold duration."

measurement-primitives:
  quantitative:
    - session_duration_minutes
    - hold_duration_seconds
    - transition_count_per_minute
    - adherence_percent
  qualitative:
    - transition_fidelity_notes
    - sensory_integration_report
    - wound_or_skin-status
    - perceived_exertion_RPE

safety-and-screening:
  baseline-assessment:
    - lower-limb-integrity
    - cutaneous-sensitivity
    - balance-proficiency
    - tetanus-vaccination_note
  pre-session-protocol:
    - substrate-inspection (document hazards)
    - geotag-substrate-photograph
    - participant-informed-consent-for-location-data
  stop-criteria:
    - sudden-localized-sharp-pain
    - uncontrolled-bleeding
    - syncope-or-near-syncope
    - signs-of-infection-post-session

data-capture-and-provenance:
  required-artifacts:
    - session-video (full-length)
    - substrate-photograph (close-up + context)
    - session-metadata.yaml (this header + session-specific fields)
    - optional: substrate-sample-log (if archaeological/forensic research)
  provenance-fields:
    - practitioner-id (pseudonymizable)
    - location-gps (consent-dependent)
    - timestamp
    - source-type: (practice-note | workshop | archival-video | interview)
  privacy-rule: "Redact personal identifiers unless explicit consent is recorded; store geolocation only with consent."

archival-metadata-schema:
  file-structure:
    - index.md (this explanatory YAML frontmatter)
    - metadata.yaml (per-session record)
    - media/
      - video.mp4
      - substrate-photo.jpg
  metadata-fields-for-session-record:
    - title
    - canonical-term
    - date
    - duration_minutes
    - surface_type (use BWG.01 terms)
    - sequence_summary
    - transition_count
    - hold_durations_list
    - RPE
    - provenance_source
    - artifacts (video;photos;notes)

curation-notes:
  - "Treat substrate complexity as primary independent variable for progression and risk management."
  - "Separate marketing materials from technical artifacts; tag marketing as provenance=marketing when present."
  - "When quantifying, prioritise reproducible measures that do not require lab instrumentation (time, counts, holds)."
  - "Maintain a change-log for any protocol edits; include rationale and version date."

contacts-and-contributors:
  maintainers:
    - name: "Beauford"
      role: author-curator
      affiliation: personal-archive
  future-contributions: "Accept field-notes, vetted workshop curricula, and geolocated substrate records; require provenance and consent."

tags: [barefoot, natural-surface, floorwork, featherfoot, flow, lever, vinyasa, proprioception, mobility, substrate-complexity]
---


File: 

# Bodywork-Groundwork: An Introdction #

PURVIEW:

On the face of it, this directory subfile may seem derivative and redundant. It is not so: From my knowledges, experiences and their mutual informing and iteration, it is of inestimable value and import. This is concerned with, especially, all forms of bodywork (subsuming floorwork), without footware of any kind, tooled or otherwise, done on naturally ocurring, non-human-made, non-synthetic, non-artificial or non-human-constructed or made surfacing or flooring of any kind. It subsumes much of the discourse and modalities of: forest bathing and grounding, for example. Particularly, their science. So, training on grass, on earth or dirt, on humus, rock, pebbles, on sand, etcetera. Water surface, swimming, water-immersion and aerials, flighted or other somesuch and related training, exercise or sporting endeavour of any kind, are not within this purview. This is not something I am doing currently, but it has been profoundly important to my manifold bodywork processes and modalities historically and will be so again. In addition to what has been stated, only true barefoot training with featherfoot-fall at-pace is entertained.


Books (foundational and practitioner-facing)
- Natural Born Heroes — narrative exploration of movement, resilience, and natural‑surface practice; useful for cultural context and applied examples.  
- Becoming a Supple Leopard (Kelly Starrett) — practical mobility, joint prep, and movement hygiene with applicable protocols for groundwork.  
- The Practice of Natural Movement (Erwan Le Corre / MovNat materials) — practical curricula and philosophy for training natural locomotion and in‑situ skill chaining.  
- Foundations of Hand Balancing and Bodyweight Strength (gymnastics‑derived manuals, e.g., Christopher Sommer’s writings) — technical progressions for levers, holds, and continuous practice blocks.  
- The Art and Science of Flexibility and Mobility (compilation texts) — focused frameworks and exercises for active stretching and joint control suited to variable substrates.  
- Body by You / You Are Your Own Gym (Mark Lauren) — systematic, reproducible bodyweight progressions and calendars adaptable to natural surfaces.  
- The Movement: Functional Movement Systems and Practical Application (collection) — applied screening and corrective protocols relevant to barefoot groundwork.

Academic reviews and research papers (biomechanics, sensory, ecology)
- Overview reviews on proprioception and balance control — survey literature explaining sensory contributions to balance on uneven substrates.  
- Papers on barefoot locomotion biomechanics — comparative studies of shod vs barefoot gait, foot strike, and substrate interaction useful for featherfoot mechanics.  
- Research on surface compliance and neuromuscular control — studies that quantify muscle activation changes and stability strategies across sand, grass, rock, and compliant surfaces.  
- Ecological dynamics and skill acquisition reviews — theoretical framing for environment‑driven progression and task‑goal coupling in natural practice.  
- Somatosensory plasticity and tactile feedback literature — studies on mechanoreceptors, cutaneous input, and sensorimotor adaptation to varied substrates.  
- Work‑capacity and injury risk analyses for plyometrics and continuous flow training — papers examining injury incidence and mechanical loading under high‑density bodyweight practice.

Practitioner manuals, curricula, and certifications
- MovNat curriculum guides and certification notes — practical progressions for vaults, balance, rolling, and in‑situ chaining.  
- Animal Flow instructor materials — module breakdowns (Wrist Prep; Beast; Traveling forms) and flow sequencing rules.  
- GymnasticBodies program materials — isometric and dynamic progression templates for lever and hand‑balance skills.  
- GMB Elements / Movement manuals — microprogression templates for strength, mobility, and flow integration.  
- Kinstretch / CARs resources — protocols for continuous joint control and active mobility that slot into flow sessions.  
- Z‑Health practitioner primers — sensorimotor drills and gaze/balance sequencing useful for integrating neurocentric balance work.

Field guides, methodological primers, and short papers
- Field manual for substrate assessment — pragmatic checklist for substrate inspection, hazard mapping, and contextual safety for natural‑surface sessions.  
- Minimalist foot health and conditioning primers — progressive toe/spread/arch conditioning programs for safe barefoot adaptation.  
- Protocols for recording and archiving field sessions — metadata templates, video capture best practices, and substrate documentation methods for reproducible archives.  
- Practical guide to featherfoot technique — drills for soft landing, step cadence, and micro‑coordination on variable terrain.

Interdisciplinary and contextual readings
- Papers on forest bathing / grounding physiology — measured autonomic and inflammatory outcomes from prolonged natural‑surface contact (contextual, not training protocol).  
- Ethnographies of natural locomotion and indigenous barefoot practices — cultural context for long‑duration barefoot and substrate‑specific skills.  
- Architectural and landscape studies on ground affordances — how substrate design and natural features afford or constrain movement patterns.  

Online resources, repositories, and media (practical, regularly updated)
- Official MovNat resources and certification info (curriculum outlines and course notes).  
- Animal Flow instructor pages for module breakdown and movement libraries.  
- GMB and GymnasticBodies program pages for progression templates and movement tests.  
- Free practitioner blogs and short‑form video libraries demonstrating featherfoot drills, substrate inspection, and flow examples.  

How to use this reading set (recommended sequence)
1. Start with an ecological dynamics review and barefoot biomechanics papers to set theoretical grounding.  
2. Read practitioner manuals (MovNat, GMB, GymnasticBodies, Animal Flow) to obtain reproducible progressions and drills.  
3. Integrate Kinstretch/CARs and mobility manuals for joint‑specific continuous elements.  
4. Apply field guides and substrate assessment before practical sessions; use foot‑conditioning primers for safe adaptation.  
5. Archive sessions with the protocol and metadata schema you’ve defined to create reproducible records.

If you want, I will:
- Produce a prioritized, annotated bibliography in your repository YAML/MD format with full bibliographic entries (authors, year, publisher/journal) for 30 high‑value items, or  
- Generate a short study syllabus (6–8 week) using only open resources and practitioner manuals that maps readings to practice sessions.

