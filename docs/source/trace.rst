Trace Data table (optional)
===========================

.. contents::

Summary
-------

This table is used to document properties that are globally associated
with individual Traces rather than individual bright Spots (e.g.,
Physical coordinates, RNA transcription, or Allele). These are
properties that are shared by all bright Spots that constitute a Trace.
Each row in the table corresponds to an individual Trace and is
identified by a unique Trace_ID that links the data reported in this
table with data stored in one of the other tables (i.e.,
DNA_Spot/Trace_Data, Global_Cell_Data, etc.,).

Example
-------

.. code::

  ##FOF-CT_version=v0.1
  ##XYZ_unit=micron
  ##intensity_unit=a.u.
  #^allele: This field records the Allele to which this Trace was mapped. This can be one of the following values: BL6, CAST.
  #^RNA_A_intensity: This records the intensity of the nascent RNA A expression signal associated with this Trace.
  #^NL_distance: This field records the distance of this Trace to the Nuclear Lamina.
  #additional_tables: DNA_Spot_Data.csv, Cell_Data.csv
  #columns=(Trace_ID, allele, RNA_A_int, NL_distance)
  1, BL6, 43253, 0.235
  2, CAST, 40001, 0.563
  3, BL6, 1000, 0.135
  4, CAST, 1500, 0.633

File Header
-----------

.. list-table::
  :header-rows: 1

  * - Name
    - Description
    - Example
    - Conditional requirement conditions
  * - ##FOF-CT_version=
    - Version of the FOF format used in this case.
    - v0.1
    -
  * - ##Table_namespace=
    - 4dn_FOF-CT_trace
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
  * - #experimenter_contact:
    - email address of the person performing the experiment.
    - john.doe@email.com
    -
  * - #description:
    - A free-text, description of the experiment and of the data recorded in this table. This description should provide a clear understanding of the process utilized to produce the data and contain sufficient details to ensure interpretation and reproducibility.
    -
    -
  * - #Software_Title:
    - The name of the Software(s) that were used in this case for localizing individual FISH-omics bright Spots and/or to produce three-dimensional (3D) polymeric chromatin Traces.
    - ChrTracer3
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - #Software_Type:
    - The type of this Software. Allowed values: SpotLoc, Tracing, SpotLoc+Tracing, Segmentation, QC, Other
    - SpotLoc+Tracing
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - #Software_Authors:
    - The Name(s) of the individual Author(s) of this Software. In case there are more than one Authors, individual names should be listed as follows, Doe, John; Smith, Jane; etc,.
    - Mateo, LJ; Sinnott-Armstrong, N; Boettiger, AN
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - #Software_Description:
    - A free-text, description of this Software. This description should provide a detailed understanding of the algortithm and of the analysis parameters that were used, in order to guarantee interpretation and reproducibility.
    - ChrTracer3 software was developed for analysis of raw DNA labeled images. As an input, it takes an.xlsx table containing information and folder names of the DNA experiment. As an output, it returns tab delimited.txt ﬁles with drift-corrected x, y, z positions for all labeled barcodes. These can be used directly to calculate the nm scale distances between all pairs of labeled loci. The current version of the software as of this writing is ChrTracer3.
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - #Software_Repository:
    - The URL of any repository or archive where the Software executable release can be obtained.
    - https://github.com/BoettigerLab/ORCA-public
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - #Software_PreferredCitationID:
    - The Unique Identifier for the preferred/primary publication describing this Software. Examples include, Digital Object Identifier (DOI), PubMed Central Identifier (PMCID), ArXiv.org ID etc,.
    - https://doi.org/10.1038/s41596-020-00478-x
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - #additional_tables:
    - list of the additional tables being submitted. Note: use a comma to separate each table name from the next.
    - DNA_Spot/Trace_Data.csv, RNA_Spot_Data.csv, Spot_Quality_Data.csv, Spot_Biological_Data.csv, Global_Cell_Data.csv
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
  * - ##XYZ_unit=
    - If relevant, the unit used to represent XYZ locations or distances in this table. Note: use micron (instead of µm) to avoid problem with special, Greek symbols. Other allowed values are: nm, mm etc.
    - micron
    - Conditional requirement: this MUST be reported if any locations metrics are reported.
  * - ##time_unit=
    - If relevant, the unit used to represent a time interval. Note: use “sec” for seconds, “msec” for milliseconds, “min” for minutes, and “hr” for hours.
    - sec
    - Conditional requirement: this MUST be reported if any time metrics are reported.
  * - ##intensity_unit=
    - If relevant, the unit used to represent intensity measurements.
    - a.u.
    - Conditional requirement: this MUST be reported if any intensity metrics are reported.
  * - ##columns=
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
  * - Trace_ID
    - This fields reports the unique identifier for a DNA Trace identified as part of this experiment. Note: this is used to connect data in this table with a given Trace and with Trace specific measurements as recorded in the corresponding Global_Trace_Data_Table.
    - 1
    -
  * - Sub_Cell_ROI_ID
    - If known, this fields reports the unique identifier for a Region of Interest (ROI) that represents the boundaries of a sub-cellular structure a given Spot or Trace is associated with. Note: this is used to connect individual Spot or Traces that are part of the same ROI. It is also used to connect data in this table with any ROI specific measurements such as boundaries, intensities or volume, recorded in the corresponding ROI_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a Sub_Cell_ROI identified as part of this experiment.
  * - Cell_ID
    - If known, this fields reports the unique identifier for the Cell a given Spot or Trace is associated with. Note: this is used to connect individual Spot or Traces that are part of the same Cell. It is also used to connect data in this table with any Cell specific measurements such as boundaries, intensities and volume, recorded in the corresponding Cell_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a Cell identified as part of this experiment.
  * - Extra_Cell_ROI_ID
    - If known, this fields reports the unique identifier for a Region of Interest (ROI) that represents the boundaries of a extracellular structure (e.g., Tissue) a given Spot or Trace is associated with. Note: this is used to connect individual Spot or Traces that are part of the same ROI. It is also used to connect data in this table with any ROI specific measurements such as boundaries, intensities and volume, recorded in the corresponding ROI_Data_Table.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with a extracellular structure ROI (e.g., Tissue) identified as part of this experiment.
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
