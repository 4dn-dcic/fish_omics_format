.. _extracell:

Extra-Cell ROI Data table
=========================

Requirement level: optional
Recommended: Yes

Summary
-------
This table is optionally used to document properties (i.e., volume, mean fluorescence
intensity) that are globally associated with individual extracellular
structures (e.g., Tissue, Organoid, etc.) Regions of Interest (ROI) identified as part of this experiment.

These are properties that are shared by all bright Spots, Traces and Cells
that belong to an individual extracellular structure identified as part of
this study.
Each row in the table corresponds to a different extracellular structure
studied in the experiment and is identified by a unique **Extra_Cell_ROI_ID** that
links the data reported in this table with data stored in one of the
other tables (e.g., :ref:`core`, :ref:`rna`, etc.).

File Header
-----------
- The first line in the header is always ``##FOF-CT_version=vX.X``.
- The second line in the header is always ``##Table_namespace=4dn_FOF-CT_mapping``.

The header MUST include a detailed description of each Optional Columns used. 

.. tip:: The table MUST contain at least 1 Optional Column. 

.. csv-table::
  :file: tables/extracell_header.csv
  :header-rows: 1

Data Columns
------------
Each row corresponds to data associated with an individual extracellular ROI.

The first column of this table is always ``Extra_Cell_ROI_ID``.
This table has to contain at least 1 Optional Column. 
The order of the other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/extracell_columns.csv
  :header-rows: 1

Example
-------
The only mandatory column in this table is ``Extra_Cell_ROI_ID``. All other columns are optional and must be defined by the user using a Header line starting with ``#^``.

.. tip:: the Optional columns in this example table are included for illustrative purposes only and describe a case in which the user is reporting the **number** of specific cells are detected within individual extracellular ROIs as well as the **volume** of each ROI. 

.. include:: examples/extracell
  :code:
