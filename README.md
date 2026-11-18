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

The materials are organised as a guided path rather than a flat collection of examples.

| Stage | Topic | Goal |
|-------|-------|------|
| **1** | Object-oriented & event-based foundations | Understand persistent identity, classes, properties, and why events are central |
| **2** | Core Persian heritage patterns | Model manuscripts, architecture, historical actors, and iconography |
| **3** | Controlled vocabularies | Apply AAT, TGN, Iconclass, and Wikidata systematically |
| **4** | Internet Archive + IIIF | Reference existing materials and contribute new ones with ontology-based descriptions |
| **5** | From examples to practice | Reusable Turtle patterns, queries, and contribution workflows |

## Repository Structure

```
Learn-CIDOC-CRM-Persian/
├── README.md
├── learning-path/
│   ├── 01-object-oriented-and-event-based.md
│   ├── 02-core-persian-examples.md
│   └── 03-controlled-vocabularies.md
├── examples/
│   ├── manuscript-page/
│   ├── architectural-object/
│   ├── historical-event/
│   └── iconography-iconclass/
├── controlled-vocabularies/
│   ├── aat-patterns.md
│   ├── tgn-patterns.md
│   ├── iconclass-patterns.md
│   └── wikidata-alignment.md
├── internet-archive-iiif/
│   ├── ia-iiif-basics.md
│   └── contribution-workflow.md
├── turtle/
│   └── (ready-to-use .ttl examples)
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

1. Read `learning-path/01-object-oriented-and-event-based.md`.
2. Examine one complete example in `examples/` (recommended: manuscript page).
3. Study the corresponding Turtle in `turtle/`.
4. Review the controlled vocabulary patterns.
5. Try the Internet Archive contribution workflow if you have material to add.

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
