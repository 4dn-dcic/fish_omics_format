DNA-Spot/Trace Data core table (required)
-----------------------------------------

Summary
~~~~~~~

*(each line corresponds to an individual DNA bright Spot along a
polymeric Trace)*

The column properties are as follows:

**Spot_ID** -- a unique identifier associated with a given spot (each
row). Recommended practice rather than relying on row index implicitly
for identity.

**Trace_ID** -- unique identifier common to all spots that are part of a
common trace (i.e. part of the same chromosome). Used to link individual
spots into a polymer. Also used to connect these data with any
measurement that is associated with individual Traces (i.e., nascent RNA
expression) and is recorded in the corresponding Trace Data Table.

**x, y, z** -- 3 columns, recording the 3D position of the spot, after
all analysis (i.e. after drift correction, chromatic correction etc).
The units remind the user of the approved convention.

**Chrom, Chrom_Start, Chrom_End**: 3 columns, in Bed format, to
interface easily with genome browser

Cell_ID -- unique identifier common to all spots that are part of a
common cell (diploid cells will generally have 2 traceIDs per cellID).
Also used to link these data with any cell specific data, such as mRNA
levels or cell volume, recorded in the Cell Table. If cell segmentation
was not performed, this column may be left with NA.

Sub_Cell_ROI_ID, Extra_Cell_ROI_ID -- Additional identifiers used to
link these data to other tables may be appended as additional columns if
needed. All other spot properties should be kept in the optional
additional table DNA Spot Properties, indexed by Spot_ID.

Example
~~~~~~~

.. code::

  ##FOF-CT_version=v0.1
  ##genome_assembly=GRCh38
  ##XYZ_unit=micron
  #Software_Title: ChrTracer3
  #Software_Type: SpotLoc+Tracing
  #Software_Authors: Mateo, LJ; Sinnott-Armstrong, N; Boettiger, AN
  #Software_Description: ChrTracer3 software was developed for analysis of raw DNA labeled images. As an input, it takes an.xlsx table containing information and folder names of the DNA experiment. As an output, it returns tab delimited.txt ﬁles with drift-corrected x, y, z positions for all labeled barcodes. These can be used directly to calculate the nm scale distances between all pairs of labeled loci. The current version of the software as of this writing is ChrTracer3.
  #Software_Repository: https://github.com/BoettigerLab/ORCA-public
  #Software_PreferredCitationID: https://doi.org/10.1038/s41596-020-00478-x
  #lab_name: Nobel
  #experimenter_name: John Doe
  #experimenter_contact: john.doe@email.com
  #additional_tables: DNA_Spot_Quality.csv, RNA_Spot.csv, RNA_Spot_Qualtiy.csv, Trace_Data.csv, Cell_Data.csv
  ##columns=(Spot_ID, Trace_ID, x, y, z, Chrom, Chrom_Start, Chrom_End, Cell_ID)
  1, 1, 14.43, 41.43, 1.23, chr1, 0001, 1000, 1
  2, 1, 14.83, 41.83, 1.83, chr1, 1001, 2000, 1
  3, 1, 15.83, 42.83, 1.33, chr1, 2001, 3000, 1
  4, 2, 20.43, 50.43, 1.23, chr1, 0002, 2000, 1
  5, 2, 21.83, 60.83, 1.83, chr1, 1002, 3000, 1

File Header
~~~~~~~~~~~

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
~~~~~~~~~~~~

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
    - In case multiple DNA Spots are connected to form 3D polymer traces of chromatin fibers (suh as in ORCA; https://doi.org/10.1038/s41596-020-00478-x), this fields reports a unique identifier for the DNA trace the Spot belongs to. Note: this is used to connect Spots that are part of the same polymeric Trace. It is also used to connect data in this table with any Trace specific measurements such as nascent RNA expression, recorded in the corresponding Trace_Dat table.
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
    - Stop coordinate on the Chromosome for the sequence associated with this bright Spot. This position is non-inclusive, unlike chromStart. Because BED (Browser Extensible Data) is the de facto exchange bioinformatics format for genomic data, the BED terminology was used here.
    - 1000
    -
  * - *Sub_Cell_ROI_ID*
    - If known, this fields reports the unique identifier for a Region of Interest (ROI) that represents the boundaries of a sub-cellular structure a given Spot/Trace is associated with. Note: this is used to connect individual Spot/Traces that are part of the same ROI. It is also used to connect data in this table with any ROI specific measurements such as boundaries, intensities or volume, recorded in the corresponding ROI_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a Sub_Cell_ROI identified as part of this experiment.
  * - *Cell_ID*
    - If known, this fields reports the unique identifier for the Cell a given Spot/Trace is associated with. Note: this is used to connect individual Spot/Traces that are part of the same Cell. It is also used to connect data in this table with any Cell specific measurements such as boundaries, intensities and volume, recorded in the corresponding Cell_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a Cell identified as part of this experiment.
  * - *Extra_Cell_ROI_ID*
    - If known, this fields reports the unique identifier for a Region of Interest (ROI) that represents the boundaries of a extracellular structure (e.g., Tissue) a given Spot/Trace is associated with. Note: this is used to connect individual Spot/Traces that are part of the same ROI. It is also used to connect data in this table with any ROI specific measurements such as boundaries, intensities and volume, recorded in the corresponding ROI_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a extracellular structure ROI (e.g., Tissue) identified as part of this experiment.
