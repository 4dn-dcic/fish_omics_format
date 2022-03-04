.. _bio:

Spot Biological Data table
==========================

Requirement level: recommended

Summary
-------

This table is highly recommended and it is designed to store and share
biological properties associated with individual Spots (e.g., distance
from the nuclear lamina (NL) or the nuclear pore complex (NPC), etc.; Su
et al 2020 Cell and Takei et al 2021 Nature) identified as part of this
experiment. In the absence of a consensus regarding biological
properties to be recorded in association with individual bright Spots or
Traces, the specific columns in this table remain at the user’s
discretion and should be described with sufficient details to ensure
interpretation and reproducibility.

This table is mandatorily indexed by Spot_ID.

Example
-------

.. include:: examples/bio
  :code:

File Header
-----------

The first line in the header is always "##FOF-CT_version=vX.X"

This Table can be indexed mandatorily by Spot_ID.

The header MUST to contain a mandatory set of fields that describe any
algorithm that was used to produce/process data in this table.
In case more than on algorithm were used, please use the same set of fields
for each of them.

The header should include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/spot_bio_header.csv
  :header-rows: 1

Data Columns
------------

Each row corresponds to data associated with an individual Spot or Trace.

The first columns are always: Spot_ID, X, Y, Z coordinates, RNA_name,
Gene_ID(, Transcript_ID).
The order of the other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/spot_bio_columns.csv
  :header-rows: 1
