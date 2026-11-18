# 02 – Core Persian Heritage Patterns

**Audience**: Scholars and students in the humanities who have read the foundations document (01) and are now ready to see the object-oriented and event-based ideas applied to concrete Persian material.

This document presents a small set of recurring modelling patterns using examples from Persian art, architecture, and history. Each pattern starts from a persistent object, then shows the main events that shaped it, and indicates where controlled vocabularies and Linked Data links can later be attached.

The goal is not to produce a complete catalogue record, but to give you a clear mental template you can reuse.

---

## Pattern 1: A Manuscript (Physical Object + Content + Production Event)

**Example**: A 16th-century illustrated Shahnameh manuscript produced in Tabriz.

### What is the persistent thing?
- The physical codex itself → **E22 Human-Made Object**
- The text of the Shahnameh (or a particular version of it) → **E73 Information Object** (distinct from any physical carrier)

### Main events
- **E12 Production** – the making of this particular manuscript
- Optionally **E65 Creation** – the creation of specific illustrations or the original composition of the text (if you wish to model them separately)

### Simplified structure
```
E22 Manuscript
    ← P108 was produced by ← E12 Production
                               ← P14 carried out by ← E39 Actor (calligrapher, workshop, patron)
                               ← P7 took place at ← E53 Place
                               ← P4 has time-span ← E52 Time-Span
```

Later you can attach:
- AAT terms for materials and techniques (paper, ink, illumination)
- Iconclass notations for the subject of individual paintings
- Wikidata identifiers for the work, the patron, or the place
- An Internet Archive IIIF Manifest as a digital surrogate

This pattern keeps the physical object, its content, and its production history clearly separated — a foundation for Linked Data.

## Pattern 2: An Architectural Object That Changes Over Time

**Example**: A caravanserai or a mosque that was built in one period and enlarged or restored later.

### What is the persistent thing?
- The building as a whole → **E24 Physical Human-Made Thing** (or E22 if you prefer a simpler class)

### Main events
- **E12 Production** (or E63 Beginning of Existence) – original construction
- One or more **E11 Modification** events – later enlargements, restorations, or changes of function

### Simplified structure
```
E24 Building
    ← P108 was produced by ← E12 Production (original)
    ← P31 was modified by ← E11 Modification (later phase)
                            ← P14 carried out by ← Actor
                            ← P7 took place at ← Place
                            ← P4 has time-span ← Time-Span
```

This pattern is especially useful for Persian architecture, where buildings frequently show multiple historical layers. Each modification remains an event linked to the same persistent building.

## Pattern 3: A Historical Person and Their Activities

**Example**: A calligrapher, painter, or patron.

### What is the persistent thing?
- The person → **E21 Person**

### Main events
- Activities they carried out (E7 Activity, E12 Production, E65 Creation, etc.)
- Events that affected them (birth, death, holding an office, etc.)

### Simplified structure
```
E21 Person
    → P14 carried out by ← E7 Activity / E12 Production
                           ← P7 took place at ← Place
                           ← P4 has time-span ← Time-Span
```

Wikidata and ULAN are natural places to align person records. Once the person is stably identified, all the events they participated in can be linked.

## Pattern 4: An Iconographic Subject

**Example**: A scene from the Shahnameh or a biblical/quranic narrative depicted in a Persian manuscript or wall painting.

### What is the persistent thing?
- The visual item or the conceptual subject → often modelled via **E36 Visual Item** or simply referenced through Iconclass
- The physical carrier remains an E22

### Linking
- Use **P129 is about** or **P67 refers to** to connect the object or image to an Iconclass notation (or a Wikidata item).

This pattern shows how controlled vocabularies for subject matter fit into the object- and event-based model without replacing it.

## How These Patterns Support Linked Data

Each pattern above creates stable nodes (the objects and events) that can later receive links to external resources:

| External resource | Typical role | Example link |
|-------------------|--------------|--------------|
| Getty AAT | Type, material, technique | `P2 has type` → AAT term |
| Getty TGN | Place | `P7 took place at` → TGN place |
| Iconclass | Subject / iconography | `P129 is about` → Iconclass notation |
| Wikidata | Persons, works, places, identifiers | Direct URI or alignment |
| Getty CONA | Cultural object authority | Reference for the E22/E24 |
| Internet Archive IIIF | Digital surrogate | Link from physical object to digital object |

Because the CRM insists on persistent identity and explicit events, these external links remain meaningful and reusable. This is the practical bridge between traditional cataloguing and Linked Data.

## Practical Advice When You Start Modelling

1. Decide first what the main persistent object is.
2. List the most important events that affected it (you do not need every detail at the beginning).
3. Only then add controlled vocabulary terms and external identifiers.
4. Keep digital surrogates (IIIF, Internet Archive, etc.) clearly distinguished from the physical or conceptual object.

## Next Steps

- Examine the ready-to-use Turtle files in the `turtle/` directory (when available) that implement these patterns.
- Continue to **03 – Controlled Vocabularies**, where AAT, TGN, Iconclass, and Wikidata are treated in more detail and their role in Linked Data is expanded.
- Or move to the Internet Archive + IIIF section if your immediate interest is digital participation.

---

These four patterns cover the majority of cases you will meet when indexing Persian cultural heritage with the CIDOC CRM. They can be combined and extended as needed.
