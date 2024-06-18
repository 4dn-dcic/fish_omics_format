.. _cell:

Cell Data table
===============

Requirement level: optional

Summary
-------
This table is used to document properties that are globally associated with
individual Cells (e.g., cell size, cell volume, cell type) and it is required
in the case Cell segmentation data was collected as part of this experiment.
These are properties that are shared by all bright Spots and
Traces that belong to an individual Cell. Each row in the table
corresponds to a different Cell studied in the experiment and is
identified by a unique **Cell_ID** that links the data reported in this
table with data stored in one of the other tables (e.g.,
:ref:`core`, :ref:`subcell`, :ref:`mapping`, etc.).

Example
-------
.. include:: examples/cell
  :code:

File Header
-----------
- The first line in the header is always "##FOF-CT_version=vX.X"
- The second line in the header is always "##Table_namespace=4dn_FOF-CT_cell"

The header MUST include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/cell_header.csv
  :header-rows: 1

Data Columns
------------
Each row corresponds to data associated with an individual Cell.

The first column of this table is always **Cell_ID**.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/cell_columns.csv
  :header-rows: 1