.. _core:

DNA-Spot/Trace Data core table
==============================

Requirement level: **required**

Namespace: *4dn_FOF-CT_core*

Summary
-------
This is the mandatory core table of the FISH-omics Format for **ball-and-stick** Chromatin
Tracing (FOF-bas-CT). This table is used to record and exchange the primary results of
Chromatin Tracing experiments, both in the case in which the genome under study is unmodified and in the case in which it contains INSERTIONS or DELETIONS.

The core table is organized around individual DNA bright Spots that are generally spatially linked in a three-dimensional (3D) polymeric Trace using a 3D polymeric tracing algorithm. As a result, all Spots that share the same ``Trace_ID``, by definition, belong to the same Trace.

In this table, each row reports the ``X``, ``Y``, ``Z`` localization, and the Trace assignment (i.e., ``Trace_ID``) of a FISH-omics bright Spot and corresponds to a specific genomic DNA target sequence identified by chromosome ID (``Chrom``), and by start (``Chrom_Start``) and end (``Chrom_End``) chromosome coordinates.
In this table the reported ``X``, ``Y``, ``Z`` coordinates are assumed to result from post-processing and quality control procedures and therefore
correspond to the final localization of the DNA target under study.

.. tip:: For genomic coordinates, it is recommended to use GRCh38 for human and GRCm38 for mouse. For other species, follow these `instructions. <https://data.4dnucleome.org/search/?type=Organism>`_ In addition, in case the genome under study contains INSERTION/DELETIONs, also follow these :ref:`IN_DEL-reference-label`.

At a minimum, the Table has to have 8 columns in the following order:
``Spot_ID``, ``Trace_ID``, ``X``, ``Y``, ``Z``, ``Chrom``, ``Chrom_Start``,
``Chrom_End``. These are required. Additionally, in case sub-cellular
structures, cells or extracellular structures (e.g., Tissue) are identified as part of this experiment, this table has to mandatorily include the ID of the Sub_Cellular, Cell, or Extracellular Structure Region of Interest (ROI) each Spot/Trace is associated with.

All other spot properties must be kept in the two additional tables
:ref:`quality` and :ref:`bio`, indexed by Spot_ID and as described in the
instructions for those tables.
Additionally, in the case in which the final localization of DNA target results from combining multiple detection events (e.g., by combining localization events from different focal planes or times), the underlying raw data can be recorded in the corresponding :ref:`demultiplexing` table as described in the instructions of that table.

.. tip:: ``Spot_ID`` identifiers are unique across the entire dataset, thus allowing to identify a Spot unambiguously in the :ref:`quality`, :ref:`bio` and :ref:`demultiplexing`. 

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

File Header
-----------
- For full instructions see :ref:`headers-reference-label`
- The first line in the header is always ``##FOF-CT_Version=vX.X``.
- The second line in the header is always ``##Table_Namespace=4dn_FOF-CT_core``.

.. tip:: The header **MUST** contain a mandatory set of fields that describe any Software tool that was used to produce/process data in this table. If more than one software tool was used, please repeat a set of Software-fields for describing each of them.

All columns for this table are mandatory and do not need to be described
in the header.

.. csv-table::
  :file: tables/core_header.csv
  :header-rows: 1

Data Columns
------------
- For full instructions see :ref:`columns-reference-label`

As with all other Spot Data tables, each row corresponds to
data associated with an individual Spot.

The first columns are always: ``Spot_ID``, ``Trace_ID``, ``X``, ``Y``, ``Z``, ``Chrom``, ``Chrom_Start``, ``Chrom_End``. Additionally in case sub-cellular structures, cells or extra cellular structures are identified as part of this experiment, the subsequent columns must mandatorily be ``Sub_Cell_ROI_ID``, ``Cell_ID`` or ``Extra_Cell_ROI_ID``, respectively.

The order of the rows is at user's discretion.

.. csv-table::
  :file: tables/core_columns.csv
  :header-rows: 1
  
Example without INSERTION/DELETION
----------------------------------
.. include:: examples/core
  :code:

Example with INSERTION/DELETION
-------------------------------

.. warning:: In case your reference genome has insertions or deletions, please remember to follow these :ref:`IN_DEL-reference-label`

.. include:: examples/core_IN-DEL
  :code:
