# sbol3-nanomedicine-design-stack

**A reference implementation demonstrating SBOL3-based representation of a published four-component mRNA lipid nanoparticle formulation, with explicit encoding of composition, molar ratio, functional roles, and CMC-relevant design meaning.**

> https://github.com/MolecularPrecision/sbol3-nanomedicine-design-stack

---

## What this is

Nanomedicine formulations are routinely described in prose. Ratios buried in methods sections. Functional roles implied rather than stated. Design decisions that carry direct regulatory consequence documented as if they were incidental.

This repository proposes a different approach.

It takes a single, well-documented LNP formulation — a four-component ionisable lipid system for mRNA delivery, based on the publicly available SM-102 composition — and represents it as a structured SBOL3 design object.

Composition, molar ratios, and functional roles are encoded explicitly rather than described in prose, allowing them to be interpreted consistently across design, manufacturing, and regulatory contexts.

**The claim is narrow and intentional:** a clinically relevant nanoparticle formulation can be represented in SBOL3 with enough precision to support reproducibility and regulatory translation.

---

## What it contains

