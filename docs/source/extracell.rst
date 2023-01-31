.. _extracell:

Extra-Cell ROI Data table
=========================

Requirement level: conditionally required

Summary
-------
This table is used to document properties (i.e., volume, mean fluorescence
intensity) that are globally associated with individual extracellular
structures (e.g., Tissue, Organoid, etc.) Regions of Interest (ROI),
and it is required in the case extracellular ROI segmentation data was
collected as part of this experiment.
These are properties that are shared by all bright Spots, Traces and Cells
that belong to an individual extracellular structure identified as part of
this study.
Each row in the table corresponds to a different extracellular structure
studied in the experiment and is identified by a unique **Extra_Cell_ROI_ID** that
links the data reported in this table with data stored in one of the
other tables (e.g., :ref:`core`, :ref:`rna`, etc.).

Example
-------
.. include:: examples/extracell
  :code:

File Header
-----------
- The first line in the header is always "##FOF-CT_Version=vX.X"
- The second line in the header is always "##Table_Namespace=4dn_FOF-CT_extracell"

The header MUST include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/extracell_header.csv
  :header-rows: 1

Data Columns
------------
Each row corresponds to data associated with an individual extracellular ROI.

The first column of this table is always **Extra_Cell_ROI_ID**.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/extracell_columns.csv
  :header-rows: 1
