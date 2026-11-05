---
title: Terminology
hide:
  - toc
---

<div class="hero" markdown>

# Terminology

<p class="hero-tagline">
A glossary of acronyms, projects, and technologies referenced across the
DOE-BRIDGE / BER Data Lakehouse ecosystem.
</p>

</div>

<section class="section section--welcome" markdown>

## Programs & Initiatives

### DOE-BRIDGE

**Biological and enviRonmental Infrastructure for Data manaGement and
Exploration.** This is the high-level BER Lakehouse effort. Formerly referred
to as **BERDL** (BER Data Lakehouse).

- **DOE-BRIDGE DM** — Data Modeling Team
- **DOE-BRIDGE PE** — Platform Engineering Team
- **DOE-BRIDGE UR** — User Research & Engagement Team

> **Note:** BERDL has now been split into **K-BERDL** (KBase BER Data
> Lakehouse) and **J-BERDL** (JGI Data Lakehouse). DOE-BRIDGE is the higher-level
> effort to link them.

### HPDF

**High Performance Data Facility.**

### AmSC

**American Science Cloud.** DOE's next-generation, federated research
ecosystem under the Genesis Mission Platform.

- [AmSC site](https://amsc.energy.gov/)
- AmSC glossary

### Genesis Mission

The top-level AI directive from DOE.

- [Genesis Mission resources](https://drive.google.com/drive/folders/1cszfGF5FBom7uXnBrVoH4hyHTicsoR0l)

</section>

<section class="section section--infrastructure" markdown>

## BER AI Projects

### AIMS-LEAF

**AI-driven Multimodal imaging for Linking gEnotype And Phenotype.** Full
title: *AI-Driven Multimodal Imaging for Predicting Stress Response in
Plants: Linking Genotype to Phenotype across Scales* (PI: Samuel Webb).

### BERtron

The prototype cross-BER data catalogue. 

### APPL ("apple")

**Advanced Plant Phenotyping Lab.** ORNL

### ADP

**Agentic Deep Phenotyping.** 

### BSSD AI Pilot Projects

Projects funded by BER for FY25. Descriptions of projects relevant to the DM
Team are below. List was obtained from the kickoff meeting agenda.

- **OPAL**
- *A Generative Pretrained Transformer for Genomic Photosynthesis to Support
  Abundant Bioenergy Production*
- **BERIL**
- **DOE-BRIDGE**
- **SLAC** — AI-Driven Multimodal Imaging for Predicting Stress Response in
  Plants: Linking Genotype to Phenotype across Scales
- **LAMBDA**

### OPAL

**Orchestrated Platform for Autonomous Laboratories.** Berkeley Lab's portion
of OPAL comprises three projects that are intended to work together:

1. Microbial Genome-to-Function Mapping (Nathan Hillson, Chris Petzold)
2. Data Architectures and Agentic AI (aka **BERIL**; Paramvir Dahal, Chris Mungall)
3. Standardized federated data infrastructure, integration
   models (aka **DOE-BRIDGE Data Modeling Team**; Kjiersten Fagnan, Valerie Skye, Montana Smith, Sierra Moxon, AJ Ireland, Danielle Christianson, Ryan Ly)

### FAMOUS

**Foundational AI Models for Optimizing and Understanding Biological
Systems.** The Model Team will use AI to enable synthetic biology
approaches. Leverage advanced AI to decipher protein and pathway function,
automate data generation and collection. PIs: Douglas Mans, Paul Adams.

### OPAL-FAMOUS

As of January 14, 2026, BER is referring to OPAL and FAMOUS collectively as
"OPAL-FAMOUS."

### A Generative Pretrained Transformer for Genomic Photosynthesis

Oak Ridge is developing a plant phenotype lakehouse framework.

### LAMBDA

**Lakehouse-enabled AI-ready Multi-modal Bioimaging Data Architecture.** PI:
Paul Adams. J. Harry Caufield and Chris Mungall are doing the data modeling for
this project. Framework for all BER-supported structural biology and imaging
resources. Establish common data structures, metadata standards, and APIs
to enable integration of multimodal datasets into the Data Lakehouse. 6-Lab
project. Web site: [https://lambda-doe.org/](https://lambda-doe.org/)

### AMP2

**Anaerobic Microbial Phenotyping Platform.** Hardware platform currently
being installed at EMSL. 

</section>

<section class="section section--modeling" markdown>

## Platforms & Frameworks

### Ganymede

A commercial data lake product based on Google BigQuery. JGI sample data, growth condition
information, and EMSL proteomics data. This data is part of the OPAL lab
automation project. 

### CODA

The UI framework and host for Ganymede system.

### BERIL

**Integrated AI Infrastructure for Genome-to-Phenotype Research Using the
BER Data Lakehouse.**

### CDM

**Central Data Model.** The KBase data model for the KBase Lakehouse.

### KE

**Knowledge Engine.** 

### KBase Tenant

A space set up within the KBase Lakehouse infrastructure for a particular
partner's data.

</section>

<section class="section section--bertron" markdown>

## Storage & Data Technologies

### S3

(Amazon Simple Storage Service.)

### MinIO

(S3-compatible object storage.)

### DuckDB

(In-process analytical database.)

### Parquet

A columnar storage file format.

### Iceberg

Open table format for analytic datasets.

### Dremio

Data lakehouse query engine.

### DBNS

### GCS

**Google Cloud Storage.**

### GOLD

</section>

<section class="section section--infrastructure" markdown>

## AI & Agentic Tooling

### Agentic AI

### MCP

**Model Context Protocol.** A somewhat standardized API (e.g., FastMCP in
Python, or a Node.js implementation) that is popular among Agentic AI
frameworks. Often this is connected to some back-end API or database and is
just a pass-through adapter for Agentic frameworks like Goose or Claude
Code. This, when paired with any LLM, gives that LLM the ability to access
resources provided by that MCP or even to perform actions (e.g., initiate
an analytic workflow with specific parameters and data).

### LLM

**Large Language Model.**

### Goose

### Claude

### Claude Code

</section>

<section class="section section--modeling" markdown>

## Data Concepts

### ETL

**Extract, Transform, Load.**

### Label / Tag / Keyword / Annotation

All often used as synonyms.

### Data Governance

### Data Dictionary

Synonym: **Controlled Vocabulary (CV)**.

</section>

