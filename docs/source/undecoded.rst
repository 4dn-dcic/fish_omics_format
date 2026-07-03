.. _undecoded:

Undecoded SM Localization Data table
=========================

Requirement level: optional

Recommended: **Yes**

Namespace: *4dn_FOF-CT_undecoded*

Summary
-------
This table is optional and is designed to be used to report the X, Y, Z coordinates of individual SM Localization events before decoding.

When raw, pre-decoding data are reported, the underlying primary localization data are recorded in this table, as shown in the example below, while the final, decoded SM Localization event is recorded in :ref:vol_core.

This table is indexed by ``Loc_ID``, mandatorily reports the ``X``, ``Y``, ``Z`` coordinates of the primary SM Localization events, as well as the image frame (``Frame_ID``) and the fluorescent channel (``Fluor``) in which each SM Localization event was detected. All other columns are at the user's discretion.

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions, see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=4dn_FOF-CT_mapping``.

.. tip:: The header **MUST** contain a mandatory set of fields that describe any Software tool that was used to produce/process data in this table. If more than one software tool was used, please repeat a set of Software-fields for describing each of them.

The header **MUST** include a detailed description of each optional column used.

.. csv-table::
  :file: tables/demultiplexing_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions see :ref:`columns-reference-label`

This table is indexed by ``Loc_ID`` and therefore each row corresponds to data associated with an individual SM Localization event.

The first columns are always: ``Loc_ID``, ``Frame_ID``, ``X``, ``Y``, ``Z``, ``Fluor``.
The content and order of all other columns are at the user's discretion. The order of the rows is at the user's discretion.

.. csv-table::
  :file: tables/demultiplexing_columns.csv
  :header-rows: 1
  
Example
-------
The only mandatory columns in this table are ``Loc_ID``, ``Frame_ID``, ``X``, ``Y``, ``Z``, ``Fluor``.  All other columns are optional and must be defined by the user using a Header line starting with ``#^``. 

.. tip:: The optional columns in this example table are included for illustrative purposes only and describe a case in which DNA spots are detected with multiplexed barcodes.

.. include:: examples/demultiplexing
  :code:
