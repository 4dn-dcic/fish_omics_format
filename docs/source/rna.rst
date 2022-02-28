.. _rna:

RNA-Spot Data table (conditionally required)
============================================

.. contents::

Summary
-------

*(each line corresponds to an individual RNA bright Spot)*

This table is used to store and share the results of RNA FISH-omics experiments
and it is required in the case RNA data was collected as part of this
experiment. Each row represents a detected RNA bright Spot
and corresponds to the localization of a specific RNA transcript. At a
minimum, one needs to know the Spot_ID, the X, Y, Z coordinates of each
localization, the Gene_ID and an additional ID used to link this data
with other tables in this format (i.e., Trace_ID, ROI_ID and/or
Cell_ID). In addition, in case multiple transcripts are associated with
the same Gene_ID and the FISH probes are capable of distinguishing them,
Transcript_ID MUST also be reported. Thus, at a minimum there needs to
be 6 (or 7) data columns. These are required. All other data columns are
optional.

In this table the reported X, Y and Z coordinates are assumed to result
from post-processing and quality control procedures and therefore
correspond to the final localization of the RNA molecule under study.

In the case of multiplexed FISH experiments (i.e., MERFISH) in which the
final localization of RNA molecule results from combining multiple
detection events (e.g., by combining Spots detected in separate images),
the underlying raw data can be recorded in corresponding RNA Spot
quality tables as described below.

Example
-------

.. include:: examples/rna
  :code:

File Header
-----------

The first line in the header is always "##FOF-CT_version=vX.X"

The header MUST to contain a mandatory set of fields that describe the
algorithm(s) that were used to identify and localize bright Spots.
In case more than on algorithm were used, please use the same set of fields
for each of them.

The header should include a detailed description of each optional columns used.

.. list-table::
  :header-rows: 1

  * - Name
    - Description
    - Example
    - Conditional requirement conditions
  * - **##FOF-CT_version=**
    - Version of the FOF format used in this case.
    - v0.1
    -
  * - **##Table_namespace=**
    - 4dn_FOF-CT_RNAspot
    -
    -
  * - #lab_name:
    - name of the lab where the experiment was performed.
    - Nobel
    -
  * - #experimenter_name:
    - name of the person performing the experiment.
    - John Doe
    -
  * - **#experimenter_contact:**
    - email address of the person performing the experiment.
    - john.doe@email.com
    -
  * - **#description:**
    - A free-text, description of the experiment and of the data recorded in this table. This description should provide a clear understanding of the process utilized to produce the data and contain sufficient details to ensure interpretation and reproducibility.
    -
    -
  * - **#Software_Title:**
    - The name of the Software(s) that were used in this case for localizing individual FISH-omics bright Spots and/or to produce three-dimensional (3D) polymeric chromatin Traces.
    - ChrTracer3
    -
  * - **#Software_Type:**
    - The type of this Software. Allowed values: SpotLoc, Tracing, SpotLoc+Tracing, Segmentation, QC, Other
    - SpotLoc+Tracing
    -
  * - **#Software_Authors:**
    - The Name(s) of the individual Author(s) of this Software. In case there are more than one Authors, individual names should be listed as follows, Doe, John; Smith, Jane; etc,.
    - Mateo, LJ; Sinnott-Armstrong, N; Boettiger, AN
    -
  * - **#Software_Description:**
    - A free-text, description of this Software. This description should provide a detailed understanding of the algortithm and of the analysis parameters that were used, in order to guarantee interpretation and reproducibility.
    - ChrTracer3 software was developed for analysis of raw DNA labeled images. As an input, it takes an.xlsx table containing information and folder names of the DNA experiment. As an output, it returns tab delimited.txt ﬁles with drift-corrected x, y, z positions for all labeled barcodes. These can be used directly to calculate the nm scale distances between all pairs of labeled loci. The current version of the software as of this writing is ChrTracer3.
    -
  * - **#Software_Repository:**
    - The URL of any repository or archive where the Software executable release can be obtained.
    - https://github.com/BoettigerLab/ORCA-public
    -
  * - **#Software_PreferredCitationID:**
    - The Unique Identifier for the preferred/primary publication describing this Software. Examples include, Digital Object Identifier (DOI), PubMed Central Identifier (PMCID), ArXiv.org ID etc,.
    - https://doi.org/10.1038/s41596-020-00478-x
    -
  * - #additional_tables:
    - list of the additional tables being submitted. Note: use a comma to separate each table name from the next.
    - DNA_Spot/Trace_Data.csv, Spot_Quality.csv, Spot_Biological_Data.csv, Gobal_Trace_Data.csv, Global_Cell_Data.csv
    -
  * - ##genome_assembly=
    - Genome build. Note: the 4DN Data Portal only accepts GRCh38 for human and GRCm38 for mouse.
    - GRCch38
    -
  * - **##Gene_ID_type=**
    - The field used to report the type of unique ID used to identify the Gene encoding for the targeted RNA transcript.
    - Ensemble_V38
    -
  * - *##Transcript_ID_type=*
    - The field used to report the type of unique ID used to identify the targeted RNA transcript.
    - Ensemble_V38
    - Conditional requirement: this MUST be reported if multiple transcripts are associated with the same Gene_ID and the FISH probes are capable of distinguishing them.
  * - **##XYZ_unit=**
    - The unit used to represent XYZ location of bright Spots in this table. Note: use micron (instead of µm) to avoid problem with special, Greek symbols. Other allowed values are: nm, mm etc.
    - micron
    -
  * - **##columns=**
    - list of the data column headers used in the table. Note: enclose the column headers and use a comma to separate each header name from the next.
    - (Spot_ID, X, Y, Z)
    -

Data Columns
------------

As with all other Spot Data tables in this format, each row corresponds to
data associated with an individual Spot.

The first columns are always: Spot_ID, X, Y, Z coordinates, RNA_name,
Gene_ID(, Transcript_ID).
The order of the other columns is at user's discretion.
The order of the rows is at user's discretion.

.. list-table::
  :header-rows: 1

  * - Name
    - Description
    - Example
    - Conditional requirement conditions
  * - **Spot_ID**
    - A unique identifier for this bright Spot.
    - 1
    -
  * - **X**
    - The sub-pixel X coordinate of this bright Spot. NOTE: the reported X position is understood to be the one resulting from any performed post-processing procedures (i.e. drift correction, chromatic correction etc).
    - 14.43
    -
  * - **Y**
    - The sub-pixel Y coordinate of this bright Spot. NOTE: the reported Y position is understood to be the one resulting from any performed post-processing procedures (i.e. drift correction, chromatic correction etc).
    - 14.43
    -
  * - **Z**
    - The sub-pixel Z coordinate of this bright Spot. NOTE: the reported Z position is understood to be the one resulting from any performed post-processing procedures (i.e. drift correction, chromatic correction etc).
    - 1.23
    -
  * - **RNA_name**
    - This is the official name of the Gene the targeted RNA is transcribed from.
    - ACTB
    -
  * - **Gene_ID**
    - This is the official ID for the Gene encoding for the targeted RNA transcript.
    - ENSG00000075624
    -
  * - *Transcript_ID*
    - This is the official ID for the targeted RNA transcript. This field is required in case the same Gene has multiple different Transcripts and the FISH probe used in this case is capable of distinguishing between them.
    - ENST00000646664.1
    - Conditional requirement: this MUST be reported if multiple transcripts are associated with the same Gene_ID and the FISH probes are capable of distinguishing them.
  * - *Trace_ID*
    - This fields reports the unique identifier for a DNA Trace identified as part of this experiment. Note: this is used to connect data in this table with a given Trace and with Trace specific measurements as recorded in the corresponding Trace_Data table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a Trace identified as part of this experiment.
  * - *Sub_Cell_ROI_ID*
    - If known, this fields reports the unique identifier for a Region of Interest (ROI) that represents the boundaries of a sub-cellular structure a given Spot is associated with. Note: this is used to connect individual Spots that are part of the same ROI. It is also used to connect data in this table with any ROI specific measurements such as boundaries, intensities or volume, recorded in the corresponding ROI_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a Sub_Cell_ROI identified as part of this experiment.
  * - *Cell_ID*
    - If known, this fields reports the unique identifier for the Cell a given Spot is associated with. Note: this is used to connect individual Spots that are part of the same Cell. It is also used to connect data in this table with any Cell specific measurements such as boundaries, intensities and volume, recorded in the corresponding Cell_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a Cell identified as part of this experiment.
  * - *Extra_Cell_ROI_ID*
    - If known, this fields reports the unique identifier for a Region of Interest (ROI) that represents the boundaries of a extracellular structure (e.g., Tissue) a given Spot is associated with. Note: this is used to connect individual Spots that are part of the same ROI. It is also used to connect data in this table with any ROI specific measurements such as boundaries, intensities and volume, recorded in the corresponding ROI_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a extracellular structure ROI (e.g., Tissue) identified as part of this experiment.
