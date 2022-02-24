Cell Data table (optional)
==========================

Summary
-------

*(scalar data only; each row is a cell)*

This table is a complementary table used to document properties that are
globally associated with individual Cells (e.g., cell size, cell volume,
cell type). These are properties that are shared by all bright Spots and
Traces that belong to an individual Cell. Each row in the table
corresponds to a different Cell studied in the experiment and is
identified by a unique Cell_ID that links the data reported in this
table with data stored in one of the other tables (i.e.,
DNA_Spot/Trace_Data, Global_Trace_Data, etc.,). The header should note
the coordinate system used for the cell x/y/z centroid.

Example
-------

.. code::

  ##FOF-CT_version=v0.1
  ##XYZ_unit=micron
  ##Extra_Cell_ROI_type=Organoid
  #^RNA_A_nr: the number of detected bright Spots corresponding to RNA transcript A detected in this Cell, see also RNA Spot Data table
  #^RNA_B_nr: the number of detected bright Spots corresponding to RNA transcript B detected in this Cell, see also RNA Spot Data table
  #^cell_cycle_state: the Cell Cycle state in which this Cell is found as measured with the Fucci system. This column can contain one of the following values: G1, S, G2 or M.
  #^cell_volume: the volume of this Cell expressed in micron^3.
  #additional_tables: DNA_Spot/Trace_Data.csv, RNA_Spot_Data.csv, Global_Trace_Data.csv
  #columns=(Cell_ID, Extra_Cell_ROI_ID, RNA_A_nr, RNA_B_nr, cell_cycle_state, cell_volume)
  1, 1, 10, 22, 1041.5, 12354.24, G1, 13453
  2, 1, 0, 11, 2041.3, 32234.24, G2, 35545
  3, 2, 10, 33, 101.5, 12354.24, S, 10010
  4, 3, 0, 44, 201.1, 32234.24, M, 25340

File Header
-----------

.. list-table::
  :header-rows: 1

  * - Name
    - Description
    - Example
    - Conditional requirement conditions
  * - **##FOF-CT_version=**
    - Version of the FOF format used in this case.
    -
    - v0.1
  * - **##Table_namespace=**
    - 4dn_FOF-CT_cell
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
  * - *#Software_Title:*
    - The name of the Software(s) that were used in this case for localizing individual FISH-omics bright Spots and/or to produce three-dimensional (3D) polymeric chromatin Traces.
    - ChrTracer3
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - *#Software_Type:*
    - The type of this Software. Allowed values: SpotLoc, Tracing, SpotLoc+Tracing, Segmentation, QC, Other
    - SpotLoc+Tracing
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - *#Software_Authors:*
    - The Name(s) of the individual Author(s) of this Software. In case there are more than one Authors, individual names should be listed as follows, Doe, John; Smith, Jane; etc,.
    - Mateo, LJ; Sinnott-Armstrong, N; Boettiger, AN
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - *#Software_Description:*
    - A free-text, description of this Software. This description should provide a detailed understanding of the algortithm and of the analysis parameters that were used, in order to guarantee interpretation and reproducibility.
    - ChrTracer3 software was developed for analysis of raw DNA labeled images. As an input, it takes an.xlsx table containing information and folder names of the DNA experiment. As an output, it returns tab delimited.txt ﬁles with drift-corrected x, y, z positions for all labeled barcodes. These can be used directly to calculate the nm scale distances between all pairs of labeled loci. The current version of the software as of this writing is ChrTracer3.
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - *#Software_Repository:*
    - The URL of any repository or archive where the Software executable release can be obtained.
    - https://github.com/BoettigerLab/ORCA-public
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - *#Software_PreferredCitationID:*
    - The Unique Identifier for the preferred/primary publication describing this Software. Examples include, Digital Object Identifier (DOI), PubMed Central Identifier (PMCID), ArXiv.org ID etc,.
    - https://doi.org/10.1038/s41596-020-00478-x
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - **#additional_tables:**
    - list of the additional tables being submitted. Note: use a comma to separate each table name from the next.
    - DNA_Spot/Trace_Data.csv, RNA_Spot_Data.csv, Spot_Quality_Data.csv, Spot_Biological_Data.csv, Global_Trace_Data.csv
    -
  * - #Intensity_measurement_method
    - If relevant, the method that was used to performed intensity measurements. In particular, sufficient information should be provided to document how digital intensity signals were converted in Photon conunts.
    - Spot centroid intensity.
    - Conditional requirement: this MUST be reported if any intensity metrics are reported.
  * - #^optional_column_1:
    - optional column 1 description
    -
    -
  * - #^optional_column_2:
    - optional column 2 description
    -
    -
  * - #^optional_column_3:
    - optional column 3 description
    -
    -
  * - *##Extra_Cell_ROI_type=*
    - This field records the type of extracellular structure ROIs used in this table represent. The value utilized should belong to this list: Tissue, Organoid, Other
    - Tissue
    - Conditional requirement: this MUST be reported in any Super_Cell ROI is idenfied as part of this experiment.
  * - *##XYZ_unit=*
    - If relevant, the unit used to represent XYZ locations or distances in this table. Note: use micron (instead of µm) to avoid problem with special, Greek symbols. Other allowed values are: nm, mm etc.
    - micron
    - Conditional requirement: this MUST be reported if any locations metrics are reported.
  * - *##time_unit=*
    - If relevant, the unit used to represent a time interval. Note: use “sec” for seconds, “msec” for milliseconds, “min” for minutes, and “hr” for hours.
    - sec
    - Conditional requirement: this MUST be reported if any time metrics are reported.
  * - *##intensity_unit=*
    - If relevant, the unit used to represent intensity measurements.
    - a.u.
    - Conditional requirement: this MUST be reported if any intensity metrics are reported.
  * - **##columns=**
    - list of the data column headers used in the table. Note: enclose the column headers and use a comma to separate each header name from the next.
    - (Spot_ID, X, Y, Z)
    -

Data Columns
------------

.. list-table::
  :header-rows: 1

  * - Name
    - Description
    - Example
    - Conditional requirement conditions
  * - **Cell_ID**
    - This fields reports the unique identifier for Region of Interest (ROI) that represent the boundaries of a Cell identified as part of this experiment. Note: this is used to connect individual Spots or Traces that are part of the same Cell.
    - 1
    -
  * - *Extra_Cell_ROI_ID*
    - In case multiple Cells are localized within a given extracellular structure (e.g., Tissue) Region of Interest (ROI), this fields reports the unique identifier that allows to identify such as ROI. Note: this is used to connect individual Cells that are part of the same extracellular ROI.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with an extracellular ROI identified as part of this experiment.
  * - optional_column_1
    -
    -
    -
  * - optional_column_2
    -
    -
    -
  * - optional_column_3
    -
    -
    -
