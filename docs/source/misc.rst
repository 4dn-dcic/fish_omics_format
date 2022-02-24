Miscellaneous
=============

.. contents:: Table of Contents

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
