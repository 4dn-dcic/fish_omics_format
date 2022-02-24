Introduction
============

This document describes the **4DN FISH Omics Format - Chromatin
Tracing (FOF-CT)**, a community data format designed for capturing and
exchanging the results of chromosome imaging experiments produced within
the context of the 4D Nucleome project. FOF-CT is directly compatible
with several FISH omics techniques including, but not limited to,
Optical Reconstruction of Chromatin Architecture (ORCA;
https://doi.org/10.1038/s41596-020-00478-x), Multiplexed Imaging of
Nucleome Architectures (MINA;
https://doi.org/10.1038/s41596-021-00518-0), Hi-M
(https://doi.org/10.1016/j.molcel.2019.01.011), DNA Sequential
Fluorescence In Situ Hybridization (seqFISH+;
https://doi.org/10.1038/s41586-019-1049-y), Oligonucleotide Fluorescent
In Situ Sequencing (OligoFISSEQ;
https://doi.org/10.1038/s41592-020-0890-0), DNA Multiplexed error-robust
fluorescence *in situ* hybridization (DNA-MERFISH;
https://doi.org/10.1016/j.cell.2020.07.032), and *In-situ* Genomic
Sequencing (IGS; https://doi.org/10.1126/science.aay3446).
In addition, the format is designed to be consistent with planned future
extensions that will encompass single-molecule localization methods for
volumetric imaging, such as OligoSTORM and OligoDNA-PAINT.

In chromatin tracing experiments, polymer tracing algorithms are used to
string together the localization of individual DNA bright Spots to
reconstruct the three-dimensional (3D) path of chromatin fibers. Thus,
the format is organized around multiple tables. The core of the format
consists of a Spot/Trace table that defines chromatin Traces as
ensembles of individual DNA-FISH bright Spot localizations.

Additional tables support the integration of this core with additional
properties such as quality metrics, physical coordinates placing the
Spot/Trace in the context of cellular space, multiplexed RNA-FISH
results (https://doi.org/10.1073/pnas.1912459116) and with additional
data that is better captured at the global Trace (e.g., expression level
of nascent RNA transcripts associated with a given Trace or overall
localization of the Trace with respect to cellular or nuclear
landmarks), Cell (e.g., boundaries and volume), sub-cellular Region of
Interest (ROI; e.g., Nuclear feature or Nucleolus), or extracellular ROI
(e.g., Tissue) level.
