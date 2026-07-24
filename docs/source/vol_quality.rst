.. _vol-quality:

SM Localization Quality table
==================

Requirement level: optional

Recommended: **Yes**

Namespace: *FOF-CT_vol_quality*

Summary
-------
This table is *recommended* and is designed to provide **quality metrics** for individual Single Molecule (SM) Localization events. 
It is **highly recommended** that all depositions contain *X_Loc_Precision*, *Y_Loc_Precision*, *Z_Loc_Precision*, and *PhotonCount* columns. Other columns can be included at the user's discretion. 

However, to align with existing `Light Microscopy Model (LiMi-Model) <https://doi.org/10.1038/s41592-021-01327-9>`_ of metadata specifications, the use of specific column names and descriptions is *conditionally required* in case the described metric is reported. As an example, the column name ``Raw_X`` is conditionally required in case the user intends to report the sub-pixel X coordinate of this SM Localization event, as determined before any performed post-processing correction procedures (i.e. drift correction, chromatic correction, etc.,).

The table is mandatorily indexed by ``Loc_ID`` and each row corresponds to an individual SM Localization event. The ``Loc_ID`` column must be immediately followed by ``Channel`` and ``Fluor``. All other columns, including conditionally required ones, may be ordered at the user's discretion, as may the rows.

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions, see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=FOF-CT_vol_quality``.

.. tip:: The header **MUST** contain a mandatory set of fields that describe any Software tool that was used to produce/process data in this table. If more than one software tool was used, please repeat a set of Software fields for describing each of them.

The header **MUST** include a detailed description of each optional column used. 

.. csv-table::
  :file: tables/vol_quality_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions, see :ref:`columns-reference-label`

Each row corresponds to data associated with an individual SM Localization event. Accordingly, the first columns of this table are always ``Loc_ID``, ``Channel``, and ``Fluor``.

The content and order of all other columns are largely at the user's discretion.

However, it is highly recommended that all depositions contain *X_Loc_Precision*, *Y_Loc_Precision*, *Z_Loc_Precision*, and *PhotonCount* columns. In addition, to align with existing `Light Microscopy Model (LiMi-Model) <https://doi.org/10.1038/s41592-021-01327-9>`_ metadata specifications, the use of specific column names and descriptions is *conditionally required* as indicated below. The order of the rows is at the user's discretion.

.. csv-table::
  :file: tables/vol_quality_columns.csv
  :header-rows: 1

Example
-------
The only mandatory columns in this table are ``Loc_ID``, ``Channel``, and ``Fluor``.

The following columns are **highly recommended**: ``X_Loc_Precision``, ``Y_Loc_Precision``, ``Z_Loc_Precision``, and ``PhotonCount``.

All other columns are either *Conditionally required* or Optional. *Conditionally required* columns should be drawn from the list provided in the file header. In all cases, all Columns MUST be defined and described by the user using a Header line starting with ``#^``. 

.. tip:: The optional columns in this example table are included for illustrative purposes only using metrics that align with existing `Light Microscopy Model (LiMi-Model) <https://doi.org/10.1038/s41592-021-01327-9>`_ metadata specifications. 

.. include:: examples/quality
  :code:

