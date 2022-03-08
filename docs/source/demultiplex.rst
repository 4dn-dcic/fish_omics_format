.. _demultiplex:

Spot Demultiplexing table (optional)
====================================

Summary
-------

This table is optional and is designed to be used in the case of multiplexed
FISH experiments (i.e., MERFISH) in which the final localization of a bright
DNA or RNA Spot results from the combination of multiple
individual localization events (e.g., by combining particles detected and
localized in separate images).
In such a case the final Spot localization data is recorded in the
:ref:`core`, while the underlying primary localization data
can be recorded by using this table, as shown for DNA Spots in the
example below.

This table is indexed by Loc_ID and it has a mandatory Spot_ID column that
is used to link individual localization events to the resulting Spot.

Example
-------
DNA spots detected with multiplexed barcodes

.. include:: examples/demultiplex
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
  :file: tables/demultiplex_header.csv
  :header-rows: 1

Data Columns
------------

Each row corresponds to data associated with an individual Localization event.

The first column of this table is always Loc_ID.
The second column has to mandatorily be Spot_ID.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/demultiplex_columns.csv
  :header-rows: 1
