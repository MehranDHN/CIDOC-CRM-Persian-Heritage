# 04 – Internet Archive and IIIF as a Participation Layer

**Audience**: Scholars, students, and practitioners in the humanities who want to make Persian cultural heritage material more accessible and to describe it with the CIDOC CRM.

The Internet Archive (IA) offers a practical, low-barrier way to publish digitised resources that are otherwise inaccessible or scattered. Its IIIF service makes those resources citable and reusable. This document shows how IA + IIIF can be combined with the object-oriented and event-based modelling you have already learned.

---

## Why Internet Archive Matters for This Learning Path

Many important Persian manuscripts, documents, photographs, and publications remain difficult to access. The Internet Archive allows individuals and institutions to upload material and immediately receive:

- A stable identifier
- A IIIF Manifest and Canvases
- Long-term public access

Once a resource is on the Internet Archive, it can be described with CRM-aligned metadata and linked to controlled vocabularies. This turns a simple upload into a contribution to Linked Data.

## Basic Concepts You Need

| Term | Meaning in this context |
|------|-------------------------|
| **IIIF Manifest** | A JSON document that describes a digitised object and lists its pages/canvases |
| **IIIF Canvas** | A single page or view inside a Manifest |
| **Digital surrogate** | The digital representation (scan, photograph, IIIF resource) of a physical or conceptual object |
| **CRMdig** | The CIDOC CRM extension that helps distinguish digital objects and digitisation events from the cultural objects themselves |

In the CRM we normally keep three levels separate:

1. The cultural object (E22, E24, E73…)
2. The events that affected it (E12, E11…)
3. The digital surrogate (modelled with CRMdig classes or simply linked)

## Simple Linking Pattern

```
E22 Physical Manuscript
    ← P62 depicts / is depicted by →  (or a dedicated surrogate relation)
        D1 Digital Object (CRMdig)  or  direct reference to IIIF Canvas/Manifest
            ← source → Internet Archive IIIF resource
```

You do not need a full CRMdig implementation at the beginning. Even a clear, documented link from the CRM object to the IA IIIF Manifest or Canvas is already useful.

## Contribution Workflow (Lightweight)

This is a practical sequence for people who want to add currently inaccessible material:

1. **Upload** the resource to the Internet Archive (following IA guidelines and copyright rules).
2. **Obtain** the IIIF Manifest URL (and, if needed, individual Canvas URIs).
3. **Identify** the persistent cultural object (the manuscript, document, photograph, etc.).
4. **Create** a small Turtle (or other RDF) description that:
   - Declares the cultural object (E22 / E24 / E73…)
   - Records at least one key event (usually E12 Production or an E7 Activity)
   - Links to relevant controlled vocabulary terms (AAT, TGN, Wikidata, Iconclass…)
   - Points to the Internet Archive IIIF Manifest or Canvas as the digital surrogate
5. **Publish** the RDF (in this repository, in your own repository, or in a shared triple store).

The result is a contribution that is both human-readable and machine-actionable.

## What This Enables

- Researchers can cite a stable IIIF Canvas instead of an unstable file link.
- Different descriptions of the same IA resource can be connected through the CRM object.
- Controlled vocabulary links (added in section 03) become attached to publicly accessible digital surrogates.
- The approach scales from a single uploaded document to larger collections.

## Practical Notes

- Always respect copyright and cultural sensitivity when uploading.
- Prefer high-quality images when possible; IIIF works with the derivatives IA generates.
- Keep the distinction between the physical/conceptual object and its digital surrogate clear in your documentation.
- Later revisions of this section will include concrete examples drawn from related repositories and ready-to-adapt Turtle snippets.

## Next Steps in the Learning Path

- Continue to **05 – From Examples to Practice**, where reusable Turtle patterns, queries, and contribution templates are collected.
- Or return to earlier sections to add concrete examples from your other repositories.
- Examine the `internet-archive-iiif/` directory (when populated) for shorter focused guides.

---

The Internet Archive does not replace careful cataloguing. It provides an accessible place to put the digital surrogates so that the object-oriented, event-based, and vocabulary-rich descriptions created with the CIDOC CRM can point to something real and publicly available.
