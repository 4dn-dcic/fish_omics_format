Miscellaneous
=============

.. contents::


Older revision history
----------------------

.. note::
    Older versions of this document are available in the following Google Doc:
    https://docs.google.com/document/d/1z7rIYsQnbeS7y_SMuwoa8qsWKBD_BpV88vR79WiH_XI/edit?usp=sharing

Feb 1, 2021 Alistair Boettiger

Feb 2, 2021 Bogdan Bintu, Steven Wang, Alistair Boettiger

Feb 8, 2021 Bogdan Bintu, Steven Wang, Alistair Boettiger

Feb 9, 2021 Steven Wang, Andrea Cosolo, Andrew Schroeder, Alistair Boettiger

Feb 12, 2021 Alistair

Feb 26, 2021 Caterina Strambio De Castillia

July 6, 2021 Alistair, Andrea

Aug, 2021, Sarah + Alistair

Sept 10, 2021 Alistair

Sept 16, 2021 Sarah (addition of SMLM data example #3 and #4)

October 18-29, 2021 Caterina (various comments and changes)

October 25, 2021 Discussion between Alistair and Caterina to address
several comments/issues. The main clarification point was that this
format is used specifically to define Chromatin Tracing results. This is
a subtype of a more generic FISH Omics Format. Other subtypes will be
defined ASAP.

November, 2021 Caterina (various comments and changes)

February 9, 2022 Caterina and Andrea: Change name and description for
tables #4 and #5 and add Table# to table header.

4DN Experimental and Microscopy Metadata
----------------------------------------

-  Project =
-  Center =
-  Lab =
-  Experiment protocol description =
-  Date collected =
-  Date submitted =
-  Experiment Type = FISH Omics - Chromatin Tracing
-  Experiment Set Type = Replicate
-  Organism = D. melanogaster
-  Biosource Type = tissue culture cell line
-  Biosource = IMR90
-  Modification Type = none
-  Treatment Type = none
-  Microscopy Metadata (including Provenance and Quality Control)
   conforming to 4DN-BINA-OME data model
-  Browsable probe map, (bed file, see example)
-  Probe sequences, (fasta file, see example)

Useful information
------------------

OME-NGFF and OME-Zarr
^^^^^^^^^^^^^^^^^^^^^
-  https://www.biorxiv.org/content/10.1101/2021.03.31.437929v4
-  https://zarr.readthedocs.io/en/stable/

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

Example published / available data sets
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
- Wang...Zhuang 2016, *Science* (IMR90)
- Bintu,Mateo...Boettiger,Zhuang, 2018, *Science* (IMR90, K562, A549, HCT116)
- Mateo...Boettiger 2019, *Nature* (mESC + D. mel)
- Liu...Wang 2020, *Nat. Com.* (mouse liver)
- Saw...Wang,Mango 2020, *Mol Cell* (C. elegans)
- Su...Bintu,Zhuang 2020 *Cell* (IMR90)
- Takei...Cai 2021 *Nature* (mESC)
- Takei...Cai 2021 *bioRxiv* (mouse brain)
- Wiggins...Boettiger,Crabtree. 2021 *NSMB*, (mESC)

Example Tables
^^^^^^^^^^^^^^

[Other publications with potentially accessible and similar data to
aggregate]

- Bintu and Ren Sox2 paper
- Nir...Wu 2018, (localization data is published:
  https://data.4dnucleome.org/experiment-set-replicates/4DNESQN4JCAS/ -
  but data format discussion ongoing)
- Wu lab FISSEQ Nat. Methods chr tracing paper,
- Joyce lab (mostly STORM so far?)
- Nollman lab data

Miscellaneous
^^^^^^^^^^^^^

On multiplexed data

Barcode - made of several readouts

Barcode 1 : **readout** - 0, 5 and 12

Readout table -

Readout X Y Z
