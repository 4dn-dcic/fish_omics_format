.. _demultiplexing:

Spot Demultiplexing table
=========================

Requirement level: optional

Recommended: **Yes**

Namespace: *4dn_FOF-CT_demultiplexing*

Summary
-------
This table is optional and is designed to be used in the case of multiplexed FISH experiments (i.e., MERFISH) in which the final localization of a bright DNA or RNA Spot results from the combination of multiple individual localization events (e.g., by combining particles detected and localized in separate images).

In such a case the final Spot localization data is recorded in the
:ref:`core`, while the underlying primary localization data can be recorded by using this table, as shown for DNA Spots in the example below.

This table is indexed by ``Loc_ID``, mandatorily reports the ``X``, ``Y``, ``Z`` coordinates of the Localization event and the fluorescent channel (``Fluor``) in which this localization was detected. In addition, the table has a mandatory ``Spot_ID`` column that is used to link individual localization events to the resulting Spot.

Other columns are at user's discretion.

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=4dn_FOF-CT_mapping``.

.. tip:: The header **MUST** contain a mandatory set of fields that describe any Software tool that was used to produce/process data in this table. If more than one software tool was used, please repeat a set of Software-fields for describing each of them.

The header **MUST** include a detailed description of each optional columns used.

.. csv-table::
  :file: tables/demultiplexing_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions see :ref:`columns-reference-label`

This table is indexed by ``Loc_ID`` and therefore each row corresponds to data associated with an individual Localization event.

The first columns are always: ``Loc_ID``, ``Spot_ID``, ``X``, ``Y``, ``Z``, ``Fluor``.
The content and order of all other columns is at user's discretion.
The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/demultiplexing_columns.csv
  :header-rows: 1
  
Example
-------
The only mandatory columns in this table are ``Loc_ID``, ``Spot_ID``, ``X``, ``Y``, ``Z``, ``Fluor``.  All other columns are optional and must be defined by the user using a Header line starting with ``#^``. 

.. tip:: The optional columns in this example table are included for illustrative purposes only and describe a case in which DNA spots are detected with multiplexed barcodes.

.. include:: examples/demultiplexing
  :code:
