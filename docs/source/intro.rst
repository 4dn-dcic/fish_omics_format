Introduction
============

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

This document describes the **4DN FISH Omics Format - Chromatin
Tracing (FOF-CT)**, a community data format designed for capturing and
exchanging the results of chromosome imaging experiments produced within
the context of the 4D Nucleome project. FOF-CT is directly compatible
with several FISH omics techniques including, but not limited to,
Optical Reconstruction of Chromatin Architecture (`ORCA <https://doi.org/10.1038/s41596-020-00478-x>`_), Multiplexed Imaging of
Nucleome Architectures (`MINA <https://doi.org/10.1038/s41596-021-00518-0>`_), `Hi-M <https://doi.org/10.1016/j.molcel.2019.01.011>`_, DNA Sequential Fluorescence In Situ Hybridization (`seqFISH+ <https://doi.org/10.1038/s41586-019-1049-y>`_), Oligonucleotide Fluorescent In Situ Sequencing (`OligoFISSEQ <https://doi.org/10.1038/s41592-020-0890-0>`_), DNA Multiplexed error-robust fluorescence *in situ* hybridization (`DNA-MERFISH <https://doi.org/10.1016/j.cell.2020.07.032>`_), and *In-situ* Genomic Sequencing (`IGS <https://doi.org/10.1126/science.aay3446>`_). In addition, the format is designed to be consistent with planned future
extensions that will encompass single-molecule localization methods for
volumetric imaging, such as OligoSTORM and OligoDNA-PAINT.

.. note:: FOF-CT is designed to work both in the case in which the genome under study is un-modified and in the case in which it contains INSERTIONS or DELETIONS. To capture genomic variants in FOF-CT please see the instructions in :ref:`core` and include a description of the custom-build using the Variant Call Format (VCF) as indicated in :ref:`_VCF_reference:`

In chromatin tracing experiments, polymer tracing algorithms are used to
string together the localization of individual DNA bright Spots to
reconstruct the three-dimensional (3D) path of chromatin fibers. Thus,
the format is organized around multiple tables. The core of the format
consists of a Spot/Trace table that defines chromatin Traces as
ensembles of individual DNA-FISH bright Spot localizations.

Additional tables support the integration of this core with additional
properties such as quality metrics, physical coordinates placing the
Spot/Trace in the context of cellular space, multiplexed `RNA-FISH results <https://doi.org/10.1073/pnas.1912459116>`_ and with additional
data that is better captured at the global Trace (e.g., expression level
of nascent RNA transcripts associated with a given Trace or overall
localization of the Trace with respect to cellular or nuclear
landmarks), Cell (e.g., boundaries and volume), sub-cellular Region of
Interest (ROI; e.g., Nuclear feature or Nucleolus), or extracellular ROI
(e.g., Tissue) level.

.. figure:: images/FOFbasCT_figure.png
  :class: shadow-image
  :width: 100%
  :align: center

  Figure 1: Schematic representation of 12 tables composing the Fish Omics Format for Chromatin Tracing. Created by Sarah Aufmkolk

Tables
======

.. list-table::
  :header-rows: 1

  * - Number
    - Extended Name
    - Short Name
    - Namespace
    - Requirement Level
    - Recommended
  * - 1
    - :ref:`core`
    - core
    - 4dn_FOF-CT_core
    - **required**
    - NA
  * - 2
    - :ref:`demultiplexing`
    - demultiplexing
    - 4dn_FOF-CT_demultiplexing
    - optional
    - Yes
  * - 3
    - :ref:`trace`
    - trace
    - 4dn_FOF-CT_trace
    - optional
    - Yes
  * - 4
    - :ref:`quality`
    - quality
    - 4dn_FOF-CT_quality
    - optional
    - Yes
  * - 5
    - :ref:`bio`
    - bio
    - 4dn_FOF-CT_bio
    - optional
    - Yes
  * - 6
    - :ref:`rna`
    - rna
    - 4dn_FOF-CT_rna
    - optional
    - Yes
  * - 7
    - :ref:`rna_quality`
    - rna_quality
    - 4dn_FOF-CT_rna_quality
    - optional
    - Yes
  * - 8
    - :ref:`rna_bio`
    - rna_bio
    - 4dn_FOF-CT_rna_bio
    - optional
    - Yes    
  * - 9
    - :ref:`cell`
    - cell
    - 4dn_FOF-CT_cell
    - optional
    - Yes
  * - 10
    - :ref:`extracell`
    - extracell
    - 4dn_FOF-CT_extracell
    - optional
    - Yes
  * - 11
    - :ref:`subcell`
    - subcell
    - 4dn_FOF-CT_subcell
    - optional
    - Yes    
  * - 12
    - :ref:`mapping`
    - mapping
    - 4dn_FOF-CT_mapping
    - *conditionally required*
    - Yes