# Ontology Audit

_Elements of this document involved the use of AI systems including ChatGPT and Safari Browser AI._

# Introduction

As part of the QIMRB 3C project, we have conducted a search for ontologies (and closely related semantic standards) that might be used for activities that are relevant to sharing genomics and genetic research datasets. The list of resources below is loosely grouped by the part of the data-sharing workflow they support and includes the purpose, typical scope, and a pointer to where each is maintained. Many of these are not directly relevant to the activities undertaken as part of QIMRB Project 3C, but they are included for noting.

As a rule, QIMRB holds limited clinical data associated with genomic datasets and relies on the sample originator, usually a clinical collaborator, to hold and manage clinical data, which can be matched to genomic data as needed. Where we do accept clinical or other data, and if that data is already encoded with an ontology, we maintain the encoding by considering it as a controlled vocabulary within our data model.

# Ontologies and Semantic Standards

## Data-use & consent restrictions

- Data Use Ontology ([DUO](https://www.ga4gh.org/product/data-use-ontology-duo/)) - GA4GH standard vocabulary that tags a data set with the exact secondary-use permissions expressed in participant consent (e.g. "disease-specific research only", "methods development permitted"). Widely adopted by EGA, dbGaP and DUOS access brokers.
- Informed Consent Ontology ([ICO](https://obofoundry.org/ontology/ico.html)) - models the structure and key clauses of consent documents so they can be parsed and aligned with DUO terms. Useful when you need to trace conditions back to the signed form.

## Phenotype & disease description

- Human Phenotype Ontology (HPO) - 13 k+ hierarchical terms for clinical features; central to rare-disease diagnostics and GA4GH Phenopacket profiles.
- Mondo Disease Ontology - logic-based unification of OMIM, Orphanet, ICD-10 and others, giving each disease a single, globally resolvable ID. This is the ontology recommended when using DUO.
- Orphanet Rare Disease Ontology (ORDO) - focuses on rare diseases, capturing gene-disease links and epidemiology; recommended for patient registries.

## Sequence & variant representation

- Sequence Ontology (SO) - canonical terms for sequence features and variant consequence (e.g. missense_variant, splice_acceptor_variant); used in VCF/GFF, Ensembl and ClinVar.
- GA4GH Variation Representation Specification (VRS) - JSON information model plus controlled terminology for unambiguous, federated exchange of variants; now at v2.0.
- Variation Ontology (VariO) - describes the mechanistic effect of a variant at DNA, RNA and protein level (structure, function, property changes). Helpful for functional annotation pipelines.

## Biosample, assay & biobanking metadata

- Ontology for Biomedical Investigations (OBI) - 2500+ terms for assays, protocols, instrumentation and study design; a backbone for capturing lab workflow provenance.
- Ontology for Biobanking (OBIB) - builds on OBI to cover biobank administration, specimen handling and storage - critical when harmonising cohorts across sites.

## File formats, analysis types & software context

- EMBRACE Data and Methods (EDAM; EMBRACE = European Model for Bioinformatics Research and Community Education ) - controlled vocabulary for bioinformatics operations, data types, formats and topics; widely used by workflow engines (Galaxy, CWL, Nextflow) for tool annotation.
  - <https://doi.org/10.7490/f1000research.1118900.1> : EDAM; Poster; 2021
  - <https://doi.org/10.1093/nar/gkq297> : EMBRACE Project; Publication; 2010
  - <https://edamontology.org/page>
  - <https://github.com/edamontology/edamontology>
  - <https://bioportal.bioontology.org/ontologies/EDAM>
- Phenopackets schema - not an ontology but a GA4GH container that relies on HPO, MONDO and DUO terms to transmit case-level genotype-phenotype bundles.

## Provenance, authorship & versioning

- PROV-O (W3C) - lightweight OWL ontology for recording what generated a given file (entity-activity-agent). Forms the basis for many pipeline "audit-trail" features.
- PAV - specialises PROV-O for scientific datasets, adding who authored, curated or versioned the resource (useful for data-release notes).

## Clinical reporting & interoperability

- HL7 FHIR Genomics Reporting IG - profile set (R4) that binds FHIR resources to SO, HPO and LOINC/SNOMED CT codes so variant and pharmacogenomic findings flow straight into EHRs.

# Adoption

While many of these standards are not relevant to project 3C, the list below is a draft plan on how the identified resources might be incorporated into a greenfield genomic research effort.

- Match the consent language first - map your study forms to ICO terms, then decorate each dataset with DUO codes so automated access decisions become possible.
- Use HPO + MONDO as the lingua franca for case data - both are referenced by Phenopackets, FHIR Genomics and many rare-disease portals.
- Choose SO (plus VRS if you need computed IDs) for variant exchange; add VariO if functional consequence is central to your project.
- Annotate workflows and outputs with OBI/OBIB and PROV-O for transparent, reproducible pipelines.
- Leverage EDAM in pipeline registries to let others discover tools by input/output type.
- Most of these ontologies live in the OBO Foundry or GA4GH GitHub organisations and publish versioned OWL files; you can pull them via BioPortal or the OLS API for validation in your own metadata pipelines.

# General Data Protection Regulations

## Introduction

The European General Data Protection Regulations (GDPR) is available from [https://gdpr-info.eu](https://gdpr-info.eu/). It was published in the Official Journal of the European Union and a PDF is at: <https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32016R0679>

The PDF is organised in two parts:

- pp1-32: 173 clauses
- pp32-88: 99 Articles in 11 Chapters

This screenshot of the front page of the [gdpr-info.eu](https://gdpr-info.eu/) website shows the organisation of the 99 Articles and is more easily comprehensible than the official PDF even though the content is the same.

In particular, the following articles may be relevant to QIMRB Project 3C:

- Chapter 1
  - Article 4 Definitions
- Chapter 4 - the whole of this is about controller and processor so it's pretty much all relevant.
  - Article 26

## Ontologies

GDPR has a number of ontologies that represent [GDPR concepts and relationships](https://www.google.com/search?client=safari&cs=0&sca_esv=06f1284d0cc9e0ea&sxsrf=AE3TifPJKsYP1DPdvgdWwyhKz6tCpEv72Q%3A1756686097858&q=GDPR+concepts+and+relationships&sa=X&ved=2ahUKEwjU9b_WpbaPAxUh1TgGHTkRD5sQxccNegQIAhAB&mstk=AUtExfAAyF8YG6MG9LSKdy-7wgus6CKPQwwAIaksSLylgRfjphBi1G5bvQ3uxupL8aIAiU0IMz0Az_qZh1e-iU73J1b9vlctyrjJKCbCvJHYhX79Opjd4DZbVp6aapYgmYjs8eXUHHmi7S32NwTOCk4sk3bcDDc6_DlPqdNO78PNw39Q8Q0&csui=3). These ontologies facilitate legal reasoning, compliance checking, and the systematic recording and retrieval of processing metadata. Examples include:

- _PrOnto,_ which models core GDPR concepts like agents, data types, and processing purposes;
- _smashHitCore_, a unified model for consent and contracts;
- _GConsent_, focused on representing consent information under GDPR;
- _CIDaTa_, for modelling international data transfers.

# GA4GH

The following activities from GA4GH are potentially relevant:

- Experiments Metadata Standard: <https://github.com/ga4gh/experiments-metadata>
- Quality Control of WGS: <https://github.com/ga4gh/quality-control-wgs>

# Australian Institute of Health and Welfare

The Australian Institute of Health and Welfare (AIHW) provides national metadata standards for health and welfare information through its [Metadata Online Registry (METEOR)](https://www.aihw.gov.au/about-our-data/accessing-data-through-the-aihw/metadata-standards), which serves as a repository for health, housing, and community sector metadata. This system helps ensure the quality, accuracy, and comparability of data by providing standardised definitions and classifications for health and welfare concepts, supporting the AIHW's role in generating authoritative statistics and informing policy and service delivery for Australians.

# Relevant Australian documents

- Government
  - Fact sheet - NSW public sector agencies and the GDPR: <https://www.ipc.nsw.gov.au/fact-sheet-nsw-public-sector-agencies-and-gdpr>
  - Australian entities and the European Union General Data Protection Regulation: <https://www.oaic.gov.au/privacy/privacy-guidance-for-organisations-and-government-agencies/more-guidance/australian-entities-and-the-european-union-general-data-protection-regulation>

# Conclusions

While the search identified many ontologies and standards relevant to genomics, there was relatively little directly relevant to the data sharing QIMRB Project 3C.
