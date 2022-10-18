.. _subcell:

Sub-Cell ROI Data table
=======================

Requirement level: conditionally required

Summary
-------
This table is used to document properties that are globally associated with
individual sub-cellular ROIs that typically correspond to sub-nuclear features
(e.g., Nucleoli, Nuclear Lamina, Chromosome Domains, PML bodies, etc.)
and it is required in the case sub-cellular ROI segmentation data was collected
as part of this experiment.
These are properties that are shared by all bright Spots and Traces that are
associated with individual ROIs.
Each row in the table corresponds to a different Subcell ROI studied in the
experiment and is identified by a unique **Sub_Cell_ROI_ID** that links the data
reported in this table with data stored in one of the other tables
(e.g., :ref:`core`, :ref:`cell`, etc.).

Example
-------
.. include:: examples/subcell
  :code:

File Header
-----------
- The first line in the header is always "##FOF-CT_version=vX.X"
- The second line in the header is always "##Table_namespace=4dn_FOF-CT_subcell"

The header MUST include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/subcell_header.csv
  :header-rows: 1

Data Columns
------------
Each row corresponds to data associated with an individual subcellular ROI.

The first column of this table is always **Sub_Cell_ROI_ID**.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/subcell_columns.csv
  :header-rows: 1
