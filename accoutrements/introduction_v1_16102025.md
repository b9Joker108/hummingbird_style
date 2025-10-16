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


