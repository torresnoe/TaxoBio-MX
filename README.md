# TaxoBio-MX

## A Taxonomically Structured Corpus of Mexican Fauna for Natural Language Processing (NLP) and Artificial Intelligence (AI)

**TaxoBio-MX** is a specialized text corpus designed to advance NLP and AI research and development in the field of biodiversity informatics, with a specific focus on Mexican fauna. This resource addresses the critical gap in standardized, machine-readable textual data in the biodiversity domain by providing a structured, reproducible, and processable collection of information on 2,571 species from the Animalia kingdom.

---

### 🎯 Purpose and Scope

The corpus was constructed following a census-based strategy, using the official species catalog from EncicloVida (CONABIO) as the target population. Its primary goal is to transform fragmented and heterogeneous information from multiple authoritative repositories into a unified computational resource. TaxoBio-MX is ready to be used in a variety of NLP and AI tasks, including:

*   Semantic search and information retrieval on species data.
*   Retrieval-Augmented Generation (RAG) for biodiversity question-answering systems.
*   Automated multi-document summarization of biological and ecological descriptions.
*   Named Entity Recognition (NER) and relation extraction for taxonomic and conservation data.
*   Development and benchmarking of domain-specific language models.

---

### 📚 Data Sources

TaxoBio-MX integrates and normalizes textual content from four complementary and authoritative sources:

*   **EncicloVida (CONABIO):** The primary source, providing species descriptions validated by biodiversity specialists in Mexico.
*   **Global Biodiversity Information Facility (GBIF):** A global source for taxonomic classification and occurrence data.
*   **IUCN Red List of Threatened Species:** Authoritative information on conservation status, ecological traits, and threat factors.
*   **Wikipedia:** A supplementary source that enriches descriptive content, especially for species with limited information in other repositories.

---

### 🏗️ Corpus Organization

To facilitate its use in NLP systems, TaxoBio-MX follows a hierarchical directory structure that mirrors biological taxonomy:

`kingdom -> phylum -> class -> order -> family -> genus -> species`

Each species is stored in its own dedicated directory, named with a unique numerical identifier and its scientific name (e.g., `34460-panthera-onca`). This directory contains the textual documents retrieved from the different sources, ensuring clear provenance and easy programmatic access.

#### Document Types

The corpus includes the following seven document types, each with a specific naming convention:

| Document Type | Source | Description |
| :--- | :--- | :--- |
| `CONABIO_description.txt` | EncicloVida | Detailed species description. |
| `CONABIO_summary.txt` | EncicloVida | Concise summary of the species. |
| `CONABIO_Technical.txt` | EncicloVida | Technical or scientific data sheets. |
| `Wikipedia_es.txt` | Wikipedia | Article in Spanish. |
| `Wikipedia_en.txt` | Wikipedia | Article in English. |
| `IUCN_*.txt` | IUCN Red List | Conservation status and ecological information. |
| `GBIF_*.txt` | GBIF | Taxonomic and occurrence data. |

---

### 🛠️ Construction Methodology

The corpus was built using a rigorous and reproducible **Extract, Transform, Load (ETL)** pipeline, designed to ensure data quality and traceability:

1.  **Extraction:** Automated data acquisition via custom Python scripts using web scraping (Selenium) and official APIs.
2.  **Transformation:**
    *   Text normalization and cleaning.
    *   Language identification using `langdetect`.
    *   Translation of all English documents to Spanish using `deep-translator` to ensure linguistic consistency.
    *   Standardization to UTF-8 encoding.
3.  **Load:** Organization of processed documents into the taxonomic directory hierarchy and storage as plain text files with associated metadata.

This workflow is fully documented to guarantee reproducibility and to allow for future updates as the underlying source repositories evolve.

---

### 📊 Key Statistics (Version 1.0)

*   **Total Species:** 2,571
*   **Total Documents:** 11,027
*   **Taxonomic Coverage:** 5 Phyla, 21 Classes
*   **Document Distribution by Type:**

| Document Type | Count |
| :--- | :--- |
| CONABIO_description | 1,365 |
| CONABIO_summary | 523 |
| CONABIO_Technical | 2,571 |
| Wikipedia_es | 1,504 |
| Wikipedia_en | 1,958 |
| IUCN | 1,992 |
| GBIF | 1,114 |

*   **Document Coverage per Species:**
    *   50.6% of species (1,301) have 5 or more documents.
    *   93.2% of species are associated with at least 2 documents.

---
