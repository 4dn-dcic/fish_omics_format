.. toctree::
    :caption: Overview
    :hidden:
    :maxdepth: 2

    self

###########################
4DN FISH Omics Format (FOF)
###########################

A key output of the 4D Nucleome (4DN) project is the open publication of
datasets related to the structure of the human cell nucleus and the genome,
within. Recent years have seen a rapid expansion of FISH-omics methods,
which quantify the spatial organization of DNA, RNA and protein in the
cell and provide expanded understanding of how higher-order chromosome
structure relates to transcriptional activity and cell development.
Despite this progress, FISH-based image-data are not yet routinely made
publicly available upon publication because of the lack of common
specifications for data exchange. This challenge is experienced across
the bioimaging community, as a result a solution built, tested and
proven in 4DN can have a wide impact all over the world.

This document describes the **4DN FISH Omics Format (FOF)**, a community data
format designed for capturing and exchanging the results of FISH-omics
experiments produced within the context of the 4D Nucleome project.

According to the specific experiment sub-type, we

Chromatin Tracing (FOF-CT)
==========================

.. toctree::
    :caption: FOF-CT
    :numbered:
    :maxdepth: 2

    intro_ct
    overview
    core_spot_trace
    rna
    quality
    spot_bio
    demultiplex
    trace
    cell
    roi_subcell
    roi_extracell
    mapping
    revisions
    misc

Genomic Single Molecule Localization (FOF-GSML)
===============================================

.. toctree::
    :caption: FOF-GSML
    :numbered:
    :maxdepth: 2

    intro_gsml
    core_dna_spot
    rna
    quality
    spot_bio
    cell
    roi_subcell
    mapping

Notes
=====
Contributors, listed alphabetically:
Sarah Aufmkolk,
Bogdan Bintu,
Alistair Boettiger,
Andrea Cosolo,
Adam Jussila,
Caterina Strambio De Castillia,
Steven Wang.

.. note::
    Older versions of this document are available in the following Google Doc:
    https://docs.google.com/document/d/1z7rIYsQnbeS7y_SMuwoa8qsWKBD_BpV88vR79WiH_XI/edit?usp=sharing
