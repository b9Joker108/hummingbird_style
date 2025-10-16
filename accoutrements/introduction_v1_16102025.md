# Introduction #

Direct Answer
Yes. A waterbladder can sit under #accoutrements/tactical—specifically as an accessory in the hydration subsystem.  

---

Proposed Hierarchy

1. load-carry  
   - load-carry/backpacks  
   - load-carry/frames  
   - load-carry/hydration  
2. accoutrements  
   - accoutrements/tactical  
     - accoutrements/tactical/hydration  
     - accoutrements/tactical/pouches  
     - accoutrements/tactical/straps  

By placing the waterbladder in accoutrements/tactical/hydration, you keep it with other mission-support items while preserving a clear path back to load-carry gear.

---

Why This Makes Sense

- Hydration systems are secondary to primary weapons or body armor but are mission-critical “tactical” accessories.  
- Treating it as an accoutrement avoids conflating it with rigid frame or pack classification.  
- A dedicated /hydration subcategory ensures any future bladder, hose kit, or quick-disconnect adapter falls under the same node.

---

Next Steps

- Add metadata fields:  
  - Capacity (L)  
  - Material (e.g., TPU, PE)  
  - Manufacturer and model  
  - Cleaning protocol version  
- Version-control your category tree in Git to track when you introduce new subcategories (e.g., /hydration).  
- Archive any field-replaceable parts (valve, hose) under a sibling node like accoutrements/tactical/hydration/spares.

Let me know if you’d like a reproducible script to validate your YAML or JSON category file against these new nodes!


Direct Answer
#load-carry/frames is the node for structural support systems—rigid or semi-rigid skeletons that distribute pack loads across your body.  

---

1. What Belongs Under /load-carry/frames
- external backpack frames (aluminium ladder, composite sheet)  
- internal frame sheets and stays  
- exoskeleton belts and hip-belt frames  
- load-lifter and compression-strap assemblies  

---

2. Proposed Subcategory Structure

```yaml
load-carry:
  frames:
    external:
      ladder-frames: []
      sheet-frames: []
    internal:
      stays: []
      frame-sheets: []
    exoskeleton:
      belts: []
      load-lifter-straps: []
```

---

3. Example Items

- external/ladder-frames  
  - Lowe Alpine CADOMOTIC aluminium ladder  
  - Mystery Ranch composite sheet insert  

- internal/frame-sheets  
  - Osprey ThermoForm PE sheet  
  - DIY polypropylene stay set  

- exoskeleton/belts  
  - Arc’teryx Bora hip-belt  
  - Kifaru load-bearing belt module  

---

4. Key Metadata for Each Frame Entry
- material; weight (g); max-load (kg)  
- dimensions (L×W×T)  
- attachment-interface (mol­le; daisy-chain; custom)  
- manufacture-date; vendor; part-number  
- cleaning/inspection protocol version  

---

5. Validating Your Category Tree
Assuming you store your tree in categories.yaml, here’s a tiny yq check for existence of load-carry.frames:  

```bash
yq e '.["load-carry"] | has("frames")' categories.yaml
```  

A result of true confirms the node; false means it’s missing or mis-nested.  

---

Next, you might script a diff between your live inventory and this taxonomy to catch un-categorized items. Let me know if you’d like a reproducible Zsh snippet for that!


Direct Answer
Introduce a new top‐level branch for sleep and shelter systems—e.g., camp/sleep-shelter—and nest your items there.

---

Proposed Taxonomy Structure

```yaml
camp:
  sleep-shelter:
    bivouac-bags:
      swag: []
      bothy-bag: []
    bedding:
      sleeping-bags: []
      sleeping-mats:
        roll-mat: []
        inflatable-mat: []
    shelters:
      tarps: []
```

---

Node Breakdown

- camp/sleep-shelter  
  • bivouac-bags – heavy-duty enclosed sacks for ground bivouac  
    – swag  
    – bothy-bag  
  • bedding – insulating layers under or around the body  
    – sleeping-bags  
    – sleeping-mats  
      * roll-mat (closed-cell foam)  
      * inflatable-mat (air-filled)  
  • shelters – lightweight ground covers or shades  
    – tarps  

---

Metadata to Capture

- capacity or rating (e.g., temperature for bags; R-value for mats)  
- dimensions (packed/unpacked)  
- material and denier  
- seam-sealing / waterproofing protocol  
- weight (g) and pack-volume (L)  
- manufacturer, model, batch/lot  

---

Next Steps

- Validate your YAML with yq or a JSON schema  
- Version-control changes so you can track when you add new shelter or bedding types  
- Script an inventory check to flag any uncategorized gear  

Let me know if you need a snippet to diff your live gear list against this taxonomy or to auto-generate placeholder entries for missing nodes.


Recommended Readings

Taxonomy and Classification Theory

- Bowker, G.C. and Star, S.L. (1999). Sorting Things Out: Classification Systems and Their Consequences.  
- Ranganathan, S.R. (1933). Colon Classification.  
- Hjørland, B. (2011). Domain Analysis in Information Science: Eleven Approaches—Traditional to Contemporary.

Archival Standards and Metadata

- Society of American Archivists. (2013). Describing Archives: A Content Standard (DACS).  
- International Council on Archives. (2000). General International Standard Archival Description (ISAD(G)).  
- Gilliland-Smith, M. (2017). Introduction to Metadata: Pathways to Digital Information.

Material Culture and Anthropology of Technology

- Miller, D. (1987). Material Culture and Mass Consumption.  
- Hicks, D. (2010). The Material-Cultural Turn: Event and Effect.  
- David, P.A. (1985). Clio and the Economics of QWERTY—History Lessons for Economic Development.

Gear-Specific Classification Systems

- Purnell, K., et al. (2014). The Ultimate Hiker’s Gear Guide.  
- The Mountaineers. (2017). Mountaineering: The Freedom of the Hills.  
- Brooks, J. and Schumacher, B. (2009). Ultra-Light Backpackin’ Tips.

Reproducible Documentation & Protocol Design

- Wilson, G. (2014). Best Practices for Scientific Computing.  
- Goodman, A., et al. (2016). Ten Simple Rules for Documenting Scientific Software.  
- Jones, S. and Maull, K. (2020). Reproducible Research in Practice: Tools, Techniques, and Workflows.

---

Looking to deepen further? Explore journals like Material Culture or Archivaria for case studies, or dive into information-architecture texts (e.g., Rosenfeld & Morville’s Information Architecture for the World Wide Web) to see how digital taxonomies mirror physical-gear classification.


