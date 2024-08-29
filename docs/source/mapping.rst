.. _mapping:

Cell/ROI Mapping table
======================

Requirement level: *conditionally required*

Summary
-------
This table is used to provide the boundaries of Cells and other ROIs
identified as part of this experiment, and it is required in case Cell and
other ROI segmentation data were collected as part of this experiment.

This table is *conditionally required* in case a :ref:`subcell`, :ref:`cell`, and/or :ref:`extracell` tables are deposited with this submission.

The table is organized on a Cell or ROI basis via a Cell or ROI ID and is designed to provide the boundaries of each Cell and ROI boundaries in global coordinates. 

This could be done as specified by the `OME ROI data model <https://docs.openmicroscopy.org/ome-model/5.6.3/developers/roi.html>`_. Alternatively, Cell or ROI boundaries could be provided using 3D MESH models (e.g., using the `OBJ format <https://en.wikipedia.org/wiki/Wavefront_.obj_file>`_). Additional formats are also allowed.

As such, this table is mandatorily indexed by one of the following ``Cell_ID``, ``Sub_Cell_ROI_ID`` or ``Extra_Cell_ROI_ID``.

In addition, the header of the file **MUST** include the ``##ROI_boundaries_format=`` field to report the format that is used to record the boundaries of the ROI in global coordinates.

As an example, this table might be organized in one of the following manner:

# Cell boundaries
	-  ``##ROI_boundaries_format=``Cell boundaries are reported in global coordinates following the OME Data Model for Polygon - ROI. As such Cell boundaries are defined as lists of comma separated x,y coordinates separated by spaces like "x1,y1 x2,y2 x3,y3"
 e.g. "0,0 1,2 3,5").
	- ``Cell_ID`` → "0,0 1,2 3,5").

# Sub-Cell ROI boundaries
	-  ``##ROI_boundaries_format=``Sub-cell ROI boundaries are reported in global coordinates following the OME Data Model for Polygon - ROI. As such the Cell boundaries are defined as lists of comma separated x,y,z coordinates separated by spaces like "x1,y1,z1 x2,y2,z2 x3,y3,z3"
 e.g. "0,0 1,2 3,5").
	- ``Sub_Cell_ROI_ID`` → "0,0,0 1,2,3 4,5,6").

# Extra_Cell_ROI_ID boundaries
	-  ``##ROI_boundaries_format=``Extra-cell ROI boundaries are reported in global coordinates using the `OBJ format <https://en.wikipedia.org/wiki/Wavefront_.obj_file>`_ for 3D MESH models. As such boundaries are defined as lists of geometric vertices, with (x, y, z, [w]) coordinates, w is optional and defaults to 1.0.
- ``Extra_Cell_ROI_ID`` → "v 0.123 0.234 0.345 1.0").

In addition, this table might be used to report additional vectorial
properties such as:

-  Lists of RNA Spot x/y/z in global coordinates
-  Lists of barcode sequence ID
-  Lists of channels

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=4dn_FOF-CT_mapping``.

The header **MUST** include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/mapping_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions see :ref:`columns-reference-label`

Each row corresponds to data associated with an individual ``Cell_ID``, ``Sub_Cell_ROI_ID``, or ``Extra_Cell_ROI_ID``.

The first column of this table is always the relevant ID.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

It is mandatory to choose one of the three types of ID.

.. csv-table::
  :file: tables/mapping_columns.csv
  :header-rows: 1

Example
-------
.. include:: examples/mapping
  :code:
