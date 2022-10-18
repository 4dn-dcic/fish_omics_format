.. _demultiplexing:

Spot Demultiplexing table
=========================

Requirement level: optional

Summary
-------
This table is optional and is designed to be used in the case of multiplexed
FISH experiments (i.e., MERFISH) in which the final localization of a bright
DNA or RNA Spot results from the combination of multiple individual localization events (e.g., by combining particles detected and localized in separate images).
In such a case the final Spot localization data is recorded in the
:ref:`core`, while the underlying primary localization data can be recorded by using this table, as shown for DNA Spots in the example below.

This table is indexed by **Loc_ID**, mandatorily reports the **X**, **Y**, **Z** coordinates of the Localization event, and it has a mandatory **Spot_ID** column that is used to link individual localization events to the resulting Spot.

Other columns are at user's discretion.

Example
-------
DNA spots detected with multiplexed barcodes

.. include:: examples/demultiplexing
  :code:

File Header
-----------
- The first line in the header is always "##FOF-CT_version=vX.X"
- The second line in the header is always "##Table_namespace=4dn_FOF-CT_demultiplexing"

The header MUST contain a mandatory set of fields that describe any
algorithm that was used to produce/process data in this table.
In case more than one algorithm were used, please use the same set of fields
for each of them.

The header MUST include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/demultiplexing_header.csv
  :header-rows: 1

Data Columns
------------
This table is indexed by Loc_ID and therefore each row corresponds to data
associated with an individual Localization event.

The first columns are always: **Loc_ID**, **Spot_ID**, **X**, **Y**, **Z**.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/demultiplexing_columns.csv
  :header-rows: 1
