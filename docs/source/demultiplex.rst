Spot Demultiplexing table (optional)
====================================

.. contents::

Summary
-------

This table is optional and is designed to provide additional Spot
properties that are not recorded in the mandatory DNA Spot/Trace Data
table, the main RNA Spot Data table or the other recommended tables. In
the absence of a consensus, the specific columns in this table remain at
the user’s discretion and should be described with sufficient details to
ensure interpretation and reproducibility. In the case of multiplexed
FISH experiments (i.e., MERFISH) in which the final localization of RNA
molecule results from combining multiple detection events (e.g., by
combining Spots detected in separate images), the underlying raw data
can be recorded in corresponding RNA Spot quality tables as shown in the
examples below.

This table can be indexed by Localization_ID.

Example
-------
DNA spots detected with multiplexed barcodes

.. code::

  # loc_ID - unique ID for the individual localization
  # Spot_ID - index from DNA spot table. Localizations not assigned to a spot are denoted NA.
  # x - fitted x position of the the individual localization event / readout
  # y - fitted y position of the individual localization event
  # z - fitted z position of the individual localization event
  # hyb - the labeling round in which this localization occurred
  # fluor - the fluorescent channel in which this localization was detected
  # brightness - the photon count for this localization event
  # fit_quality - the quality of fit for this localization, on a relative scale of 0-1.
  #
  loc_ID Spot_ID x y z hyb fluor brightness fit_quality
  1 1 2342 2354 545 2 cy3 1003 .83
  2 1 2342 2354 545 2 cy5 2000 .93
  3 1 2342 2354 545 3 cy5 1233 .85
  4 2 3345 5432 654 3 cy3 2324 .95
  5 2 3345 5432 654 3 cy5 2324 .95
  6 NA 4345 432 100 4 cy3 2324 .95
  7 2 3345 5432 654 4 cy3 2324 .95

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
    - v0.1
    -
  * - **##Table_namespace=**
    - 4dn_FOF-CT_demultiplex
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
    - DNA_Spot/Trace_Data.csv, RNA_Spot_Data.csv, Spot_Biological_Data.csv, Gobal_Trace_Data.csv, Global_Cell_Data.csv
    -
  * - *#Intensity_measurement_method*
    - If relevant, the method that was used to performed intensity measurements. In particular, sufficient information should be provided to document how digital intensity signals were converted in Photon conunts.
    - Spot centroid intensity.
    - Conditional requirement: this MUST be reported if any intensity metrics are reported.
  * - *##XYZ_unit=*
    - The unit used to represent XYZ locations or distances in this table. Note: use micron (instead of µm) to avoid problem with special, Greek symbols. Other allowed values are: nm, mm etc.
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
  * - *Spot_ID*
    - A unique identifier for this bright Spot.
    - 1
    -
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
