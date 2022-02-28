.. _spot_bio:

Spot Biological Data table (recommended)
========================================

.. contents::

Summary
-------

This table is highly recommended and it is designed to store and share
biological properties associated with individual Spots (e.g., distance
from the nuclear lamina (NL) or the nuclear pore complex (NPC), etc.; Su
et al 2020 Cell and Takei et al 2021 Nature) identified as part of this
experiment. In the absence of a consensus regarding biological
properties to be recorded in association with individual bright Spots or
Traces, the specific columns in this table remain at the user’s
discretion and should be described with sufficient details to ensure
interpretation and reproducibility.

This table is mandatorily indexed by Spot_ID.

Example
-------

.. include:: examples/spot_bio
  :code:

File Header
-----------

The first line in the header is always "##FOF-CT_version=vX.X"

This Table can be indexed mandatorily by Spot_ID.

The header MUST to contain a mandatory set of fields that describe any
algorithm that was used to produce/process data in this table.
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
    - 4dn_FOF-CT_bio
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
  * - **#Software_PreferredCitationID:**
    - The Unique Identifier for the preferred/primary publication describing this Software. Examples include, Digital Object Identifier (DOI), PubMed Central Identifier (PMCID), ArXiv.org ID etc,.
    - https://doi.org/10.1038/s41596-020-00478-x
    - Conditional requirement: this MUST be reported any time a software is used to produce data associated with this table.
  * - **#additional_tables:**
    - list of the additional tables being submitted. Note: use a comma to separate each table name from the next.
    - DNA_Spot/Trace_Data.csv, RNA_Spot_Data.csv, Spot_Quality_Data.csv, Gobal_Trace_Data.csv, Global_Cell_Data.csv
    -
  * - *#Intensity_measurement_method*
    - If relevant, the method that was used to performed intensity measurements. In particular, sufficient information should be provided to document how digital intensity signals were converted in Photon conunts.
    - Spot centroid intensity.
    - Conditional requirement: this MUST be reported if any intensity metrics are reported.
  * - #^optional_column_1:
    -
    -
    -
  * - #^optional_column_2:
    -
    -
    -
  * - #^optional_column_3:
    -
    -
    -
  * - **##XYZ_unit=**
    - The unit used to represent XYZ locations or distances in this table. Note: use micron (instead of µm) to avoid problem with special, Greek symbols. Other allowed values are: nm, mm etc.
    - micron
    -
  * - *##time_unit=*
    - If relevant, the unit used to represent a time interval. Note: use "sec" for seconds, "msec" for milliseconds, "min" for minutes, and "hr" for hours.
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

Each row corresponds to data associated with an individual Spot or Trace.

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
  * - *Spot_ID*
    - A unique identifier for this bright Spot.
    - 1
    -
  * - optional_column_1:
    -
    -
    -
  * - optional_column_2:
    -
    -
    -
  * - optional_column_3:
    -
    -
    -
