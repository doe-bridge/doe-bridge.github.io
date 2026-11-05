---
date: 2026-11-05
categories:
  - Data Modeling
tags:
  - linkml
  - bervo
  - measurements
  - samples
  - schema
authors:
  - sierra-moxon
---

# How BRIDGE Models Data: LinkML and Ontologies

BRIDGE connects data from independently run BER resources: JGI, EMSL,
ESS-DIVE, KBase, and NMDC. Each resource keeps its own database and its
own formats. BRIDGE adds a shared data model on top, so a query can span
all of them.

This post explains how that data model is built: the schema language
(LinkML), the ontology that names measured properties (BERVO), and two
schema modules you can read and test today.

<!-- more -->

## Connecting independently operated facilities raises some questions:

1. What is the data model for experiment results, and who owns the schema?
2. How does data get published, and how can another system ingest or
   mirror it?
3. How are samples and materials tracked as they move through workflows?

The sections below answer each one for BRIDGE.

## The schema language: LinkML

BRIDGE writes its schemas in [LinkML](https://linkml.io), a schema
language whose source files are plain YAML. That choice gives us four
things:

- **One source of truth, many formats.** A LinkML schema compiles to JSON Schema,
  SQL table definitions, Python classes, RDF/OWL, and browsable
  documentation. 
- **Modules.** The
  [BRIDGE central schema](https://github.com/doe-bridge/bridge-central-schema)
  is a small core that imports focused modules: measurements, samples, and
  processing, shared identifiers. Each partner resource also keeps its own
  full schema (see the [Data Modeling](../../schemas.md) page) and maps it
  to the central one.
- **Transparent development.** The schema lives in a public GitHub repository.
  Every change is a pull request reviewed by people from the partner
  facilities, and every release is versioned. "Who owns the schema" has a
  concrete answer: the repository and its review process.
- **Tests.** Each module ships with example records that must validate and
  counter-example records that must fail, all checked in CI. A schema
  change that breaks real data fails before it merges.

## Naming properties: One example: BERVO and mappings

Two facilities can store the same property under different names. GOLD
records an organism's pressure tolerance, EMSL MONet records soil
phosphate, BASIN-3D brokers river discharge. A federated query needs to
know when two columns describe the same property.

Every BRIDGE measurement names its property with one of three options,
tried in order:

1. a term from [BERVO](https://github.com/bioepic-data/bervo), the
   Biological and Environmental Research Variable Ontology;
2. a BRIDGE-issued property identifier, used when BERVO has no term for
   the property yet;
3. a free-text label, so a record with an unrecognized property is still
   stored.

Correspondences to other vocabularies, such as MIxS and METPO, live in
[SSSOM](https://mapping-commons.github.io/sssom/) mapping tables inside
the schema repository, so the mappings are version-controlled and
machine-readable alongside the schema itself.
The schema classes also declare their relationships to external models
(`sosa:Observation`, NMDC's `QuantityValue`) in the schema source.

## Schema artifact 1: the measurements module

The [measurements module](https://github.com/doe-bridge/bridge-central-schema/pull/9)
came out of a cross-facility hackathon. It models one value of one
property of one thing, as reported by a source. A single `Measurement`
class always keeps the source text verbatim (`raw_value`) and adds
structured fields — number, range, unit, statistic, qualifier,
missing-value reason, method, time, source lineage — when the source
supports them.

The module was built from real rows. A GOLD cell that packs a range and
an optimum into one string becomes two clean records. Here is the range:

```yaml
observed_property: bridge_property:pressure
feature_of_interest: gold:Go0120212
raw_value: 0–30 MPa (Optimal 10MPa)
minimum_numeric_value: 0
maximum_numeric_value: 30
unit: MPa
value_qualifier: tolerated
source_system: ber_registry:schema-jgi-gold
source_record_id: Go0120212
source_field: organism_pressure
```

A nitrate value below the detection limit keeps that information as a
coded reason, with no fabricated number:

```yaml
observed_property: bridge_property:nitrate_concentration
feature_of_interest: nmdc:bsm-11-2hswww54
raw_value: below detection
missing_value_reason: below_detection_limit
unit: umol/L
source_system: ber_registry:schema-nmdc-schema
```

The test suite holds valid examples copied from real GOLD, NMDC, EMSL
MONet, ORNL APPL, BASALT, and BASIN-3D rows; invalid examples that each
break one rule; and "known gap" examples that record what the model
cannot yet express. The gaps are tracked in the repository as open
issues.

## Schema artifact 2: samples and provenance

The [umbrella module](https://github.com/doe-bridge/bridge-central-schema/pull/16)
(in review) adds the shared classes above measurements: `Study`, `Site`,
`Organism`, and `Sample`. It also defines an abstract `PlannedProcess`
class with `has_input` and `has_output` fields, and a
`MaterialProcessing` subclass for steps that turn one sample into
another. Each class declares its mappings to nmdc-schema, BASALT, and COB
(the Core Ontology for Biology and Biomedicine).

Chaining processes through their inputs and outputs gives sample
provenance: this sample was derived from that sample by this step. The
same structure describes samples moving through automated and autonomous
lab workflows, and every measurement points at the sample it describes
through `feature_of_interest`.

## Connecting to BRIDGE

A facility or network that wants to interoperate with BER data can start
with any of these steps:

- **A pilot crosswalk.** Map a sample of your measurement or sample
  records to the BRIDGE central schema. The schema's example-based tests
  check the result, so a crosswalk can be submitted and reviewed as a
  pull request.
- **Schema export.** Adopting LinkML is optional. Any machine-readable
  schema — JSON Schema, SQL, OWL — is enough to build a crosswalk. But we have found
  LinkML to be a superior schema metadata, mapping, and computation tool and using it means
  easier interoperability.
- **SSSOM mappings.** Optional property-level correspondences between your
  vocabulary and BERVO or BRIDGE terms, maintained as TSV files in
  version control.
- **Standards conversations.** Schema design happens in public issues and
  pull requests on the
  [BRIDGE GitHub organization](https://github.com/doe-bridge). Anyone
  working on the same modeling questions is welcome to join them.
