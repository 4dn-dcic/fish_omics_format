.. _core:

DNA-Spot/Trace Data core table
==============================

Requirement level: required

Summary
-------

This is the mandatory core table of the 4DN FISH-omics Format for Chromatin
Tracing. This table is used to record and exchange the primary results of
Chromatin Tracing experiments. The Table is organized around individual DNA
bright Spots that are spatially linked together in a three-dimensional (3D)
polymeric Trace using a 3D polymeric tracing algorithm. As a result, all Spots
that share the same Trace_ID, by definition belong to the same Trace.

Each row reports the x, y, z localization, and the Trace assignment
(i.e., Trace_ID) of a FISH-omics bright Spot and corresponds to a specific
genomic DNA target sequence identified by Chromosome ID, and by Start and End
chromosome coordinates.

At a minimum the Table has to have 8 columns in the following order: Spot_ID,
Trace_ID, X, Y, Z coordinates, Chromosome ID, Chromosome Start, Chromosome End.
These are required.
Additionally in case sub-cellular structures, cells or Extra Cellular
Structures (e.g., Tissue) are identified as part of this experiment,
this table has to mandatorily include the ID of the Sub_Cellular, Cell or
Extra Cellular Structure (e.g., Tissue) Region of Interest (ROI)
each Spot/Trace is associated with. The order of these columns is optional.

All other spot properties should be kept in the optional
additional Spot Biological Data table, indexed by Spot_ID.

Example
-------

.. include:: examples/core
  :code:

File Header
-----------

The first line in the header is always "##FOF-CT_version=vX.X"

The header MUST to contain a mandatory set of fields that describe the
algorithm(s) that were used to identify and localize bright Spots and to
connect them to form Traces.
In case more than one algorithm were used, please use the same set of fields
for each of the algorithm used.

The columns for this table are mandatory and do not need to be described
in the header.

.. csv-table::
  :file: tables/core_header.csv
  :header-rows: 1

Data Columns
------------

As with all other Spot Data tables in this format, each row corresponds to
data associated with an individual Spot.

The first columns are always: Spot_ID, Trace_ID, X, Y, Z, Chrom, Chrom_Start,
Chrom_End.
The order of the other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/core_columns.csv
  :header-rows: 1
