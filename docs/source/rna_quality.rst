.. _rna_quality:

RNA Spot Quality table
======================

Requirement level: optional

Recommended: **Yes**

Namespace: *4dn_FOF-CT_rna_quality*

Summary
-------
This table is highly recommended, and it is designed to provide quality metrics for RNA bright Spots, information about the optical Channel that was used to image a given RNA bright Spot, and various aberration corrections that might have been applied before identification (e.g., drift correction, chromatic correction, etc.).

Because the metrics used to quantify RNA bright Spot detection accuracy and precision are not trivial and lacking a widely shared consensus, the specific columns in this table remain largely at the user's discretion and should be described with sufficient details to ensure interpretation and reproducibility.

However, to align with existing `Light Microscopy Model (LiMi-Model) <https://doi.org/10.1038/s41592-021-01327-9>`_ metadata specifications, the use of specific column names and descriptions is **conditionally required** in case the described metric is reported. As an example, the column name **X_Drift** is conditionally required in case the user intends to report a comparison between the Observed vs. Expected (i.e., based on a fiducial reference) positions of a detected Spot.

The table is indexed by ``RNA_Spot_ID`` and each row corresponds to an RNA bright Spot. The ``RNA_Spot_ID`` column must be immediately followed by ``Channel`` and ``Fluor``. All other columns, including conditionally required and optional (Optional Column, OC) ones, must follow the three required columns and may be ordered at the user's discretion, as may the rows.

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=4dn_FOF-CT_rna_quality``.

.. tip:: If applicable, the header **MUST** contain a mandatory set of fields that describe any Software tool that was used to produce/process data in this table. If more than one software tool was used, please repeat a set of Software fields for describing each of them.

The header **MUST** include a detailed description of each Optional Column (OC) used.

.. tip:: The table **MUST** contain at least 1 Optional or Conditionally Required Column. 

.. note:: The columns below marked *conditionally required* (e.g., ``Raw_X``, ``X_Drift``, ``X_Loc_Precision``) are reserved names: their use is optional, but if the corresponding metric is reported, this exact column name **MUST** be used. All other ``#^`` columns are free-form — see :ref:`headers-reference-label` for the full distinction.

.. csv-table::
  :file: tables/rna_quality_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions see :ref:`columns-reference-label`

As with all other RNA Spot Data tables in this format, each row corresponds to data associated with an individual RNA_Spot.

The first columns of this table are always ``RNA_Spot_ID``, ``Channel``, ``Fluor``.

This table **MUST** contain at least 1 Optional or Conditionally Required Column.

The content and order of all other columns is largely at the user's discretion.
However, to align with existing `LiMi-Model <https://doi.org/10.1038/s41592-021-01327-9>`_ metadata specifications, the use of specific column names and descriptions is **conditionally required** as indicated below. The order of the rows is at the user's discretion.

.. csv-table::
  :file: tables/rna_quality_columns.csv
  :header-rows: 1
  
Example
-------
The only mandatory columns in this table are ``RNA_Spot_ID``, ``Channel``, and ``Fluor``. 

All other columns are either *Conditionally required* or Optional. *Conditionally required* columns should be drawn from the list provided in the file header or MUST be defined by the user using a Header line starting with ``#^``. 

.. tip:: The optional columns in this example table are included for illustrative purposes only and describe a case in which the user is reporting the RNA Spot fit quality using metrics that align with existing `LiMi-Model <https://doi.org/10.1038/s41592-021-01327-9>`_ of metadata specifications. 

.. include:: examples/rna_quality
  :code:
