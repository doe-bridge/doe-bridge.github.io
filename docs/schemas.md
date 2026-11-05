---
title: Data Modeling
hide:
  - navigation
  - toc
---

<div class="hero" markdown>

# Data Modeling

<p class="hero-tagline">
LinkML-based data models that power interoperability across the BER data
lakehouse — from sample context and sequencing metadata to credit and
provenance.
</p>

</div>

<section class="section section--welcome" markdown>

## Overview

Each BER resource has historically managed its metadata independently, with
its own models and tools. The schemas below are the LinkML-based data models
that DOE-BRIDGE partners are aligning to enable cross-lakehouse discovery,
shared ETL tooling, and AI-assisted mapping between datasets. Every schema
links back to its canonical site and repository for documentation, source,
and issues.

</section>

<section class="section section--infrastructure" markdown>

## BERtron Schema

The BERtron schema defines the shared metadata contract used by the
BERtron federated search service to index data across partner lakehouses.
It specifies how each lakehouse describes its holdings so that a single
query can return results spanning EMSL, ESS-DIVE, JGI, KBase, and NMDC.

<div class="grid cards lakehouses" markdown>

-   [![BERtron schema](assets/images/schema.png)](https://doe-bridge.github.io/bertron-schema/)

    __BERtron schema__

    [:material-book-open-variant: Docs](https://doe-bridge.github.io/bertron-schema/){ .card-btn }
    [:material-github: Code](https://github.com/doe-bridge/bertron-schema){ .card-btn }
    {: .card-links }

</div>

</section>

<section class="section section--modeling" markdown>

## KBase Schemas

KBase contributes two complementary schemas to the BER data ecosystem. The
Common Data Model (CDM) schema provides the core types and relationships
KBase uses to represent biological entities, their annotations, and the
analyses performed on them — giving downstream tools a stable, well-documented
vocabulary for computational biology data. The CRediT metadata schema adopts
the community-standard Contributor Roles Taxonomy to describe the specific
contributions each person made to a dataset or analysis, supporting
attribution, reproducibility, and credit across collaborative BER projects.

<div class="grid cards lakehouses" markdown>

-   [![KBase CDM schema](assets/images/partners/kbase.png)](https://kbase.github.io/cdm-schema/)

    __KBase CDM schema__

    [:material-book-open-variant: Docs](https://kbase.github.io/cdm-schema/){ .card-btn }
    [:material-github: Code](https://github.com/kbase/cdm-schema){ .card-btn }
    {: .card-links }

-   [![KBase CRediT metadata schema](assets/images/partners/kbase.png)](https://www.kbase.us/news/kbase-credit-metadata-schema/)

    __KBase CRediT metadata schema__

    [:material-book-open-variant: Docs](https://www.kbase.us/news/kbase-credit-metadata-schema/){ .card-btn }
    [:material-github: Code](https://github.com/kbase/credit_engine){ .card-btn }
    {: .card-links }

</div>

</section>

<section class="section section--bertron" markdown>

## NMDC Schema

The NMDC Schema is critical substrate used to facilitate interoperability
and collaboration, as it provides a common language for data exchange
across systems and disciplines. In the context of the NMDC, this schema
supports the integration of microbiome data from medicine, agriculture,
bioenergy, and environmental science into a cohesive platform.

This schema is organized into two modules:

- A core set of elements for representing data values represented in
  [LinkML format](https://w3id.org/linkml/) consisting of a set of classes,
  slots, types, and enumerations that are used to define the structure of
  the NMDC schema.
- A subset of the MIxS schema developed by the Genomic Standards
  Consortium, that is used to describe the environmental context of
  samples.

<div class="grid cards lakehouses" markdown>

-   [![NMDC schema](assets/images/partners/nmdc.png)](https://microbiomedata.github.io/nmdc-schema/)

    __NMDC schema__

    [:material-book-open-variant: Docs](https://microbiomedata.github.io/nmdc-schema/){ .card-btn }
    [:material-github: Code](https://github.com/microbiomedata/nmdc-schema){ .card-btn }
    {: .card-links }

</div>

</section>

<section class="section section--infrastructure" markdown>

## BASIN-3D

BASIN-3D (Broker for Assimilation, Synthesis and Integration of eNvironmental
Diverse, Distributed Datasets) is a data brokering framework that integrates
environmental data from heterogeneous remote sources into a common model.
Rather than replicating data, BASIN-3D synthesizes it on demand, giving
researchers a unified view over sources like ESS-DIVE, USGS, and EPA.

<div class="grid cards lakehouses" markdown>

-   [![BASIN-3D](assets/images/schema.png)](https://basin3d.readthedocs.io/en/stable/intro.html)

    __BASIN-3D__

    [:material-book-open-variant: Docs](https://basin3d.readthedocs.io/en/stable/intro.html){ .card-btn }
    [:material-github: Code](https://github.com/BASIN-3D/basin3d){ .card-btn }
    {: .card-links }

</div>

</section>

<section class="section section--bertron" markdown>

## Bridge Schemas

Bridge Schemas are LinkML schemas that map and translate between related data
models, enabling interoperability across BER partner resources. They provide
explicit crosswalks that connect overlapping concepts in different schemas so
that data described in one model can be understood and used in the context of
another.

<div class="grid cards lakehouses" markdown>

-   [![Bridge Schemas](assets/images/schema.png)](https://github.com/cmungall/bridge-schemas)

    __Bridge Schemas__

    [:material-github: Code](https://github.com/cmungall/bridge-schemas){ .card-btn }
    {: .card-links }

</div>

</section>

<section class="section section--modeling" markdown>

## LAMBDA

LAMBDA is a LinkML schema developed within the BER community to capture
dataset-level metadata in a shape that supports harmonization across
partner lakehouses. It focuses on the common descriptors needed to connect
experiments, samples, and analyses regardless of the originating resource.

<div class="grid cards lakehouses" markdown>

-   [![LAMBDA schema](assets/images/schema.png)](https://lambda-ber.github.io/lambda-ber-schema/)

    __LAMBDA schema__

    [:material-book-open-variant: Docs](https://lambda-ber.github.io/lambda-ber-schema/){ .card-btn }
    [:material-github: Code](https://github.com/lambda-ber/lambda-ber-schema){ .card-btn }
    {: .card-links }

</div>

</section>
