.. _rna:

RNA-Spot Data table
===================

Requirement level: conditionally required

Summary
-------

This table is used to store and share the results of RNA FISH-omics experiments
and it is **conditionally required** in the case RNA data was collected as part of this
experiment. Each row represents a detected RNA bright Spot
and corresponds to the location of a specific RNA transcript. 

At a minimum, one needs to know the **Spot_ID**, the **X**, **Y**, **Z** coordinates of each
spot, the **Gene_ID** and an additional ID used to link this data
with other tables in this format (i.e., *Trace_ID*, *Sub_Cell_ROI_ID*, *Cell_ID* and/or *Extra_Cell_ROI_ID*). In addition, in case multiple transcripts are associated with
the same Gene_ID and the FISH probes are capable of distinguishing them,
*Transcript_ID* MUST also be reported. Thus, at a minimum there needs to
be 6 (or 7) data columns. These are required. All other data columns are
optional.

In this table the reported X, Y and Z coordinates are assumed to result
from post-processing and quality control procedures performed on primary localization events and therefore
correspond to what is considered the best-bet location of the RNA molecule under study.

In the case of multiplexed FISH experiments (i.e., `MERFISH <https://doi.org/10.1073/pnas.1912459116>`_) in which the
final location of RNA molecule results from combining multiple
detection events (e.g., by combining individual Localization events detected in separate planes or images),
the underlying raw data can be recorded in the corresponding
:ref:`demultiplexing` as described in the instructions of that table.

Example
-------

.. include:: examples/rna
  :code:

File Header
-----------
- The first line in the header is always "##FOF-CT_version=vX.X"
- The second line in the header is always "##Table_namespace=4dn_FOF-CT_rna"

The header MUST contain a mandatory set of fields that describe the
algorithm(s) that were used to identify and localize bright Spots.
In case more than on algorithm were used, please use the same set of fields
for each of them.

The header should include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/rna_header.csv
  :header-rows: 1

Data Columns
------------
As with all other Spot Data tables in this format, each row corresponds to data associated with an individual Spot.

The first columns are always: **Spot_ID**, **X**, **Y**, **Z**, **RNA_name**,
**Gene_ID**, followed by *Transcript_ID* if applicable, and by **one or more** of the following *Trace_ID*, *Sub-Cell_ROI_ID* and/or
*Cell_ID*.
The order of the other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/rna_columns.csv
  :header-rows: 1
