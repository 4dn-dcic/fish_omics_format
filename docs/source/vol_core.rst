.. _vol-core:

SM Localization Data vol_core table
===================================

Requirement level: **required**

Namespace: *FOF-CT_vol_core*

.. note:: The FOF-vol-CT namespaces (``FOF-CT_vol_core``, ``FOF-CT_undecoded``, ``FOF-CT_vol_quality``) intentionally omit the ``4dn_`` prefix to reflect the format's continued stewardship by the broader community beyond 4DN.

Summary
-------
This is the mandatory core table of the FISH-omics Format for Volumetric (vol) Chromatin Tracing (FOF-vol-CT). It records and exchanges the primary results of vol Chromatin Tracing experiments, whether the genome under study is unmodified or contains INSERTIONS or DELETIONS.

The vol_core table is organized around individual Single Molecule (SM) Localization events. Each row reports the ``X``, ``Y``, ``Z`` coordinates of an individual SM Localization event, the genomic DNA target it corresponds to — identified by chromosome ID (``Chrom``), and by start (``Chrom_Start``) and end (``Chrom_End``) — and the Spot and Trace assignment of that event.

.. note:: A valid FOF-vol-CT deposition **MUST** mandatorily report ``Loc_ID`` together with its associated ``Spot_ID`` and ``Trace_ID`` for every SM Localization event. ``Spot_ID`` and ``Trace_ID`` identify the same conceptual entities defined for FOF-bas-CT, a bright DNA Spot and the Trace it belongs to. The two modalities differ only in how the Spot centroid is derived: in FOF-bas-CT directly from an optically-resolved fluorescence spot, in FOF-vol-CT as the centroid (center of mass) of a cluster (i.e., volume) of individual SM Localization events. ``Trace_ID`` identifies the trace connecting individual Spot centroids along the chromosome in either case.

.. tip:: For genomic coordinates, it is recommended to use GRCh38 for human and GRCm38 for mouse. For other species, follow these `instructions. <https://data.4dnucleome.org/search/?type=Organism>`_ In addition, in case the genome under study contains INSERTION/DELETIONs, also follow these :ref:`IN_DEL-reference-label`.
  
At a minimum, the table must have the **9 required columns** in the following order: ``Loc_ID``, ``Spot_ID``, ``Trace_ID``, ``X``, ``Y``, ``Z``, ``Chrom``, ``Chrom_Start``, ``Chrom_End``.

Additionally, in case sub-cellular structures, cells, or extracellular structures (e.g., Tissue) are identified as part of this experiment, this table has to mandatorily include the ID of the Sub_Cellular (``Sub_Cell_ROI_ID``), Cell (``Cell_ID``) or Extra Cellular (``Extra_Cell_ROI_ID``) Region of Interest (ROI) each SM Localization event is associated with.

All other SM Localization properties must be kept in the corresponding :ref:`vol-quality` as described in the instructions for this table.
  
Additionally, the underlying raw data can be recorded in the corresponding :ref:`undecoded` table as described in the instructions of that table.

.. tip:: ``Loc_ID`` identifiers are unique across the entire dataset, thus allowing the unambiguous identification of SM Localization events across this table and the :ref:`vol-quality`, and the :ref:`undecoded`. 

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=FOF-CT_vol_core``.

.. tip:: The header **MUST** contain a mandatory set of fields that describe any Software tool that was used to produce/process data in this table. If more than one software tool was used, please repeat a set of Software-fields for describing each of them.

All columns for this table are mandatory and do not need to be described
in the header.

.. csv-table::
  :file: tables/vol_core_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions, see :ref:`columns-reference-label`

As with all other Spot Data tables, each row corresponds to data associated with an individual SM Localization event.

The first columns are always: ``Loc_ID``, ``Spot_ID``, ``Trace_ID``, ``X``, ``Y``, ``Z``, ``Chrom``, ``Chrom_Start``, ``Chrom_End``. Additionally, in case sub-cellular structures, cells or extracellular structures are identified as part of this experiment, the subsequent columns must mandatorily be ``Sub_Cell_ROI_ID``, ``Cell_ID`` or ``Extra_Cell_ROI_ID``, respectively.

The order of the rows is at the user's discretion.

.. csv-table::
  :file: tables/vol_core_columns.csv
  :header-rows: 1
  
Example without INSERTION/DELETION
----------------------------------
.. include:: examples/vol_core
  :code:

Example with INSERTION/DELETION
-------------------------------

.. warning:: In case your reference genome has insertions or deletions, please remember to follow these :ref:`IN_DEL-reference-label`

.. include:: examples/vol_core_IN-DEL
  :code:
