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


