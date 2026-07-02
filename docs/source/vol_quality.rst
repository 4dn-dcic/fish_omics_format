.. _vol-quality:

Localization Quality table
==================

Requirement level: optional

Recommended: **Yes**

Namespace: *4dn_FOF-CT_vol_quality*

Summary
-------
This table is *recommended* and is designed to provide **quality metrics** for individual Single Molecule (SM) localization events. 
It is highly recommended that all depositions contain *X_Loc_Precision*, *Y_Loc_Precision*, *Z_Loc_Precision*, *PhotonCount*, and *Goodness_of_Fit* columns. Other columns can be included at the user's discretion. 
In all cases, all columns **MUST** be described in the header with sufficient details to ensure interpretation and reproducibility.

However, to align with existing `Light Microscopy Model (LiMi-Model) <https://doi.org/10.1038/s41592-021-01327-9>`_ of metadata specifications, the use of specific column names and descriptions is *conditionally required* in case the described metric is reported. As an example, the column name ``X_Drift`` is conditionally required in case the user intends to report a comparison between the Observed vs. Expected (i.e., based on a fiducial reference) positions of a detected Spot.

The table is mandatorily indexed by ``Localization_ID`` and each row corresponds to an individual SM localization event. The order of all other columns (including those conditionally required) and of the rows is at the user's discretion.

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions, see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=4dn_FOF-CT_vol-quality``.

.. tip:: The header **MUST** contain a mandatory set of fields that describe any Software tool that was used to produce/process data in this table. If more than one software tool was used, please repeat a set of Software fields for describing each of them.

The header **MUST** include a detailed description of each optional column used. 

.. csv-table::
  :file: tables/quality_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions see :ref:`columns-reference-label`

As with all other Spot Data tables in this format, each row corresponds to
data associated with an individual SM localization event.

The first columns of this table are always ``Spot_ID``, ``Channel_Name``, and ``Fluorophore_Name``.

The content and order of all other columns is largely at the user's discretion.
However, to align with existing `Light Microscopy Model (LiMi-Model) <https://doi.org/10.1038/s41592-021-01327-9>`_ metadata specifications, the use of specific column names and descriptions is *conditionally required* as indicated below. The order of the rows is at the user's discretion.

.. csv-table::
  :file: tables/quality_columns.csv
  :header-rows: 1

Example
-------
This table has only one mandatory column: ``Localization_ID``.

The following columns are **highly recommended**: ``X_Loc_Precision``, ``Y_Loc_Precision``, ``Z_Loc_Precision``, ``PhotonCount``, and ``Goodness_of_Fit``.

All other columns are either *Conditionally required* or Optional. *Conditionally required* columns should be drawn from the list provided in the file header. In all cases, all Columns MUST be defined and described by the user using a Header line starting with ``#^``. 

.. tip:: The optional columns in this example table are included for illustrative purposes only and describe a case in which the user is reporting the Spot fit quality using metrics that align with existing `Light Microscopy Model (LiMi-Model) <https://doi.org/10.1038/s41592-021-01327-9>`_ metadata specifications. 

.. include:: examples/quality
  :code:

