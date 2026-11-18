# Learn CIDOC CRM with Persian Cultural Heritage

**Learning CIDOC CRM through Persian art, architecture, and history**  
Object-oriented and event-based modelling with AAT, TGN, Iconclass, Wikidata, and Internet Archive IIIF.

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![CIDOC CRM](https://img.shields.io/badge/CIDOC-CRM%207.x-blue)](https://cidoc-crm.org/)
[![IIIF](https://img.shields.io/badge/IIIF-Presentation%203.0-green)](https://iiif.io/)
[![Internet Archive](https://img.shields.io/badge/Internet%20Archive-IIIF-orange)](https://archive.org/)

---

## Vision

Most formal CIDOC CRM documentation and published examples remain strongly oriented toward Western cultural heritage. This creates a practical barrier for students, cataloguers, researchers, and cultural institutions working with Persian, Iranian, and broader Persianate material.

This repository provides a progressive learning path that:

- Introduces the **object-oriented** and **event-centric** nature of the CIDOC CRM using concrete Persian examples.
- Treats **indexing and cataloguing** of Persian cultural heritage as the core practical goal.
- Demonstrates systematic use of established controlled vocabularies (**AAT**, **TGN**, **Iconclass**) and **Wikidata** as a knowledge base.
- Shows how the **Internet Archive** (especially its IIIF service) can serve as a low-barrier participation platform for making currently inaccessible or under-documented resources available and linked.

The aim is to make CRM modelling approachable, culturally relevant, and immediately usable for Persian heritage work.

## Learning Path

The materials are organised as a progressive path. Start here:

| # | Document | Focus |
|---|----------|-------|
| **1** | [Object-Oriented and Event-Based Foundations](learning-path/01-object-oriented-and-event-based.md) | Persistent identity, why the CRM is event-centric, relation to Getty CONA/GVP and CRMdig |
| **2** | [Core Persian Heritage Patterns](learning-path/02-core-persian-examples.md) | Reusable patterns for manuscripts, architecture, persons, and iconography |
| **3** | [Controlled Vocabularies and Linked Data](learning-path/03-controlled-vocabularies.md) | AAT, TGN, Iconclass, Wikidata, CONA — and how they create Linked Data links |
| **4** | [Internet Archive and IIIF](learning-path/04-internet-archive-and-iiif.md) | Using IA + IIIF as a participation layer for digital surrogates |
| **5** | [From Examples to Practice](learning-path/05-from-examples-to-practice.md) | Minimal Turtle patterns, SPARQL starters, and contribution checklist |

Each section can be read independently, but they are designed to be followed in order. Concrete examples drawn from related repositories will be added over time.

## Repository Structure

```
CIDOC-CRM-Persian-Heritage/
├── README.md
├── learning-path/
│   ├── 01-object-oriented-and-event-based.md
│   ├── 02-core-persian-examples.md
│   ├── 03-controlled-vocabularies.md
│   ├── 04-internet-archive-and-iiif.md
│   └── 05-from-examples-to-practice.md
├── examples/
├── controlled-vocabularies/
├── internet-archive-iiif/
├── turtle/
└── queries/
```

## Core Principles

- **Object-oriented**: Every physical or conceptual thing has a persistent identity (E22 Human-Made Object, E24 Physical Human-Made Thing, E73 Information Object, etc.).
- **Event-centric**: Production, modification, use, and documentation are modelled as events (E12 Production, E11 Modification, E7 Activity, E65 Creation, …).
- **Controlled vocabularies first**: Prefer AAT, TGN, Iconclass, and Wikidata over free-text strings whenever possible.
- **Digital surrogates as first-class citizens**: IIIF Manifests and Canvases (especially from Internet Archive) are linked to the conceptual objects they represent.
- **Minimal but expandable**: Start with a small, correct core and extend only when necessary.

## Controlled Vocabularies

| Vocabulary | Primary Use in This Repository | Typical CRM Properties |
|------------|--------------------------------|------------------------|
| **AAT** | Materials, techniques, object types, architectural features | `P2 has type`, `P45 consists of` |
| **TGN** | Places (cities, regions, historical toponyms) | `P7 took place at`, `P53 has former or current location` |
| **Iconclass** | Narrative and iconographic subjects (especially painting and manuscript illumination) | `P129 is about`, `P67 refers to` |
| **Wikidata** | Persons, places, works, identifiers, and cross-links | Direct URIs + alignment properties |

## Internet Archive & IIIF

The Internet Archive is positioned as a practical participation layer:

- Existing digitised materials can be referenced via IIIF Manifests and Canvases.
- Contributors can upload currently inaccessible resources to the Internet Archive and then describe them with CRM-aligned metadata.
- A lightweight workflow connects IA identifiers to CRM entities without requiring a full institutional repository.

See the `internet-archive-iiif/` directory for details.

## Quick Start

1. Begin with [01 – Object-Oriented and Event-Based Foundations](learning-path/01-object-oriented-and-event-based.md).
2. Continue through the learning path in order (documents 02–05).
3. When ready, examine examples in the `examples/` and `turtle/` directories (added over time from related repositories).
4. Use the contribution checklist in document 05 if you wish to add material.

## Contributing

Contributions are welcome, especially:

- Additional well-documented Persian examples (with Turtle).
- Improvements to the learning path materials.
- Alignments with additional controlled vocabularies or ontologies.
- Translations or bilingual (Persian/English) explanations.
- Practical workflows for other digitisation platforms.

Please open an issue or pull request. When adding examples, prefer small, complete, and clearly commented Turtle files over large incomplete models.

## Related Resources

- [CIDOC CRM](https://cidoc-crm.org/)
- [Getty AAT](https://www.getty.edu/research/tools/vocabularies/aat/)
- [Getty TGN](https://www.getty.edu/research/tools/vocabularies/tgn/)
- [Iconclass](https://iconclass.org/)
- [Wikidata](https://www.wikidata.org/)
- [Internet Archive IIIF](https://archive.org/services/docs/api/iiif.html)
- [IIIF Presentation API](https://iiif.io/api/presentation/3.0/)

## License

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

---

**Status**: Early public draft — learning path and first examples under active development.
