# 03 – Controlled Vocabularies and Their Role in Linked Data

**Audience**: Scholars and students in the humanities who have read the foundations (01) and core patterns (02) and now want to understand how controlled vocabularies turn CRM models into Linked Data.

Controlled vocabularies are essential for indexing and cataloguing Persian cultural heritage. They replace free-text strings with stable, shared identifiers so that data created by different people and institutions can be connected.

This document introduces the main vocabularies used in this learning path and shows how they attach to the object- and event-based patterns you have already seen.

---

## Why Controlled Vocabularies Matter for Linked Data

When two catalogues both write “paper” or “Tabriz” or “Rostam”, a computer cannot be sure they mean the same thing.  
When both use the same identifier from a controlled vocabulary, the link becomes explicit and machine-readable.

In the CIDOC CRM this is normally done with properties such as:

- `P2 has type`
- `P45 consists of`
- `P7 took place at`
- `P129 is about`
- `P67 refers to`

The vocabulary term (or its URI) becomes the object of the property. This is one of the most direct ways the CRM participates in Linked Data.

## The Main Vocabularies in This Repository

| Vocabulary | Full name / Provider | Best used for | Typical CRM property | Persian relevance |
|------------|----------------------|---------------|----------------------|-------------------|
| **AAT** | Art & Architecture Thesaurus (Getty) | Materials, techniques, object types, styles, architectural features | `P2 has type`, `P45 consists of` | Paper types, pigments, illumination techniques, building parts, etc. |
| **TGN** | Thesaurus of Geographic Names (Getty) | Places (cities, regions, historical names) | `P7 took place at`, `P53 has former or current location` | Tabriz, Isfahan, Shiraz, historical Persian toponyms |
| **Iconclass** | Iconclass (independent / RKD) | Iconographic and narrative subjects | `P129 is about`, `P67 refers to` | Shahnameh scenes, biblical and quranic narratives in Persian painting |
| **Wikidata** | Wikidata | Persons, places, works, concepts, identifiers | Direct URI or alignment properties | Almost everything; excellent coverage of Persian cultural figures and places |
| **CONA** | Cultural Objects Name Authority (Getty) | Works of art and architecture as named entities | Reference / alignment for E22 or E24 | Paintings, manuscripts, buildings that already have CONA records |
| **ULAN** | Union List of Artist Names (Getty) | Artists, patrons, architects | `P14 carried out by` | Calligraphers, painters, architects |

## How to Attach a Vocabulary Term (Conceptual Pattern)

Using the manuscript example from the previous document:

```
E22 Manuscript
    P2 has type          →  AAT term for “manuscript” or “codex”
    P45 consists of      →  AAT terms for “paper”, “ink”, “gold”
    P108 was produced by →  E12 Production
                              P7 took place at → TGN place (e.g. Tabriz)
                              P14 carried out by → ULAN or Wikidata person
    P129 is about        →  Iconclass notation (for a specific painting)
```

Each arrow that points to an external vocabulary creates a Linked Data connection.

## Practical Recommendations for Persian Heritage

1. **Prefer URIs over strings**  
   Whenever possible, use the official URI of the AAT, TGN, Iconclass, or Wikidata item.

2. **Start small**  
   You do not need to classify every detail at the beginning. Adding a few high-value terms (object type, main material, place of production, main subject) already makes the record useful for Linked Data.

3. **Wikidata as a practical hub**  
   Wikidata often provides the easiest bridge between Persian names and international identifiers. It can be used both as a source of identifiers and as a place to align local entities.

4. **Iconclass for narrative art**  
   For illustrated manuscripts and wall paintings, Iconclass is currently one of the most precise tools for subject indexing. It works well alongside the CRM even when the rest of the model stays light.

5. **Keep the CRM structure stable**  
   The object and its events remain the backbone. Vocabulary terms are attached to them; they do not replace the object-oriented and event-based model.

## Relationship to Getty CONA and GVP

- The Getty Vocabulary Program (GVP) publishes AAT, TGN, ULAN and CONA.
- CONA records can serve as ready-made identifiers for cultural objects (E22 / E24).
- Even when you do not use a CONA record, the same Getty vocabularies (AAT, TGN, ULAN) can be applied directly inside your CRM descriptions.

## Next Steps in the Learning Path

- Continue to **04 – Internet Archive and IIIF**, where digital surrogates are linked to the objects and events modelled here.
- Or examine concrete Turtle examples (drawn from related repositories) that show these vocabulary links in practice.
- Later revisions of this document will add more detailed Persian examples and ready-to-copy patterns for each vocabulary.

---

Controlled vocabularies do not change the object-oriented or event-based nature of the CRM. They make the descriptions you create with the CRM shareable and connectable — which is the essence of Linked Data for cultural heritage.
