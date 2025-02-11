.. _subcell:

Sub-Cell ROI Data table
=======================

Requirement level: optional

Recommended: **Yes**

Namespace: *4dn_FOF-CT_subcell*

Summary
-------
This table is optionally used to document properties that are globally associated with individual sub-cellular ROIs that typically correspond to sub-nuclear features (e.g., Nucleoli, Nuclear Lamina, Chromosome Domains, PML bodies, etc.) identified as part of this experiment.

These are properties that are shared by all bright Spots and Traces that are associated with individual ROIs.

Each row in the table corresponds to a **different Subcell ROI** studied in the experiment and is identified by a unique ``Sub_Cell_ROI_ID`` that links the data reported in this table with data stored in one of the other tables
(e.g., :ref:`core`, :ref:`cell`, etc.).

As such, this table is mandatorily indexed by ``Sub_Cell_ROI_ID``.

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=4dn_FOF-CT_subcell``.

.. tip:: If applicable, the header **MUST** contain a mandatory set of fields that describe any Software tool that was used to produce/process data in this table. If more than one software tool was used, please repeat a set of Software-fields for describing each of them.

The header **MUST** include a detailed description of each optional columns used.

.. tip:: The table **MUST** contain at least 1 Optional Column. 

.. csv-table::
  :file: tables/subcell_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions see :ref:`columns-reference-label`

Each row corresponds to data associated with an individual subcellular ROI.

The first column of this table is always ``Sub_Cell_ROI_ID``.
This table **MUST** contain at least 1 Optional Column. 
The order of the other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/subcell_columns.csv
  :header-rows: 1

Example
-------
The only mandatory column in this table is ``Sub_Cell_ROI_ID``. All other columns are optional and must be defined by the user using a Header line starting with ``#^``.

.. tip:: The optional columns in this example table are included for illustrative purposes only and describe a case in which the user is reporting a **description** of the sub-cell ROI, the **marker** that was used to detect the sub-cell ROI, as well as the **volume** and the **intensity** of each ROI. 

.. include:: examples/subcell
  :code:

