.. _core_spot_trace:

DNA-Spot/Trace Data core table (required)
=========================================

.. contents::

Summary
-------

This is the mandatory core table of the 4DN FISH-omics Format for Chromatin
Tracing. This table is used to record and exchange the primary results of
Chromatin Tracing experiments. The Table is organized around individual DNA
bright Spots that are spatially linked together in a three-dimensional (3D)
polymeric Trace using a 3D polymeric tracing algorithm. As a result, all Spots
that share the same Trace_ID, by definition belong to the same Trace.

Each row reports the x, y, z localization, and the Trace assignment
(i.e., Trace_ID) of a FISH-omics bright Spot and corresponds to a specific
genomic DNA target sequence identified by Chromosome ID, and by Start and End
chromosome coordinates.

At a minimum the Table has to have 8 columns in the following order: Spot_ID,
Trace_ID, X, Y, Z coordinates, Chromosome ID, Chromosome Start, Chromosome End.
These are required.
Additionally in case sub-cellular structures, cells or Extra Cellular
Structures (e.g., Tissue) are identified as part of this experiment,
this table has to mandatorily include the ID of the Sub_Cellular, Cell or
Extra Cellular Structure (e.g., Tissue) Region of Interest (ROI)
each Spot/Trace is associated with. The order of these columns is optional.

All other spot properties should be kept in the optional
additional Spot Biological Data table, indexed by Spot_ID.

Example
-------

.. include:: examples/core_spot_trace
  :code:

File Header
-----------

The first line in the header is always "##FOF-CT_version=vX.X"

The header MUST to contain a mandatory set of fields that describe the
algorithm(s) that were used to identify and localize bright Spots and to
connect them to form Traces.
In case more than one algorithm were used, please use the same set of fields
for each of the algorithm used.

The columns for this table are mandatory and do not need to be described
in the header.

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
    - 4dn_FOF-CT_master
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
  * - **#additional_tables:**
    - list of the additional tables being submitted. Note: use a comma to separate each table name from the next.
    - RNA_Spot_Data.csv, Spot_Quality.csv, Spot_Biological_Data.csv, Gobal_Trace_Data.csv, Global_Cell_Data.csv
    -
  * - **##genome_assembly=**
    - Genome build. Note: the 4DN Data Portal only accepts GRCh38 for human and GRCm38 for mouse.
    - GRCch38
    -
  * - **##XYZ_unit=**
    - The unit used to represent the XYZ location of bright Spots in this table. Note: use micron (instead of µm) to avoid problems with special, Greek symbols. Other allowed values are: nm, mm etc.
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

The first columns are always: Spot_ID, Trace_ID, X, Y, Z, Chrom, Chrom_Start,
Chrom_End.
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
    -
    -
  * - **Trace_ID**
    - In case multiple DNA Spots are connected to form 3D polymer traces of chromatin fibers (such as in ORCA; https://doi.org/10.1038/s41596-020-00478-x), this fields reports a unique identifier for the DNA trace the Spot belongs to. Note: this is used to connect Spots that are part of the same polymeric Trace. It is also used to connect data in this table with any Trace specific measurements such as nascent RNA expression, recorded in the corresponding Trace_Data table.
    - 1
    -
  * - **X**
    - The sub-pixel X coordinate of this bright Spot. NOTE: the reported X position is understood to be the one resulting from any performed post-processing correction procedures (i.e. drift correction, chromatic correction etc).
    -
    -
  * - **Y**
    - The sub-pixel Y coordinate of this bright Spot. NOTE: the reported Y position is understood to be the one resulting from any performed post-processing correction procedures (i.e. drift correction, chromatic correction etc).
    -
    -
  * - **Z**
    - The sub-pixel Z coordinate of this bright Spot. NOTE: the reported Z position is understood to be the one resulting from any performed post-processing correction procedures (i.e. drift correction, chromatic correction etc).
    -
    -
  * - **Chrom**
    - Chromosome name. Because BED (Browser Extensible Data) is the de facto exchange bioinformatics format for genomic data, the BED terminology was used here.
    - chr3, chrY, chr2_random
    -
  * - **Chrom_Start**
    - Start coordinate on the Chromosome for the sequence associated with this bright Spot (the first base on the chromosome is numbered 0). Because BED (Browser Extensible Data) is the de facto exchange bioinformatics format for genomic data, the BED terminology was used here.
    - 0
    -
  * - **Chrom_End**
    - Stop coordinate on the Chromosome for the sequence associated with this bright Spot. This position is non-inclusive, unlike Chrom_Start. Because BED (Browser Extensible Data) is the de facto exchange bioinformatics format for genomic data, the BED terminology was used here.
    - 1000
    -
  * - *Sub_Cell_ROI_ID*
    - If known, this field reports the unique identifier for a Region of Interest (ROI) that represents the boundaries of a sub-cellular structure a given Spot/Trace is associated with. Note: this is used to connect individual Spot/Traces that are part of the same ROI. It is also used to connect data in this table with any ROI specific measurements such as boundaries, intensities or volume, recorded in the corresponding ROI_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a Sub_Cell_ROI identified as part of this experiment.
  * - *Cell_ID*
    - If known, this field reports the unique identifier for the Cell a given Spot/Trace is associated with. Note: this is used to connect individual Spot/Traces that are part of the same Cell. It is also used to connect data in this table with any Cell specific measurements such as boundaries, intensities and volume, recorded in the corresponding Cell_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a Cell identified as part of this experiment.
  * - *Extra_Cell_ROI_ID*
    - If known, this field reports the unique identifier for a Region of Interest (ROI) that represents the boundaries of a extracellular structure (e.g., Tissue) a given Spot/Trace is associated with. Note: this is used to connect individual Spot/Traces that are part of the same ROI. It is also used to connect data in this table with any ROI specific measurements such as boundaries, intensities and volume, recorded in the corresponding ROI_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a extracellular structure ROI (e.g., Tissue) identified as part of this experiment.
