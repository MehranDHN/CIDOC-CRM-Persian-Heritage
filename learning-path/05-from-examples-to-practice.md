# 05 – From Examples to Practice

**Audience**: Scholars, students, and practitioners who have followed the learning path and now want reusable patterns, queries, and contribution templates they can adapt.

This document collects practical starting points. Most concrete examples will later be drawn from related repositories and added here (or linked from here). The focus is on small, correct, and reusable pieces rather than large complete models.

---

## 1. Minimal Reusable Patterns

### Pattern A – Object + Production Event + Vocabulary Links
```turtle
@prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .
@prefix aat: <http://vocab.getty.edu/aat/> .
@prefix tgn: <http://vocab.getty.edu/tgn/> .
@prefix wd:  <http://www.wikidata.org/entity/> .

<http://example.org/object/manuscript-001> a crm:E22_Human-Made_Object ;
    crm:P2_has_type aat:300026877 ;          # manuscript (example AAT term)
    crm:P108_was_produced_by <http://example.org/event/production-001> .

<http://example.org/event/production-001> a crm:E12_Production ;
    crm:P7_took_place_at tgn:7000000 ;       # replace with real TGN place
    crm:P14_carried_out_by wd:Q000000 ;      # replace with real Wikidata person
    crm:P4_has_time-span <http://example.org/timespan/1520s> .
```

### Pattern B – Linking an Internet Archive IIIF Resource
```turtle
@prefix crm: <http://www.cidoc-crm.org/cidoc-crm/> .

<http://example.org/object/manuscript-001> a crm:E22_Human-Made_Object ;
    crm:P138_represents <http://example.org/digital/ia-manifest-001> .  # or a more precise surrogate property

<http://example.org/digital/ia-manifest-001> a crm:E73_Information_Object ;
    crm:P2_has_type <http://vocab.getty.edu/aat/300264578> ;  # digital image (example)
    # Link to actual Internet Archive IIIF Manifest URL in documentation or via a dedicated property
    .
```

(These are intentionally minimal. Real examples will replace the placeholder URIs with terms and identifiers taken from actual Persian heritage material.)

## 2. Useful SPARQL Query Starting Points

### Find all production events and their places
```sparql
PREFIX crm: <http://www.cidoc-crm.org/cidoc-crm/>

SELECT ?object ?event ?place
WHERE {
  ?object crm:P108_was_produced_by ?event .
  ?event crm:P7_took_place_at ?place .
}
```

### Find objects linked to a specific Iconclass notation or Wikidata item
```sparql
PREFIX crm: <http://www.cidoc-crm.org/cidoc-crm/>

SELECT ?object ?subject
WHERE {
  ?object crm:P129_is_about ?subject .
  # FILTER or VALUES can be added for specific Iconclass or Wikidata URIs
}
```

## 3. Contribution Checklist

When you add a new example (especially one based on material from your other repositories or a new Internet Archive upload), try to include:

- [ ] Clear identification of the persistent object (E22, E24, E73…)
- [ ] At least one event (usually production or modification)
- [ ] One or more controlled vocabulary links (AAT, TGN, Iconclass, Wikidata…)
- [ ] Link to digital surrogate if available (Internet Archive IIIF Manifest or Canvas)
- [ ] Short human-readable explanation
- [ ] Valid Turtle (or other RDF serialisation)

## 4. Suggested Directory Usage

| Location | Purpose |
|----------|---------|
| `turtle/` | Small, self-contained `.ttl` files implementing the patterns above |
| `examples/` | One folder per worked example (Markdown explanation + Turtle) |
| `queries/` | SPARQL queries that can be run against the example data |
| `internet-archive-iiif/` | Focused notes and workflows for IA contributions |

## 5. How This Section Will Grow

- Concrete Turtle files and full examples will be added from related repositories.
- Bilingual (Persian/English) versions of key explanations can be introduced.
- Additional patterns (ownership histories, architectural modification sequences, etc.) will be included as they are developed.
- Validation shapes (SHACL) may be added later if lightweight quality control becomes useful.

## Closing Note on the Learning Path

You have now seen:

1. The object-oriented and event-based foundations of the CIDOC CRM
2. Core modelling patterns for Persian heritage
3. The role of controlled vocabularies in Linked Data
4. How Internet Archive + IIIF can serve as a participation layer
5. Practical patterns and contribution habits

These five parts form a coherent starting point. Each section can now be revised and enriched independently while the overall structure remains stable.

---

**Next practical actions**
- Add the first real examples (from your other repositories) into `examples/` and `turtle/`.
- Test the minimal patterns with a triple store or RDF tool of your choice.
- Invite others to contribute additional Persian examples following the checklist above.
