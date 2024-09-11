Additional Information
======================

.. contents::

Contributors
------------
Contributors, listed alphabetically:

- Sarah Aufmkolk, Harvard Medical School
- Alistair Boettiger, Stanford University
- Andrea Cosolo
- Rahi Navelkar, Harvard Medical School
- Nuno Martins, Harvard Medical School
- **Caterina Strambio De Castillia**, UMass Chan Medical School, (caterina.strambio@umassmed.edu)
- Steven Wang, Yale University

Older revision history
----------------------
.. note::
    Older versions of this document are available in the following `Google Doc <https://docs.google.com/document/d/1z7rIYsQnbeS7y_SMuwoa8qsWKBD_BpV88vR79WiH_XI/edit?usp=sharing>`_ and `Google Sheet <https://docs.google.com/spreadsheets/d/1GvqokS5w8Yw2tAngsqDC8YcLdRha5cGr/edit?usp=sharing&ouid=103316056144222958298&rtpof=true&sd=true>`_

Useful information
------------------
.. _VCF-reference-label:
The Variant Call Format (VCF)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
The `Variant Call Format (VCF) <https://samtools.github.io/hts-specs/VCFv4.2.pdf>`_ is a standard tab-delimited text file format used in bioinformatics for storing gene sequence variations. The format was developed in 2010 for the 1000 Genomes Project and has since been used by other large-scale genotyping and DNA sequencing projects.

VCF is unambiguous, scalable and flexible, allowing extra information to be added to the info field. 

More information about how to prepare valid VCF files can be found `here <https://gatk.broadinstitute.org/hc/en-us/articles/360035531692-VCF-Variant-Call-Format>`_

.. figure:: images/VCF_IN_example.png
  :class: shadow-image
  :width: 100%
  :align: center

  Figure 2: Schematic representation of the use of VCF to represent a genome variant containing an Inserted DNA fragement. Image from The Variant Call Format (VCF) Version 4.2 Specification, Dec 2013, available at https://cseweb.ucsd.edu/classes/sp16/cse182-a/notes/VCFv4.2.pdf

REMBI: Recommended Metadata for Biological Images
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
- Sarkans, U., Chiu, W., Collinson, L. et al. REMBI: Recommended Metadata for Biological Images—enabling reuse of microscopy data in biology. `Nat Methods 18, 1418–1422 (2021) <https://doi.org/10.1038/s41592-021-01166-8>`_

4DN-BINA-OME-QUAREP (NBO-Q) Microscopy Metadata Specifications
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-  December 20221 Nature Methods FOCUS Issue on `Reporting and reproducibility in microscopy <https://www.nature.com/collections/djiciihhjh>`_
-  Hammer, M., Huisman, M., Rigano, A. et al. Towards community-driven metadata standards for light microscopy: tiered specifications extending the OME model. `Nat Methods 18, 1427–1440 (2021) <https://doi.org/10.1038/s41592-021-01327-9>`_

OME-NGFF and OME-Zarr
^^^^^^^^^^^^^^^^^^^^^
-  Moore, J., Allan, C., Besson, S. et al. OME-NGFF: a next-generation file format for expanding bioimaging data-access strategies. `Nat Methods 18, 1496–1498 (2021). <https://doi.org/10.1038/s41592-021-01326-w>`_
-  Moore, J., et al. OME-Zarr: a cloud-optimized bioimaging file format with international community support. `Histochemistry and Cell Biology 160, 223-251 (2023) <https://doi.org/10.1007/s00418-023-02209-1>`_
-  `Zarr documentation <https://zarr.readthedocs.io/en/stable/>`_


Browsable probe map, example bed file
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

  track name="AllRegions" description="mm10 AllRegions" visibility=1 itemRgb="On"
  chr12 113100000 113130000 IgH_001 1 + 113100000 113130000 255,0,0
  chr12 113130001 113160001 IgH_002 1 + 113130001 113160001 255,14,0
  chr12 113160002 113190002 IgH_003 1 + 113160002 113190002 255,28,0
  chr12 113190003 113220003 IgH_004 1 + 113190003 113220003 255,42,0
  ...

Probe sequence, example fasta file
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^


.. code::

  >FwdPrimer01__BarcodeName__SecondBarcodeName__probeTargetName_p001__RevPrimer01
  GCGGGACGTAAGGGCAACCGcatcaacgccacgatcagctGCTATCGTTCGTTCGAGGCCaggcaattcgagtggcgccctcgaagacgtctcgcaccttCCGTTCTGAGGGTTGCCGTG
  >FwdPrimer01__BarcodeName__SecondBarcodeName__probeTargetName_p002__RevPrimer01
  GCGGGACGTAAGGGCAACCGcatcaacgccacgatcagctGCTATCGTTCGTTCGAGGCCagactttggaagccaccctcattgattgctcgtgctccatCCGTTCTGAGGGTTGCCGTG
  ...

