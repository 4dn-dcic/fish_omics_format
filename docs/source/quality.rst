.. _quality:

Spot Quality Data table
=======================

Requirement level: recommended

Summary
-------

This table is highly recommended and it is designed to provide quality
metrics for the Spot localization, information about the optical Channel
that was used to image the Spot, and various aberration corrections that
have been applied prior to localization (e.g., drift correction,
chromatic correction, etc.,).

Because the quantification of Spot quality and uncertainty is not
trivial and lacking consensus, the specific columns in this table remain
at the user’s discretion and should be described with sufficient details
to ensure interpretation and reproducibility.

The table is indexed by Spot_ID and each row corresponds to a DNA or RNA
bright Spot. The order of not required columns and of the rows are at
the user's discretion.

Example
-------
Spot fit quality

.. include:: examples/quality
  :code:

File Header
-----------

The first line in the header is always "##FOF-CT_version=vX.X"

The header MUST to contain a mandatory set of fields that describe any
algorithm that was used to produce/process data in this table.
In case more than on algorithm were used, please use the same set of fields
for each of them.

The header should include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/quality_header.csv
  :header-rows: 1

Data Columns
------------

As with all other Spot Data tables in this format, each row corresponds to
data associated with an individual Spot.

The first column of this table is always Spot_ID.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/quality_columns.csv
  :header-rows: 1
