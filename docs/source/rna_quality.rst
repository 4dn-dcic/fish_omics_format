.. _rna_quality:

RNA Spot Quality table
==================

Requirement level: optional

Recommended: **Yes**

Namespace: *4dn_FOF-CT_rna_quality*

Summary
-------
This table is highly recommended and it is designed to provide quality
metrics for RNA Spots localization, information about the optical Channel
that was used to image a given RNA Spot, and various aberration corrections that might have been applied prior to localization (e.g., drift correction,
chromatic correction, etc.).

Because the metrics used to quantify RNA Spot detection accuracy and precision are not
trivial and lacking a widely shared consensus, the specific columns in this table remain largely
at the user's discretion and should be described with sufficient details
to ensure interpretation and reproducibility.

However, in order to align with existing `4DN-BINA-OME <https://doi.org/10.1038/s41592-021-01327-9>`_ Microscopy Metadata specifications, the use of specific column names and descriptions is **conditionally required** in case the described metric is reported. As an example, the column name **X_Drift** is conditionally required in case the user intends to report a comparison between the Observed vs. Expected (i.e., based on a fiducial reference) positions of a detected Spot.

The table is indexed by ``RNA_Spot_ID`` and each row corresponds to a RNA bright Spot. The order of all other columns (including those conditionally required) and of the rows are at the user's discretion.

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=4dn_FOF-CT_rna_quality``.

The header **MUST** contain a mandatory set of fields that describe any
algorithm that was used to produce/process data in this table.
In case more than one algorithm were used, please use the same set of fields for each of them.

The header **MUST** include a detailed description of each optional columns used.

.. tip:: The table **MUST** contain at least 1 Optional or Conditionally Required Column. 

.. csv-table::
  :file: tables/rna_quality_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions see :ref:`columns-reference-label`

As with all other RNA Spot Data tables in this format, each row corresponds to data associated with an individual RNA_Spot.

The first columns of this table are always ``Spot_ID``, ``Channel_Name``, ``Fluorophore_Name``.

This table **MUST** contain at least 1 Optional or Conditionally Required Column.

The content and order of all other columns is largely at user's discretion.
However, in order to align with existing `4DN-BINA-OME <https://doi.org/10.1038/s41592-021-01327-9>`_ Microscopy Metadata specifications, the use of specific column names and descriptions is **conditionally required** as indicated below. The order of the rows are at
the user's discretion.

.. csv-table::
  :file: tables/rna_quality_columns.csv
  :header-rows: 1
  
Example
-------
The only mandatory column in this table are ``RNA_Spot_ID``, ``Channel_Name``, and ``Fluorophore_Name``. 

All other columns are either *Conditionally required* or Optional. *Conditionally required* columns should be drawn from the list provided in the file header or MUST be defined by the user using a Header line starting with ``#^``. 

.. tip:: The optional columns in this example table are included for illustrative purposes only and describe a case in which the user is reporting the RNA Spot fit quality using metrics that align with existing `4DN-BINA-OME <https://doi.org/10.1038/s41592-021-01327-9>`_ Microscopy Metadata specifications. 

.. include:: examples/rna_quality
  :code:
