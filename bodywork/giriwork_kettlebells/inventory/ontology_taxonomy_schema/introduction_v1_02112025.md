File: xxx

I need assistance in making a global GitHub YAML frontmatter GFM *.md template for my kettlebell exercise inventory and register. The template needsmust accomodate all possible kettlebell movements. It must be logical, that is, formally logical in its construction. It should catalogue exercises, subsuming their: analysis of force types according to physics and how the forces move through the biomechanics of the movement in relation to the dynamic translation/transition of the movement and the kettlebell; physiology, detailed; anatomy, detailed; exercise sciences, detailed; rehabilitation, detailed; parse it in relation to all factors, like an Engineering spec sheet. Tech stack: YAML Taxonomy, JSON Ontology as a specification formalising the ontology, so there is no ambiguity for either humans nor machines and it is to produce a platinum standard knowledge graph and be scriptable. Before you execute, fully understand all the edge cases and corner cases for universally mapping kettlebell exercises in the most optimal fashion possible.

That’s an ambitious and conceptually beautiful goal: a formally logical, globally extensible YAML–JSON hybrid schema for kettlebell movement cataloguing with precision similar to an engineering specification. The objective would be to support multidimensional knowledge representation: *exercise taxonomy, force dynamics, biomechanics, physiology, anatomy, rehabilitation context, and specification-level metadata*; whilst maintaining both human-readability (GitHub Flavored Markdown frontmatter) and machine-actionability (ontological mapping).  

Below is a **proposed universal master template** in YAML frontmatter for GFM (`*.md`) files. It is structured for ontological consistency and designed to sit at the apex of a knowledge graph that could serialize to JSON-LD without semantic loss.

***

```yaml
---
schema: "KettlebellExerciseOntology.v1.0"
metadata:
  id: null
  canonical_name: null
  variant_names: []
  author: null
  version: 1.0
  date_created: null
  date_modified: null
  license: "CC-BY-SA-4.0"
  data_origin: 
    source: [ "Coaching standard reference", "Peer-reviewed study", "Empirical lab analysis" ]
    sensor_sources: [ "IMU", "EMG", "Force plate", "Motion capture" ]
  language: "en"
  region_focus: "global"
  classification_level: [ "general", "rehabilitative", "competitive", "applied research" ]
  interoperability:
    compatible_serializations: [ "JSON", "JSON-LD", "Turtle" ]
    ontology_ref: "https://example.org/kettlebell/ontology"

taxonomy:
  domain: "Exercise Science"
  category: "Kettlebell Training"
  sub_category: [ "Swing family", "Cleans", "Snatches", "Presses", "Turkish Get-up", "Squats", "Complexes" ]
  biomechanical_class: [ "Ballistic", "Grind", "Transitional", "Sequential" ]
  force_type: 
    primary: [ "Rotational", "Translational", "Gravitational" ]
    secondary: [ "Centripetal", "Centrifugal", "Angular momentum-driven", "Inertial overload" ]
  kinetic_chain: [ "Closed", "Open", "Hybrid" ]
  plane_of_motion: [ "Sagittal", "Frontal", "Transverse", "Multiplanar" ]
  equipment_held: "Single kettlebell"  # or double, offset, alternating
  grip_variants: [ "Overhand", "Underhand", "Hook", "Rack", "Bottoms-up", "Horn", "Crush" ]
  functional_goal: [ "Strength", "Power", "Endurance", "Mobility", "Coordination", "Posture" ]
  applied_context: [ "Sport performance", "General fitness", "Rehabilitation", "Tactical training" ]

mechanical_analysis:
  system_body_mass: 
    total_mass: null
    bell_mass: null
    relative_load_percent_bodyweight: null
  force_vectors:
    directionality: [ "Vertical", "Horizontal", "Rotational" ]
    torque_joints: [ "Hip", "Spine", "Shoulder", "Elbow" ]
    moment_analysis:
      peak_force: null
      average_force: null
      impulse_time_ms: null
      power_curve_characteristics: null
  energy_transfer:
    phases:
      - name: "Acceleration"
        type: "Positive concentric"
        dominant_muscle_groups: [ "Hip extensors", "Shoulder flexors" ]
      - name: "Deceleration"
        type: "Eccentric control"
        dominant_muscle_groups: [ "Hamstrings", "Trapezius" ]
    kinetic_energy_joules: null
    potential_energy_change: null
    angular_momentum: null
  external_mechanics:
    center_of_mass_path: null
    line_of_action_relative_to_body: null
    torque_to_moment_ratio: null
    effective_leverage: null

anatomical_domains:
  primary_muscles: []
  secondary_muscles: []
  stabilizers: []
  antagonists: []
  joint_actions: 
    - joint: "Hip"
      motion: [ "Extension", "Flexion" ]
    - joint: "Shoulder"
      motion: [ "Flexion", "Abduction", "External rotation" ]
  fascia_chains: [ "Posterior chain", "Deep front line", "Lateral line" ]
  typical_injury_points: [ "Shoulder impingement", "Lumbar overextension", "Wrist strain" ]

physiological_parameters:
  energy_systems: [ "ATP-PC", "Anaerobic glycolysis", "Oxidative" ]
  heart_rate_zone: null
  lactate_threshold_zone: null
  metabolic_equivalent (MET): null
  force_velocity_profile: null
  hormonal_response_profile:
    acute: [ "Cortisol", "Testosterone", "GH" ]
    chronic_adaptation: [ "Improved insulin sensitivity", "Enhanced mitochondrial density" ]
  recovery_time_hr: null
  nervous_system_load:
    type: [ "CNS-dominant", "PNS-dominant" ]
    rating_scale: null

rehabilitation_and_therapeutic_use:
  corrective_focus: [ "Scapular stability", "Hip hinge retraining", "Thoracic mobility" ]
  contraindications: [ "Acute shoulder bursitis", "Lumbar disc pathology" ]
  modifications: []
  safe_progressions: []
  clinical_evidence_ref: []

exercise_specification:
  movement_sequence:
    - phase: "Setup"
      cues: [ "Neutral spine", "Kettlebell one foot ahead" ]
    - phase: "Execution"
      cues: [ "Powerful hip drive", "Bell floats passively" ]
    - phase: "Recovery"
      cues: [ "Absorption through hips", "Ground connection" ]
  tempo_notation: "X0X0"
  range_of_motion: "Full or partial hip extension"
  symmetry_profile: [ "Unilateral", "Alternating", "Bilateral" ]
  variability_tolerance: "Medium"
  fatigue_resistance_factor: null

performance_metrics:
  1RM_equivalent_kg: null
  velocity_m_s: null
  work_output_joules: null
  repetitions: null
  session_density (work/total time): null
  technical_stability_index: null
  fatigue_accumulation_curve: null

relations:
  prerequisite_exercises: []
  progressions_to: []
  regressions_to: []
  equivalent_patterns: []
  related_studies: []
  video_reference: []
  linked_ontology_nodes: []

notes: |
  Use this template to encode each kettlebell movement instance.
  Ensure that biomechanical and physiological parameters are empirically validated before populating dataset fields.
---
```

***

Would you like this schema version expressed also as a JSON-LD ontology scaffold (defining @context, @type, and interrelations for automated knowledge graph ingestion), or should we first refine this YAML layer into a conforming schema specification (YAML Schema draft v2021-12) for validation?

