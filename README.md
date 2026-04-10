sbol3-nanomedicine-design-stack
A reference implementation demonstrating SBOL3-based representation of a published four-component mRNA lipid nanoparticle formulation, with explicit encoding of composition, molar ratio, functional roles, and CMC-relevant design meaning.

github.com/MolecularPrecision/sbol3-nanomedicine-design-stack


What this is
Nanomedicine formulations are routinely described in prose. Ratios buried in methods sections. Functional roles implied rather than stated. Design decisions that carry direct regulatory consequence documented as if they were incidental.
This repository proposes a different approach.
It takes a single, well-documented LNP formulation — a four-component ionisable lipid system for mRNA delivery, based on the publicly available SM-102 composition — and represents it as a structured SBOL3 design object. Composition, molar ratios, and functional roles are encoded explicitly rather than described in prose, allowing them to be interpreted consistently across design, manufacturing, and regulatory contexts.
The claim is narrow and intentional: a clinically relevant nanoparticle formulation can be represented in SBOL3 with enough precision to support reproducibility and regulatory translation.

What it contains
sbol3-nanomedicine-design-stack/
│
├── README.md
├── LICENSE
│
├── /examples
│   └── /sm102-mrna-lnp
│       ├── README.md
│       └── design.ttl
│
├── /docs
│   ├── data-model.md
│   └── cmc-mapping.md
│
└── /assets
    └── lnp-design-stack.png

examples/sm102-mrna-lnp/ — SBOL3 Turtle representation of the formulation with annotated design parameters
docs/data-model.md — modelling argument, conventions used, and explicit limitations
docs/cmc-mapping.md — how the design object maps to CMC-relevant interpretation
assets/lnp-design-stack.png — engineering schematic of the four-component stack

The representation includes explicit conventions for modelling formulation-level parameters not natively expressed as first-class SBOL3 relationships.

What it does not contain
Process execution. Analytical assay data. Full product lifecycle traceability. Particle size distributions. Encapsulation efficiency.
Those are characterisation and manufacturing concerns. This repository isolates the design object itself. The boundary is deliberate.

Why it matters
Reproducibility failures in nanomedicine are rarely failures of intent. They are failures of description. When the design object is unstructured, every downstream step — process transfer, regulatory submission, independent replication — inherits that ambiguity.
SBOL3 was built for biological design. This repository tests how far that standard stretches into formulation space, where it holds cleanly, and where conventions must be proposed to fill the gaps.

The formulation
The example models a four-component ionisable LNP system for mRNA delivery, based on the SM-102 composition documented in public FDA filings.
ComponentFunctional roleMolar fractionSM-102Ionisable lipid — functional delivery component0.50DSPCHelper lipid — structural stabilisation0.10CholesterolMembrane modulator0.385PEG2000-DMGSurface stabilisation component0.015mRNA payloadActive cargo—
Molar ratio is treated as a first-class design parameter, not a footnote. It is encoded explicitly in the SBOL3 representation with typed annotations and a declared namespace.

Modelling approach
This repository does not claim that SBOL3 natively supports all nanomedicine concepts. It does not. Where required, explicit conventions are proposed to represent formulation-level parameters with scientific and CMC relevance.
Three conventions are introduced:

Molar ratio represented as a typed om:Measure annotation on each lipid feature
Functional role URIs declared in the repository namespace where no suitable Sequence Ontology term exists
Encapsulation represented as a directed SBOL3 Constraint using a locally declared restriction term

Full modelling argument and limitations are documented in docs/data-model.md.

Regulatory relevance
The structured design object maps directly to CMC documentation requirements under MHRA, EMA, and FDA frameworks. Composition specification, functional role justification, and design version control are baseline requirements for IND and IMPD submissions. This repository demonstrates how SBOL3 can serve as the underlying structure for those requirements.
Full mapping is documented in docs/cmc-mapping.md.

Status
v1 — single formulation, single representation, deliberately constrained.
Proposed conventions have not been submitted to the SBOL community for ratification. They are offered here as a starting point for that conversation.

Namespace
Custom terms used in this repository resolve under:
https://molecularprecision.github.io/sbol3-nanomedicine-design-stack/ns#

MolecularPrecision · github.com/MolecularPrecision
