.. _rna_bio:

RNA Spot Biological Data table
==========================

Requirement level: optional
Recommended: Yes

Summary
-------
This table is highly recommended and it is designed to store and share
biological properties associated with individual Spots (e.g., distance
from the nuclear lamina (NL) or the nuclear pore complex (NPC), etc.; Su
et al 2020 Cell and Takei et al 2021 Nature) identified as part of this
experiment. In the absence of a consensus regarding biological
properties to be recorded in association with individual bright Spots,
the specific columns in this table remain at the user's
discretion and should be described with sufficient details to ensure
interpretation and reproducibility.

This table is mandatorily indexed by RNA_Spot_ID.

File Header
-----------
- The first line in the header is always ``##FOF-CT_version=vX.X``.
- The second line in the header is always ``##Table_namespace=4dn_FOF-CT_mapping``.

The header MUST contain a mandatory set of fields that describe any algorithm that was used to produce/process data in this table. In case more than one algorithm were used, please use the same set of fields for each of them.

The header MUST include a detailed description of each optional columns used. 

The table MUST contain at least 1 optional column. 

.. csv-table::
  :file: tables/bio_header.csv
  :header-rows: 1

Data Columns
------------
Each row corresponds to data associated with an individual RNA Spot.
The first column is always **RNA_Spot_ID**.
The order of the other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/bio_columns.csv
  :header-rows: 1

Example
-------
The only mandatory column in this table is ``RNA_Spot_ID``. All other columns are optional and must be defined by the user using a Header line starting with ``#^``. 

.. tip:: the Optional columns in this example table are included for illustrative purposes only and describe a case in which the user is reporting the **distance** of RNA spots from two different nuclear landmarks.

.. include:: examples/bio
  :code:

