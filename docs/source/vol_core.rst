.. _vol-core:

SM Localization Data vol_core table
==============================

Requirement level: **required**

Namespace: *FOF-CT_vol_core*

Summary
-------
This is the mandatory core table of the FISH-omics Format for Volumetric (vol) Chromatin Tracing (FOF-vol-CT). It records and exchanges the primary results of vol Chromatin Tracing experiments, whether the genome under study is unmodified or contains INSERTIONS or DELETIONS.

The vol_core table is organized around individual single-molecule (SM) localization events. Each row reports the ``X``, ``Y``, ``Z`` coordinates of an individual SM Localization event, the genomic DNA target it corresponds to — identified by chromosome ID (``Chrom``), and by start (``Chrom_Start``) and end (``Chrom_End``) — and the Spot and Trace assignment of that event.

  .. tip:: For genomic coordinates, it is recommended to use GRCh38 for human and GRCm38 for mouse. For other species, follow these `instructions. <https://data.4dnucleome.org/search/?type=Organism>`_ In addition, in case the genome under study contains INSERTION/DELETIONs, also follow these :ref:`IN_DEL-reference-label`.
  
At a minimum, the table must have the **9 required columns** in the following order: ``Loc_ID``, ``Spot_ID`` ``Trace_ID``, ``X``, ``Y``, ``Z``, ``Chrom``, ``Chrom_Start``, ``Chrom_End``.

Additionally, in case sub-cellular structures, cells, or extracellular structures (e.g., Tissue) are identified as part of this experiment, this table has to mandatorily include the ID of the Sub_Cellular (``Sub_Cell_ROI_ID``), Cell (``Cell_ID``) or Extra Cellular (``Extra_Cell_ROI_ID``) Region of Interest (ROI) each SM Localization event is associated with.

All other SM Localization properties must be kept in the corresponding :ref:`vol-quality` as described in the instructions for this table.
  
Additionally, the underlying raw data can be recorded in the corresponding :ref:`undecoded` table as described in the instructions of that table.

.. tip:: ``Localization_ID`` identifiers are unique across the entire dataset, thus allowing the unambiguous identification of SM Localization events across this table and the :ref:`vol-quality`, and the :ref:`undecoded`. 

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

.. _IN_DEL-reference-label:
  
Instructions for when the genome under study is modified
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Instructions for reporting the location of SM Localization events, Spots and Traces in case the genome under study contains insertions or deletions:

#. Add the ``custom-build`` prefix to the genome build name and introduce a descriptive name detailing the nature of the genome modification.
#. Insert the following additional fields in the File header
#. ``##modification`` to indicate the nature and location of the modification
#. ``##VCF_File_name`` to indicate the name of the mandatory `Variant Call Format (VCF) <https://samtools.github.io/hts-specs/VCFv4.2.pdf>`_ file to be included with the FOF-CT dataset to report the nature and location of the genome modification.
#. ``##VCF_version`` to indicate the VCF version used for the VCF file describing the nature and location of the genome modification.
#. - Attach a separate `VCF <https://samtools.github.io/hts-specs/VCFv4.2.pdf>`_ file with your FOF-CT dataset to describe the nature and location of the genome modification.
#. - In the ``Chrom`` column insert the name of the inserted or deleted DNA fragment.
#. - In the ``ChromStart`` and ``ChromEnd`` columns insert the Start and End coordinates of the target chromosome segment with respect to the INSERTION or DELETION.

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

As with all other Spot Data tables, each row corresponds to
data associated with an individual Spot.

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
