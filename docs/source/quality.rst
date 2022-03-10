.. _quality:

Spot Quality Data table
=======================

Requirement level: recommended

Summary
-------

This table is highly recommended and it is designed to provide quality
metrics for the Spot localization, information about the optical Channel
that was used to image the Spot, and various aberration corrections that
have been applied prior to localization (e.g., drift correction,
chromatic correction, etc.).

Because the metrics used to quantify Spot detection accuracy and precision are not
trivial and lacking a widely shared consensus, the specific columns in this table remain largely
at the user’s discretion and should be described with sufficient details
to ensure interpretation and reproducibility.

However, in order to align with existing `4DN-BINA-OME <https://doi.org/10.1038/s41592-021-01327-9>`_ Microscopy Metadata specifications, the use of specific column names and descriptions is **conditionally required** in case the described metric is reported. As an example, the column name **X_Drift** is conditionally requred in case the user intends to report a comparison between the Observed vs. Expected (i.e., based on a fiducial reference) positions of a detected Spot.

The table is indexed by Spot_ID and each row corresponds to a DNA or RNA bright Spot. The order of all other columns (including those conditionally requried) and of the rows are at the user's discretion.

Example
-------
Spot fit quality

.. include:: examples/quality
  :code:

File Header
-----------
- The first line in the header is always "##FOF-CT_version=vX.X"
- The second line in the header is always "##Table_namespace=4dn_FOF-CT_quality"

The header MUST contain a mandatory set of fields that describe any
algorithm that was used to produce/process data in this table.
In case more than one algorithm were used, please use the same set of fields
for each of them.

The header should include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/quality_header.csv
  :header-rows: 1

Data Columns
------------
As with all other Spot Data tables in this format, each row corresponds to
data associated with an individual Spot.

The first column of this table is always Spot_ID.
The content and order of all other columns is largely at user's discretion.
However, in order to align with existing Microscopy Metadata specifications, the use of specific column names and descriptions is **conditionally required** as indicated below. The order of all other columns (including those conditionally requried) and of the rows are at
the user's discretion.

.. csv-table::
  :file: tables/quality_columns.csv
  :header-rows: 1
