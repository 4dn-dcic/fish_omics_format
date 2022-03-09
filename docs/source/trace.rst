.. _trace:

Trace Data table
================

Requirement level: optional

Summary
-------
This table is used to document properties that are globally associated with individual Traces rather than individual bright Spots (e.g., Physical coordinates, RNA transcription, or Allele). These are properties that are shared by all bright Spots that constitute a Trace.

Each row in the table corresponds to an individual Trace and is indexed by a unique **Trace_ID** that links the data reported in this table with data stored in one of the other tables (i.e., :ref:`core`, :ref:`cell`, etc.). 

Example
-------
.. include:: examples/trace
  :code:

File Header
-----------
- The first line in the header is always "##FOF-CT_version=vX.X"
- The second line in the header is always "##Table_namespace=4dn_FOF-CT_trace"

The header should include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/trace_header.csv
  :header-rows: 1

Data Columns
------------
Each row corresponds to data associated with an individual Trace.

The first column of this table is always **Trace_ID**.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/trace_columns.csv
  :header-rows: 1
