.. _cell:

Cell Data table (optional)
==========================

.. contents::

Summary
-------

This table is used to document properties that are globally associated with
individual Cells (e.g., cell size, cell volume, cell type) and it is required
in the case Cell segmentation data was collected as part of this experiment.
These are properties that are shared by all bright Spots and
Traces that belong to an individual Cell. Each row in the table
corresponds to a different Cell studied in the experiment and is
identified by a unique Cell_ID that links the data reported in this
table with data stored in one of the other tables (i.e.,
DNA_Spot/Trace_Data, Global_Trace_Data, etc.,). The header should note
the coordinate system used for the cell x/y/z centroid.

Example
-------

.. include:: examples/cells
  :code:

File Header
-----------

The first line in the header is always “##FOF-CT_version=vX.X”

The header should include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/cell_header.csv
  :widths: 20 40 20 20
  :header-rows: 1

Data Columns
------------

Each row corresponds to data associated with an individual Cell.

The first column of this table is always Cell_ID.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

.. list-table::
  :header-rows: 1

  * - Name
    - Description
    - Example
    - Conditional requirement conditions
  * - **Cell_ID**
    - This fields reports the unique identifier for Region of Interest (ROI) that represent the boundaries of a Cell identified as part of this experiment. Note: this is used to connect individual Spots or Traces that are part of the same Cell.
    - 1
    -
  * - *Extra_Cell_ROI_ID*
    - In case multiple Cells are localized within a given extracellular structure (e.g., Tissue) Region of Interest (ROI), this fields reports the unique identifier that allows to identify such as ROI. Note: this is used to connect individual Cells that are part of the same extracellular ROI.
    - 1
    - Conditional requirement: this column is mandatory if data in this table can be associated with an extracellular ROI identified as part of this experiment.
  * - optional_column_1
    -
    -
    -
  * - optional_column_2
    -
    -
    -
  * - optional_column_3
    -
    -
    -
