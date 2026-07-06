Background
==========

The FISH Omics Format for Chromatin Tracing (FOF-CT) is an open format for **reporting Chromatin Tracing datasets**. It is intended to **serve the broader community** and to promote the study of the spatial arrangement of DNA, RNA, and proteins within the human cell nucleus, uncovering the functional dynamics of the genome in three dimensions and over time (3D+t = 4D).
FOF-CT originated within the (`4D Nucleome <https://www.4dnucleome.org/>`_) project, but many datasets released in this format have since been produced by laboratories outside the consortium.

We **encourage broad adoption** of, and contribution to, the format by the entire community.

FISH Omics techniques description
---------------------------------

Specific genomic sequences can be visualized by fluorescence in situ hybridization (FISH) using fluorescently labeled DNA probes, and their location in individual cells can be imaged using either traditional microscopy techniques (e.g., widefield or confocal) or super-resolution microscopy, as reviewed by (`Fraser et al. 2015 <https://doi.org/10.1128/MMBR.00006-15>`_) and (`Jerkovic and Cavilli 2021 <https://doi.org/10.1038/s41580-021-00362-w>`_).

Evolutions of these techniques expanded the number of imaged targets to multiple and potentially all DNA segments across the genome (see recent reviews: `Jercovic and Cavalli 2021 <https://doi.org/10.1038/s41580-021-00362-w>`_, `Boettiger and Murphy 2020 <https://doi.org/10.1016/j.tig.2019.12.010>`_, `Hu and Wang 2020 <https://doi.org/10.1016/j.tcb.2020.10.006>`_, `Maslova and Krasikova 2021 <https://doi.org/10.3389/fcell.2021.753097>`_, 
`Zhuang 2021 <https://doi.org/10.1038/s41592-020-01037-8>`_, and `Bouwman et al. 2022 <https://doi.org/10.1016/j.molcel.2023.06.018>`_).

Collectively, these technologies can be called interchangeably **multiplexed FISH** or **FISH omics**, which emphasize the visualization of multiple or ideally all genomic targets, respectively. These methods provide an expanded understanding of how higher-order chromosome structure relates to transcriptional activity and cell development.

A variety of protocols have been developed in the past few years, and they can be divided into two main categories called respectively **ball-and-stick (bas)** or **volumetric (vol)** Chromatin Tracing, depending on whether the targeted genomic segment is visualized as a **centroid** (i.e., fitting the imaged spot of a detected fluorescent signal) or a **cloud of single-molecule localizations** (i.e., often rendered as a volume; see Figure 2 in `Dekker et al. 2023 <https://doi.org/10.1016/j.molcel.2023.06.018>`_).

.. figure:: images/MolBio_Fig1_Aufmkolk_final_600dpi.jpg
  :class: shadow-image
  :width: 100%
  :align: center

  Figure 1: FISH omics methods can be utilized to map chromatin structures across multiple genomic scales (Figure credit: Sarah Aufmkolk; `Dekker et al., 2023, Mol.Cell <https://doi.org/10.1016/j.molcel.2023.06.018>`_.

FISH Omics Format rationale
---------------------------

This document describes the **4DN FISH Omics Format - Chromatin Tracing (FOF-CT)**, a community data format designed for capturing and exchanging the results of Chromatin Tracing experiments. 

FOF-CT is directly compatible with both **ball-and-stick** and **volumetric** Chromatin Tracing techniques. 

FOF-bas-CT is compatible with several **ball-and-stick** FISH-omics techniques including, but not limited to, Optical Reconstruction of Chromatin Architecture (`ORCA <https://doi.org/10.1038/s41596-020-00478-x>`_), Multiplexed Imaging of Nucleome Architectures (`MINA <https://doi.org/10.1038/s41596-021-00518-0>`_), `Hi-M <https://doi.org/10.1016/j.molcel.2019.01.011>`_, DNA Sequential Fluorescence In Situ Hybridization (`seqFISH+ <https://doi.org/10.1038/s41586-019-1049-y>`_), Oligonucleotide Fluorescent In Situ Sequencing (`OligoFISSEQ <https://doi.org/10.1038/s41592-020-0890-0>`_), DNA Multiplexed error-robust fluorescence *in situ* hybridization (`DNA-MERFISH <https://doi.org/10.1016/j.cell.2020.07.032>`_), and *In-situ* Genomic Sequencing (`IGS <https://doi.org/10.1126/science.aay3446>`_). 

Similarly, FOF-vol-CT is compatible with multiple **volumetric** chromatin tracing methods, such as OligoSTORM and OligoDNA-PAINT 
(`Belivau et al.  2017 <https://doi.org/10.1007/978-1-4939-7265-4_19>`_, `Bintu et al. 2018 <https://doi.org/10.1126/science.aau1783>`_, `Nir et al. 2018 <https://doi.org/10.1371/journal.pgen.1007872>`_, `Luppino et al. 2020 <https://doi.org/10.1038/s41588-020-0647-9>`_)

.. note:: FOF-CT is designed to work with both unmodified genomes and genomes containing INSERTIONS or DELETIONS. For guidance on capturing genomic variants using FOF-CT, refer to the instructions in :ref:core, and include a description of the custom build using the Variant Call Format (VCF) as outlined in :ref:`VCF-reference-label`.

.. figure:: images/2026-7-4_Figure_1_FOF-bas-vol-CT_Aufmkolk_Strambio_2026-5-9_CORRESPONDENCE_v1.png
  :class: shadow-image
  :width: 100%
  :align: center

  **Figure 2: Schematic representation of 15 tables composing the Fish Omics Format for Chromatin Tracing.** FOF-CT is a modular format designed to capture Chromatin Tracing data from two experiment modalities: Ball-and-Stick (bas) and Volumetric (vol). Tables are represented as color-coded boxes (**3 red** for bas primary tables; **3 blue** for vol-specific tables; **9 grey** for tables shared across both modalities), with each table's index number and short name in the upper-right corner. (Figure credit: Sarah Aufmkolk).

Summary: FISH Omics Format for ball-and-stick Chromatin Tracing
-------------------------

In **ball-and-stick** Chromatin Tracing experiments, polymer tracing algorithms are used to string together the localization of individual DNA bright Spots to reconstruct the three-dimensional (3D) path of chromatin fibers. 

In order to capture chromatin traces as well as additional metrics captured during the course of the experiment, the FOF-CT format is organized around 12 tables.

The root of the format consists of the **mandatory** :ref:`core` table that defines Chromatin Traces as ordered lists of individual DNA-FISH bright Spots. In addition, eleven supplementary :ref:`BAS-table-reference-label` support the integration of this :ref:`core` with:

#. **Supplementary Spot properties** such as: 

	* Quality metrics. 
	* The underlying primary localization data
	* Physical coordinates placing the Spot/Trace in the context of cellular space.

#. The results of multiplexed `RNA-FISH <https://doi.org/10.1073/pnas.1912459116>`_ experiments 

#. **Supplementary global data** that is better captured at the level of:

	* **Trace** (e.g., expression level of nascent RNA transcripts associated with a given Trace or overall localization of the Trace with respect to cellular or nuclear landmarks).
	* **Cell** (e.g., boundaries and volume).
	* **Sub-cellular Region of Interest** (ROI; e.g., Nuclear feature or Nucleolus).
	* **Extracellular ROI** (e.g., Tissue).

Summary: FISH Omics Format for volumetric Chromatin Tracing
-------------------------

For FOF-vol-CT the root of the format consists of the **mandatory** :ref:`vol-core` that reports the location of individual SM Localization events, the localization of their target chromosome segments, as well as their associated DNA-FISH bright Spots and chromatin Traces. In addition, two supplementary :ref:`VOL-table-reference-label` support the integration of this :ref:`vol-core` with:

#. **Supplementary SM Localization properties** such as: 

	* Quality metrics. 
	* The underlying un-decoded raw localization data

.. Tip:: In addition to the 3 specific :ref:`VOL-table-reference-label`, all 12 :ref:`BAS-table-reference-label` are also available for use to report the results of **volumetric** Chromatin Tracing experiments.

