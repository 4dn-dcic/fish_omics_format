.. _rna:

RNA-Spot Data table
===================

Requirement level: conditionally required

Summary
-------

This table is used to store and share the results of RNA FISH-omics experiments
and it is required in the case RNA data was collected as part of this
experiment. Each row represents a detected RNA bright Spot
and corresponds to the localization of a specific RNA transcript. At a
minimum, one needs to know the Spot_ID, the X, Y, Z coordinates of each
localization, the Gene_ID and an additional ID used to link this data
with other tables in this format (i.e., Trace_ID, ROI_ID and/or
Cell_ID). In addition, in case multiple transcripts are associated with
the same Gene_ID and the FISH probes are capable of distinguishing them,
Transcript_ID MUST also be reported. Thus, at a minimum there needs to
be 6 (or 7) data columns. These are required. All other data columns are
optional.

In this table the reported X, Y and Z coordinates are assumed to result
from post-processing and quality control procedures and therefore
correspond to the final localization of the RNA molecule under study.

In the case of multiplexed FISH experiments (i.e., MERFISH) in which the
final localization of RNA molecule results from combining multiple
detection events (e.g., by combining Spots detected in separate images),
the underlying raw data can be recorded in corresponding RNA Spot
quality tables as described below.

Example
-------

.. include:: examples/rna
  :code:

File Header
-----------

The first line in the header is always "##FOF-CT_version=vX.X"

The header MUST to contain a mandatory set of fields that describe the
algorithm(s) that were used to identify and localize bright Spots.
In case more than on algorithm were used, please use the same set of fields
for each of them.

The header should include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/rna_header.csv
  :header-rows: 1

Data Columns
------------

As with all other Spot Data tables in this format, each row corresponds to
data associated with an individual Spot.

The first columns are always: Spot_ID, X, Y, Z coordinates, RNA_name,
Gene_ID(, Transcript_ID).
The order of the other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/rna_columns.csv
  :header-rows: 1
