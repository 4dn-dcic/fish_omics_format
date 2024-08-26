.. _subcell:

Sub-Cell ROI Data table
=======================

Requirement level: optional
Recommended: Yes

Summary
-------
This table is optionally used to document properties that are globally associated with individual sub-cellular ROIs that typically correspond to sub-nuclear features (e.g., Nucleoli, Nuclear Lamina, Chromosome Domains, PML bodies, etc.) identified as part of this experiment.
These are properties that are shared by all bright Spots and Traces that are associated with individual ROIs.
Each row in the table corresponds to a different Subcell ROI studied in the
experiment and is identified by a unique **Sub_Cell_ROI_ID** that links the data reported in this table with data stored in one of the other tables
(e.g., :ref:`core`, :ref:`cell`, etc.).

File Header
-----------
- For full instructions see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_version=vX.X``.
- The second line in the header is always ``##Table_namespace=4dn_FOF-CT_mapping``.

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

.. tip:: the Optional columns in this example table are included for illustrative purposes only and describe a case in which the user is reporting a **description** of the sub-cell ROI, the **marker** that was used to detect the sub-cell ROI, as well as the **volume** and the **intensity** of each ROI. 

.. include:: examples/subcell
  :code:

