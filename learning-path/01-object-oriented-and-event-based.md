# 01 – Object-Oriented and Event-Based Foundations

**Audience**: Scholars and students in the humanities (art history, architecture, history, manuscript studies, etc.) who are new to object-oriented approaches in data modelling.

This document introduces the two most important conceptual ideas in the CIDOC CRM:

1. Its **object-oriented** character (persistent identity of things).
2. Its **event-based** way of modelling cultural heritage.

It then briefly situates two related frameworks you will encounter: the Getty Cultural Objects Name Authority (CONA) and the Getty Vocabulary Program (GVP), and the CRMdig extension for digital objects and digitisation processes.

---

## 1. Why “Object-Oriented” Matters for Cultural Heritage

In everyday language we say things such as:

- “This is the same manuscript that was copied in Tabriz in 1524.”
- “This is the mosque that was enlarged under Shah Abbas.”
- “This is the same painting that was later overpainted.”

We treat cultural objects as **things that keep their identity** even when they change, move, or are described differently. The CIDOC CRM is built on exactly this idea.

### What “object-oriented” means here (without computer-science jargon)

- Every significant thing (a manuscript, a building, a painting, a person, a place) is treated as an **entity with a persistent identity**.
- We give that entity a stable identifier so that we can talk about “the same thing” across different events, documents, and descriptions.
- Properties (material, size, style, location at a certain time, etc.) are attached to the entity, but the entity itself remains the same.

In CRM terms this is expressed through classes such as:

| CRM Class | Typical Persian example | What it represents |
|-----------|-------------------------|--------------------|
| **E22 Human-Made Object** | A specific Shahnameh manuscript | A physical object made by humans |
| **E24 Physical Human-Made Thing** | A caravanserai or mosque | A physical structure that can be modified over time |
| **E73 Information Object** | The text of the Shahnameh, a particular inscription | The conceptual content (distinct from its physical carriers) |
| **E21 Person** | Ferdowsi, Shah Tahmasp, a calligrapher | A historical individual |

The crucial point for cataloguing is: **we first decide what the “thing” is**, then we describe its history.

## 2. The Event-Based Nature of the CRM

Cultural heritage objects almost never exist in isolation. They are produced, modified, moved, used, damaged, restored, documented, and digitised. The CRM models this reality by treating **events** as first-class citizens.

### Core idea

Instead of writing a long static description (“this manuscript was made in the 16th century in Tabriz by calligrapher X and later owned by Y”), we record a sequence of events that affected the object.

Typical event classes:

| CRM Class | Meaning | Persian example |
|-----------|---------|-----------------|
| **E12 Production** | The making of an object | Production of a Shahnameh manuscript in Tabriz, 1520s |
| **E11 Modification** | A change to an existing object | Later addition of illumination, rebinding, or architectural enlargement of a mosque |
| **E7 Activity** | A broader intentional action | Commissioning of a manuscript by a royal patron |
| **E65 Creation** | Creation of conceptual content | Composition of a particular illustration or poem |
| **E63 Beginning of Existence** | The moment something starts to exist | Founding of a caravanserai |

A simplified pattern that appears again and again is:

```
Object  ←— produced by / modified by —  Event  — carried out by —→ Actor
                                              |
                                              └— took place at —→ Place
                                              └— has time-span —→ Time
```

This event-based approach has several practical advantages for Persian heritage:

- It can express change over time (very important for architecture and for manuscripts that were altered).
- It separates the physical object from its content and from its digital surrogate.
- It makes it easier to link controlled vocabularies and external authorities later.

## 3. Getty CONA and the Getty Vocabulary Program (GVP)

The Getty Research Institute maintains several controlled vocabularies that are widely used in cultural heritage. Two are especially relevant here:

- **Getty Vocabularies** (AAT, TGN, ULAN, etc.) – the broader program, often referred to as GVP.
- **CONA** (Cultural Objects Name Authority) – a Getty resource specifically designed for works of art and architecture.

### How they relate to the CRM

- CONA provides **authoritative records for cultural objects** (paintings, sculptures, buildings, manuscripts, etc.). Each CONA record can be seen as a candidate for an E22 or E24 entity in the CRM.
- The other Getty vocabularies supply the controlled terms used inside those records (materials from AAT, places from TGN, artists from ULAN).
- In practice, many projects treat a CONA identifier as a stable reference for the object, then use CRM properties to express the events that affected it and to link to AAT/TGN/ULAN terms.

You do not have to use CONA, but understanding its purpose helps you see why the CRM insists on stable object identity: both systems are trying to solve the same problem of “which thing are we talking about?”

## 4. CRMdig – Digital Objects and Digitisation Processes

Most of the material we work with today is digital (scans, photographs, IIIF manifests, 3D models). The CIDOC CRM itself focuses on the cultural objects; **CRMdig** is the official extension that models the digital side.

CRMdig is useful when you need to distinguish:

| Concept | CRM / CRMdig class | Example |
|---------|--------------------|---------|
| The physical manuscript | E22 Human-Made Object | The actual 16th-century codex |
| A digital image or scan of a page | D1 Digital Object (CRMdig) | A high-resolution TIFF or JPEG of folio 42 |
| The act of digitising | D7 Digital Machine Event / related activities | Scanning performed by a particular institution on a certain date |
| An IIIF Manifest or Canvas | Can be linked as a digital surrogate | Internet Archive IIIF resource |

### Why this matters for the present repository

- When we point to an Internet Archive IIIF Canvas or Manifest, we are usually pointing to a **digital object**, not to the physical cultural object itself.
- CRMdig (or a lightweight equivalent pattern) lets us keep these two levels separate while still linking them.
- This separation is essential if we want to encourage people to upload material to the Internet Archive and then describe it properly.

You do not need to master all of CRMdig at the beginning. It is enough to know that the CRM family provides a clear way to talk about both the heritage object **and** its digital representations.

## 5. Putting the Ideas Together – A Minimal Mental Model

When you approach a Persian cultural heritage item, try to answer these questions in order:

1. **What is the persistent thing?** (the manuscript, the building, the painting, the person…)
2. **Which events shaped it?** (production, modification, ownership, documentation…)
3. **Who and where were involved in those events?**
4. **Which controlled terms** (AAT, TGN, Iconclass, Wikidata, CONA…) best describe its type, material, place, or subject?
5. **Is there a digital surrogate** (especially an Internet Archive IIIF resource) that should be linked to it?

This sequence—object identity first, then events, then vocabularies and digital surrogates—is the practical core of using the CIDOC CRM for Persian cultural heritage.

---

### Next steps in this learning path

- Continue to **02 – Core Persian Examples**, where these ideas are applied to concrete cases (manuscript page, architectural object, etc.).
- Or jump to the `examples/` and `turtle/` directories if you prefer to see complete worked examples immediately.

### Further reading (optional)

- CIDOC CRM official site: https://cidoc-crm.org/
- Getty CONA: https://www.getty.edu/research/tools/vocabularies/cona/
- CRMdig specification (available from the CIDOC CRM website)

