.. _mapping:

Cell/ROI Mapping table (conditionally required)
===============================================

Summary
-------
This table is used to provide the boundaries of Cells and other ROIs
identified as part of this experiment, and it is required in case Cell and
other ROI segmentation data were collected as part of this experiment.

This table is mandatory in case a Sub_Cell_ROI _Data, Cell_Data,
and/or Extra_Cell_ROI_Data tables are deposited with this submission.

The table is organized on a Cell/ROI basis via a Cell/ROI ID and
provides the Cell/ROI boundaries in global coordinates as specified by
the OME ROI data model
(https://docs.openmicroscopy.org/ome-model/5.6.3/developers/roi.html).

This table might be organized in one of the following manner:

-  Cell_ID → Cell boundaries in global coordinates (following the OME
   Data Model for Polygon - ROI, the Cell boundaries are defined as a
   list of comma separated x,y coordinates separated by spaces like
   "x1,y1 x2,y2 x3,y3" e.g. "0,0 1,2 3,5").
-  Sub_Cell_ROI_ID → Sub-cellular ROI (e.g., Nuclear feature, Nucleolus,
   etc.,) boundaries x/y/z in global coordinates (following the OME Data
   Model for Polygon - Sub_Cell ROI, boundaries are defined as a list of
   comma separated x,y coordinates separated by spaces like "x1,y1 x2,y2
   x3,y3" e.g. "0,0 1,2 3,5"). This table might also report the feature
   brightness.
-  Extra_Cell_ROI_ID → Extracellular ROI boundaries (e.g., Tissue) in
   global coordinates (following the OME Data Model for Polygon - ROI,
   Super-Cell ROI boundaries are defined as a list of comma separated
   x,y coordinates separated by spaces like "x1,y1 x2,y2 x3,y3" e.g.
   "0,0 1,2 3,5").

In addition, this table might be used to report additional vectorial
properties such as:

-  Lists of RNA Spot x/y/z in global coordinates,
-  Lists of barcode sequence ID
-  Lists of channels

Example
-------

.. include:: examples/mapping
  :code:

File Header
-----------

The first line in the header is always “##FOF-CT_version=vX.X”

The header should include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/mapping_header.csv
  :header-rows: 1

Data Columns
------------

Each row corresponds to data associated with an individual Cell, Sub-Cell_ROI
or Extra_Cell_ROI.

The first column of this table is always the relevant ID.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

It is mandatory to choose one of the three types of ID.

.. csv-table::
  :file: tables/mapping_columns.csv
  :header-rows: 1
