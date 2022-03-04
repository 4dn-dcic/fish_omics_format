.. _demultiplexing:

Spot Demultiplexing Data table
==============================

Requirement level: optional

Summary
-------

This table is optional and is designed to provide additional Spot
properties that are not recorded in the mandatory DNA Spot/Trace Data
table, the main RNA Spot Data table or the other recommended tables. In
the absence of a consensus, the specific columns in this table remain at
the user’s discretion and should be described with sufficient details to
ensure interpretation and reproducibility. In the case of multiplexed
FISH experiments (i.e., MERFISH) in which the final localization of RNA
molecule results from combining multiple detection events (e.g., by
combining Spots detected in separate images), the underlying raw data
can be recorded in corresponding RNA Spot quality tables as shown in the
examples below.

This table can be indexed by Localization_ID.


This table is optional and is designed to be used in the case of multiplexed
FISH experiments (i.e., MERFISH) in which the final localization of a bright
DNA or RNA Spot of interest results from the combination of multiple
individual localization events (e.g., by combining particles detected and
localized in separate images).
In such a case the final Spot localization data is recorded in the core
DNA Spot/Trace Data table, while the underlying primary localization data
can be recorded by using this table, as shown for RNA Spots in the
example below.

This table is indexed by Loc_ID and it has a mandatory Spot_ID column that
is used to link individual localization events to the resulting Spot.

Example
-------
DNA spots detected with multiplexed barcodes

.. include:: examples/demultiplexing
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
