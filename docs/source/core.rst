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

Each row reports the X, Y, Z localization, and the Trace assignment
(i.e., Trace_ID) of a FISH-omics bright Spot and corresponds to a specific
genomic DNA target sequence identified by chromosome ID (Chrom), and by start
(Chrom_Start) and end (Chrom_End) chromosome coordinates. In this table the reported X, Y and Z coordinates are assumed to result
from post-processing and quality control procedures and therefore
correspond to the final localization of the DNA target under study.

At a minimum the Table has to have 8 columns in the following order: Spot_ID, Trace_ID, X, Y, Z, Chrom, Chrom_Start, Chrom_End. These are required. Additionally in case sub-cellular structures, cells or extra cellular structures (e.g., Tissue) are identified as part of this experiment, this table has to mandatorily include the ID of the Sub_Cellular, Cell or Extra Cellular Structure Region of Interest (ROI) each Spot/Trace is associated with. All other spot properties must be kept in the two additional tables :ref:`quality` amd :ref:`bio`, indexed by Spot_ID and as described in the instructions for those tables.

Finally, in the case in which the final localization of DNA target results from combining multiple
detection events (e.g., by combining localization events from different focal planes or times),
the underlying raw data can be recorded in the corresponding
:ref:`demultiplexing` table as described in the instructions of that table.


Example
-------

.. include:: examples/core
  :code:

File Header
-----------

- The first line in the header is always "##FOF-CT_version=vX.X"
- The second line in the header is always "##Table_namespace=4dn_FOC-CT_core"

The header MUST contain a mandatory set of fields that describe the
algorithm(s) that were used to identify and localize bright Spots and to
connect them to form Traces. In case more than one algorithm were used, please use the same set of fields
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
Chrom_End. Additionally in case sub-cellular structures, cells or extra cellular structures are identified as part of this experiment, the subsequent columns must mandatorily be Sub_Cell_ROI_ID, Cell_ID or Extra_Cell_ROI_ID, respectively. 

The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/core_columns.csv
  :header-rows: 1
