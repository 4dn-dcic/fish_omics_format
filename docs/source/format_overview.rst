Format description
============================

General Info
------------
- The format is designed to cover both **Ball-and-Stick (BAS)** as well as **Volumetric (VOL)** Chromatin Tracing experimental modalities.
- The format is organized in multiple individual tables. The tables differ between the BAS and VOL modalities:

  - The 12 :ref:`BAS-table-reference-label` are common to both **BAS Chromatin Tracing** and **VOL Chromatin Tracing**. 
  - The additional 3 :ref:`VOL-table-reference-label` pertain **exclusively to VOL Chromatin Tracing**.

- Each modality only has one mandatory table:

  - For **BAS Chromatin Tracing**, the mandatory table is the :ref:`core`.
  - For **VOL Chromatin Tracing**, the mandatory table is the :ref:`vol-core`.

- All other tables are either conditionally required depending on experiment design and type or optional but *recommended* for all experiment types.
- Each file must contain a single table.
- Accepted file formats for storing tables are txt, csv and tsv.
- An underscore ``_`` must be used as a word separator in header field
  names and column headers to improve readability while not violating
  common name restrictions in coding environments (dash ``-`` may be
  mistaken as subtraction of variables).
- Each file has two parts: file header and data columns.

.. warning:: All **MANDATORY** header fields and column names are indicated in **bold**. All *conditionally required* header fields and column names are indicated in *italics*.

.. tip:: Except for :ref:`core`, :ref:`demultiplexing`, :ref:`vol-core`, :ref:`undecoded`, :ref:`rna` and :ref:`mapping`, all other :ref:`BAS-table-reference-label` and :ref:`VOL-table-reference-label` that are included in the deoposition **MUST** contain at least 1 **Optional Column**.

.. _headers-reference-label:
File Header
-----------
- All tables have to contain a mandatory header section.
- In the file header, each line contains only key-value pair.
- Header lines are denoted by ``#``. In particular:

  - ``##`` denotes machine readable header lines. These lines must follow the
    following format ``##Key_A=Value_1`` (e.g., ``##FOF-CT_Version=v0.1``).
  - ``#`` denotes human readable header lines. These lines should follow the
    following format, ``#Term_X: free text description`` (e.g.,
    ``#Lab_Name: name of the lab where the experiment was performed``).
  - ``#^`` denotes lines that define user specified **Optional Columns**.
    These lines provide the name of the column header and a description of the
    column content. Descriptions must be understandable and sufficient to ensure
    the interpretation and reproducibility of the results. These lines should
    follow the following format ``#^Term_X: free text description`` (e.g.,
    ``#^Optional_Column_1: optional column 1 description``).

- Header names **MUST** use the underscore as a word separator (e.g., RNA_A_intensity).
- The file header contains **required**, *conditionally-required*, and optional fields.
- Conditionally-required fields are fields that are required when certain
  conditions are met (e.g., ``##Intensity_Unit=`` is required any time an
  intensity metric is reported).

Mandatory header lines (all tables)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**##FOF-CT_Version=** Data format version number. E.g., v2.0

**##Table_Namespace=** Identifier for this type of table. Value must be as in the example. E.g., 4dn_FOF-CT_core

**##XYZ_Unit=** The unit used to represent XYZ locations or distances. Note: use micron to avoid problems with special, Greek symbols. Other allowed values *should* be drawn from SI units of `Length <https://en.wikipedia.org/wiki/SI_base_unit>`_. Examples: 'nm', 'micron' 'mm' etc.

**#Lab_Name:** Name of the lab where the experiment was performed

**#Experimenter_Name:** Name of the person performing the experiment

**#Experimenter_Contact:** Email address of the person performing the
experiment

**#Description:** A free-text description of the experiment and of the
data recorded in this table. This description should provide a clear
understanding of the process utilized to produce the data and contain
sufficient details to ensure interpretation and reproducibility.

**#Software_Title:** The name of the Software(s) that were used in this
case for localizing individual FISH-omics bright Spots and/or to produce
three-dimensional (3D) polymeric chromatin Traces.

**#Software_Type:** The type of this Software. Allowed values: SpotLoc,
Tracing, SpotLoc+Tracing, Other

**#Software_Authors:** The Name(s) of the individual Author(s) of this
Software. In case there are more than one Authors, individual names
should be listed as follows: Doe, John; Smith, Jane; etc,.

**#Software_Description:** A free-text description of this Software.
This description should provide a detailed understanding of the
algorithm and of the analysis parameters that were used, in order to
guarantee interpretation and reproducibility.

**#Software_Repository:** The URL of any repository or archive where the
Software executable release can be obtained.

**#Software_PreferredCitationID:** The Unique Identifier for the
preferred/primary publication describing this Software. Examples include
Digital Object Identifier (DOI), PubMed Central Identifier (PMCID),
ArXiv.org ID etc,.

**#Additional_Tables:** List of the additional tables being submitted. Note: use a comma to separate each table name from the next. E.g., AddTable1, AddTable2, AddTableN

**##Columns:=** List of the data column headers used in the table. Note: enclose the column headers and use a comma to separate each header name from the next. E.g., \ (C1, C2, C3, Cn)


Additional required header lines by table type
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.. list-table:: List of **mandatory** and *conditionally required* header fields
   :header-rows: 1
   :widths: 10 20 70
   :width: 100%

   * - Table Number
     - Table Name
     - Header Fields
   * - 1
     - :ref:`core`
     - **Genome_Assembly**
   * - 2
     - :ref:`demultiplexing`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 3
     - :ref:`quality`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 4
     - :ref:`trace`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 5
     - :ref:`bio`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 6
     - :ref:`rna`
     - **Genome_Assembly**, **Gene_ID_Type**, *Transcript_ID_Type* 
   * - 7
     - :ref:`rna_quality`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 8
     - :ref:`rna_bio`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 9
     - :ref:`cell`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 10
     - :ref:`subcell`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 11
     - :ref:`extracell`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 12
     - :ref:`mapping`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 1v
     - :ref:`vol-core`
     - **Genome_Assembly**
   * - 2v
     - :ref:`undecoded`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*
   * - 3v
     - :ref:`vol-quality`
     - *Time_Unit*, *Intensity_Measurement_Method*, *Intensity_Unit*

**Legend:** Header field names in **bold** are **mandatory** in the indicated table. Header fields in *italics* are *conditionally required* in the indicated table depending on the experiment type.

Genome_Assembly
"""""""""""""""

.. tip:: For genomic coordinates, it is recommended to use GRCh38 for human and GRCm38 for mouse. For other species, follow these `instructions. <https://data.4dnucleome.org/search/?type=Organism>`_ In addition, in case the genome under study contains INSERTION/DELETIONs, also follow these :ref:`IN_DEL-reference-label`.

Metrics Units
"""""""""""""

.. note:: In addition to the **##XYZ_Unit=** Other units-related header lines are also *conditionally required* for all other :ref:`BAS-table-reference-label` and :ref:`VOL-table-reference-label` that are included in the deposition in case relevant metrics are reported (e.g., the ``##Time_Unit=`` field is required if a time measure is reported).


.. _columns-reference-label:
Data Columns
------------

- Tables contain **required**, *conditionally-required*, and optional columns.
- Conditionally-required columns are columns that are required when certain
  conditions are met (e.g., ``Cell_ID`` is required any time the experiment
  involves the identification of Cell boundaries).
- Column names **MUST** use the underscore ``_`` as a word separator (e.g., ``Spot_ID``).
- The first column is always either ``Spot_ID``, ``Loc_ID``, ``RNA_Spot_ID``or another relevant ID (i.e., ``Trace_ID``, ``Cell_ID``, etc.). 
- The following tables have additional mandatory columns that do need to be specified in the header: :ref:`core`, :ref:`demultiplexing`, :ref:`rna` and :ref:`mapping`
- Unless otherwise specified, the order of all Optional Columns is at the user's discretion.
- The order of the rows is at the user's discretion.

