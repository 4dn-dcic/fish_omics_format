.. _undecoded:

Undecoded SM Localization Data table
====================================

Requirement level: optional

Recommended: **Yes**

Namespace: *FOF-CT_undecoded*

.. note:: The FOF-vol-CT namespaces (``FOF-CT_vol_core``, ``FOF-CT_undecoded``, ``FOF-CT_vol_quality``) intentionally omit the ``4dn_`` prefix to reflect the format's continued stewardship by the broader community beyond 4DN.

Summary
-------
This table is optional and is designed to be used to report the X, Y, Z coordinates of individual SM Localization events before decoding.

When raw, pre-decoding data are reported, the primary localization data collected across multiplexed hybridization rounds, image frames, and channels are recorded in this table (see example below). The final, decoded SM Localization event is recorded in :ref:`vol-core`."

This table is indexed by ``Loc_ID`` and mandatorily reports, for each primary SM Localization event, its ``X``, ``Y``, ``Z`` coordinates and the ``Image_Frame_ID``, ``Hyb_ID``, ``Channel``, and Fluorophore (``Fluor``) in which it was originally identified.

All other columns are at the user's discretion.

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions, see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=FOF-CT_undecoded``.

.. tip:: The header **MUST** contain a mandatory set of fields that describe any Software tool that was used to produce/process data in this table. If more than one software tool was used, please repeat a set of Software-fields for describing each of them.

The header **MUST** include a detailed description of each optional column used.

.. csv-table::
  :file: tables/undecoded_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions see :ref:`columns-reference-label`

This table is indexed by ``Loc_ID`` and therefore each row corresponds to data associated with an individual SM Localization event.

The first columns are always: ``Loc_ID``, ``Hyb_ID``, ``Image_Frame_ID``, ``X``, ``Y``, ``Z``, ``Channel``, ``Fluor``.
The content and order of all other columns are at the user's discretion. 
The order of the rows is at the user's discretion.

.. csv-table::
  :file: tables/undecoded_columns.csv
  :header-rows: 1
  
Example
-------
The only mandatory columns in this table are ``Loc_ID``, ``Hyb_ID``, ``Image_Frame_ID``, ``X``, ``Y``, ``Z``, ``Channel``, ``Fluor``.  All other columns are optional and must be defined by the user using a Header line starting with ``#^``. 

.. tip:: The Optional Columns (OC) in this example table are included for illustrative purposes only and describe a case in which DNA spots are detected with multiplexed barcodes.

.. include:: examples/undecoded
  :code:
