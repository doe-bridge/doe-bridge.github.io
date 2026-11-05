---
title: BER Data
hide:
  - navigation
  - toc
---

<div class="hero" markdown>

# DOE-BRIDGE: A Scientific Data Ecosystem

<p class="hero-tagline">
Open data, software, and schemas for the U.S. Department of Energy's
Biological and Environmental Research (BER) community.
</p>

[Data Lakehouse :material-arrow-down:](#data-lakehouse){ .md-button .md-button--primary }
[Data Modeling :material-arrow-down:](#data-modeling){ .md-button }
[Collaboration :material-arrow-down:](#national-lab-collaboration){ .md-button }
[Team :material-arrow-down:](#team){ .md-button }

</div>

<section class="section section--welcome" markdown>

## Welcome :wave:

Biological sciences are entering a new era — one shaped by data and powered by
strategic national resources like BER. These resources do more than store
scientific information; they enable discovery by collecting, transforming, and
organizing vast volumes of data. A single experimental file may be accompanied
by hundreds of thousands to millions of pieces of metadata — contextual details
essential for future use. To fully realize the benefits of Artificial
Intelligence (AI) in this space, we must go beyond simply accumulating data.
We need purposeful, high-quality data — curated and annotated at the time of
collection but structured to support future insight and innovation. This
requires smart, flexible data systems capable of linking diverse data types
across multiple institutions.

Investing in this curated data infrastructure is not just a technical choice,
it is a strategic imperative — one that lays the groundwork for predictive
science, accelerates discovery, and ensures the U.S. remains at the forefront
of scientific innovation.

For more information about the research programs and data centers supported
by DOE, click below.  It is likely that this list is currently incomplete, 
to add a resource or otherwise edit this list, please contact `smoxon @ lbl.gov` - feedback welcome!

<div class="grid cards doe-ber" markdown>

-   [![DOE BER research programs and data centers](assets/images/DOEBER.png)](https://portal.nersc.gov/cfs/m3408/nmdc-sfas-brcs/browser.html)

</div>

</section>

<section class="section section--infrastructure" markdown>

## Data Lakehouse

The data lakehouse architecture pattern was first described in 2021
([source PDF](https://people.eecs.berkeley.edu/~matei/papers/2021/cidr_lakehouse.pdf)).


!!! note
    System in development: architecture is subject to change.

Solving today's grand scientific challenges requires more than biology — it
demands interdisciplinary innovation in computation and data science. Yet,
many of our existing resources are designed with biological research in mind,
not computational discovery. While datasets may share high-level descriptors
like PI, project, or resource, and feature rich annotations from tools like
GO, ChEBI, or KEGG, the connective tissue — samples, analyses, metadata —
differs dramatically across platforms.

At JGI, for example, data is organized by PI and proposal, streamlining access
for individual users but making it harder to search by organism or taxa. In
contrast, NMDC builds around physical samples, EMSL emphasizes instrumentation,
and ESS-DIVE focuses on project datasets. This fragmentation poses a major
roadblock to scientific discovery — especially for AI systems that thrive on
pattern recognition across diverse, structured datasets.

To unlock the full potential of our data, we must reimagine our architecture.
We need new data structures and algorithms capable of linking billions of data
points across modalities, disciplines, and institutions — making science not
just accessible, but truly interoperable and discoverable at scale.


<div class="grid cards lakehouses" markdown>

-   [![J-BERDL](assets/images/partners/jgi.png)](https://lakehouse-poc.jgi.lbl.gov/)

    [__J-BERDL__](https://lakehouse-poc.jgi.lbl.gov/)

-   [![K-BERDL](assets/images/partners/kbase.png)](https://hub.berdl.kbase.us/)

    [__K-BERDL__](https://hub.berdl.kbase.us/)

</div>

</section>

<section class="section section--modeling" markdown>

## Data Modeling

Creating connections across projects. Each BER resource collects, stores,
and aggregates vast amounts of scientific data, with potentially millions of
pieces of metadata describing the context of each experiment. Well-defined
formats and community standards (GO, ENVO, GOLD, ChEBI, MIxS, and others)
exist, but every resource has historically managed its metadata
independently with its own models and tools.

DOE-BRIDGE is assembling a Data Stewards committee with representatives from
each partner organization. The Data Stewards create and maintain LinkML
models for every data source registered in their respective lakehouses,
building on the foundation of existing schemas. Each lakehouse maintains a
data directory describing its holdings, and DOE-BRIDGE operates a central
registry that indexes across lakehouses so scientists can discover what
data exists and where it resides.

<div class="grid cards lakehouses" markdown>

-   [![Schemas](assets/images/schema.png)](schemas.md)

    [__Schemas__](schemas.md)

-   [![Registry](assets/images/registry.png)](https://github.com/doe-bridge)

    [__Registry__](https://github.com/doe-bridge)

</div>

</section>

<section class="section section--bertron" markdown>

## National Lab Collaboration

<div class="grid cards partner-logo" markdown>

-   [![LBNL](assets/images/labs/lbnl.png)](https://www.lbl.gov/)

    [__LBNL__](https://www.lbl.gov/)

-   [![PNNL](assets/images/labs/pnnl.png)](https://www.pnnl.gov/)

    [__PNNL__](https://www.pnnl.gov/)

-   [![ORNL](assets/images/labs/ornl.png)](https://www.ornl.gov/)

    [__ORNL__](https://www.ornl.gov/)

-   [![ANL](assets/images/labs/anl.png)](https://www.anl.gov/)

    [__ANL__](https://www.anl.gov/)

</div>
This architecture pattern enables all participants to contribute their own
compute and storage infrastructure. Implementation of the same technology
stack and collaborative management of the data catalog allows for a logically
unified view of distributed assets.

Explore the variety of data available from EMSL, ESS-DIVE, JGI, KBase and NMDC
by accessing our code repos, or sites.

</section>

<section class="section section--contribs" markdown>

## Team

Representatives from these institutions have committed time to building the
global search resource and data lakehouse.

### Partners

<div class="grid cards partner-logo" markdown>

-   [![JGI](assets/images/partners/jgi.png)](https://jgi.doe.gov/)

    [__JGI__](https://jgi.doe.gov/)

-   [![ESS-DIVE](assets/images/partners/ess-dive.png)](https://ess-dive.lbl.gov/)

    [__ESS-DIVE__](https://ess-dive.lbl.gov/)

-   [![NMDC](assets/images/partners/nmdc.png)](https://microbiomedata.org/)

    [__NMDC__](https://microbiomedata.org/)

-   [![EMSL](assets/images/partners/emsl.svg)](https://www.emsl.pnnl.gov/)

    [__EMSL__](https://www.emsl.pnnl.gov/)

-   [![KBase](assets/images/partners/kbase.png)](https://www.kbase.us/)

    [__KBase__](https://www.kbase.us/)

</div>

### Staff

<div class="grid cards staff-compact" markdown>

-   __Valerie Skye__

    JGI, DOE-BRIDGE

-   ![Kjiersten Fagnan](assets/images/staff/fagnan.jpg)

    __Kjiersten Fagnan__

    JGI

-   __Danielle Christianson__

    ESS-DIVE, DOE-BRIDGE

-   ![Shreyas Cholia](assets/images/staff/cholia.png)

    __Shreyas Cholia__

    ESS-DIVE, NMDC

-   ![Alicia Clum](assets/images/staff/clum.jpg)

    __Alicia Clum__

    NMDC

-   ![Sierra Moxon](assets/images/staff/moxon.png)

    __Sierra Moxon__

    NMDC, DOE-BRIDGE

-   ![Makena Dettmann](assets/images/staff/dettmann.jpeg)

    __Makena Dettmann__

    EMSL

-   ![James Carr](assets/images/staff/carr.jpg)

    __James Carr__

    EMSL

-   ![Montana Smith](assets/images/staff/smith.jpg)

    __Montana Smith__

    EMSL, NMDC, DOE-BRIDGE

-   __Conrad Mearns__

    EMSL, DOE-BRIDGE

-   ![Ryan Ly](assets/images/staff/ly.png)

    __Ryan Ly__

    JAMO, DOE-BRIDGE

-   ![AJ Ireland](assets/images/staff/ireland.png)

    __AJ Ireland__

    KBase, DOE-BRIDGE

-   ![Gazi Mahmud](assets/images/staff/mahmud.jpg)

    __Gazi Mahmud__

    KBase

-   ![Elisha Wood-Charlson](assets/images/staff/wood-charlson.jpg)

    __Elisha Wood-Charlson__

    KBase

-   __Georg Rath__

    JGI, DOE-BRIDGE

-   __Deanna Beatty__

    JGI, DOE-BRIDGE

</div>

!!! note "Join us"
    Contributors are welcome. Open an issue or PR on any of our
    [repositories](https://github.com/doe-bridge).

</section>

<section class="section section--funding" markdown>

<p class="funding-attribution">
  Supported by
  <a href="https://www.energy.gov/science/ber/biological-and-environmental-research">
    <img src="assets/images/doe.png" alt="U.S. Department of Energy" class="doe-logo">
  </a>
</p>

</section>
