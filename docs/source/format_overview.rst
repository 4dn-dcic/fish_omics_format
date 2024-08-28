Format description: overview
============================

.. contents::

General Info
------------

- The format is organized in multiple individual :ref:`table-reference-label`.
- The only mandatory table is the :ref:`core`.
- All other tables are either recommended for all experiment types, or optional depending on the experiment design and type.
- Each file must contain a single table.
- Accepted file formats for storing tables are txt, csv and tsv.
- An underscore ``_`` must be used as a word separator in header field
  names and column headers to improve readability while not violating
  common name restrictions in coding environments (dash ``-`` may be
  mistaken as subtraction of variables).
- Each file has two parts: file header and data columns.

.. tip:: If included all :ref:`table-reference-label`, except :ref:`core`, :ref:`demultiplexing`, :ref:`rna` and :ref:`mapping`, **MUST** contain at least 1 **Optional Column**.

.. _headers-reference-label:
File Header
-----------
- All tables have to contain a mandatory header section.
- In the file header, each line contains only one field.
- Header lines are denoted by ``#``. In particular:

  - ``##`` denotes machine readable header lines. These lines must follow the
    following format ``##Key1=Value1`` (e.g., ``##FOF-CT_version=v0.1``).
  - ``#`` denotes human readable header lines. These lines should follow the
    following format, ``#term: free text description`` (e.g.,
    ``#lab_name: name of the lab where the experiment was performed``).
  - ``#^`` denotes lines that define user specified **Optional Columns**.
    These lines provide the name of the column header and a description of the
    column content. Descriptions must be understandable and sufficient to ensure
    the interpretation and reproducibility of the results. These lines should
    follow the following format ``#^term: free text description`` (e.g.,
    ``#^optional_column_1: optional column 1 description``).

- Header names MUST use the underscore as a word separator (e.g., RNA_A_intensity).
- The file header contains **required**, *conditionally-required*, and optional fields.
- Conditionally-required fields are fields that are required when certains
  conditions are met (e.g., ``##intensity_unit=`` is required any time an
  intensity metric is reported).

Mandatory header lines (all tables)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**##FOF-CT_version=** Data format version number. E.g., v0.2

**##Table_namespace=** Identifier for this type of table. Value must be as in the example. E.g., 4dn_FOF-CT_core

**#Lab_Name:** Name of the lab where the experiment was performed

**#Experimenter_Name:** Name of the person performing the experiment

**#Experimenter_Contact:** Email address of the person performing the
experiment

**#Description:** A free-text, description of the experiment and of the
data recorded in this table. This description should provide a clear
understanding of the process utilized to produce the data and contain
sufficient details to ensure interpretation and reproducibility.

**#Additional_Tables:** List of the additional tables being submitted. Note: use a comma to separate each table name from the next. E.g., AddTable1, AddTable2, AddTableN

**##Columns:=** List of the data column headers used in the table. Note: enclose the column headers and use a comma to separate each header name from the next. E.g., \ (C1, C2, C3, Cn)


Additional conditionally required header lines 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

:ref:`core` and :ref:`rna` tables
"""""""""""""""""""""""""""""""""
In addition to all of the above, the following header line is required for the :ref:`core` and :ref:`rna` tables.

**##Genome_Assembly=** Genome build. E.g., GRCh38 

.. note:: \(1) the 4DN Data Portal only accepts GRCh38 for human and GRCm38 for mouse. For other species see the list of all 4DN allowable `genome builds <https://data.4dnucleome.org/search/?type=Organism>`_; (2) in case the genome under study contains an INSERTION or a DELETION, indicate this as indicated in :ref:`core`.

:ref:`core`, :ref:`demultiplexing`, :ref:`bio`, :ref:`rna`, :ref:`rna_bio`, and :ref:`mapping` tables
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
Further, the following header line is required for the :ref:`core`, :ref:`demultiplexing`, :ref:`bio`, :ref:`rna`, :ref:`rna_bio`, and :ref:`mapping` tables.

**##XYZ_Unit=** The unit used to represent XYZ locations or distances. Note: use micron to avoid problem with special, Greek symbols. Other allowed values *should* be drawn from SI units of `Length <https://en.wikipedia.org/wiki/SI_base_unit>`_. Examples: 'nm', 'micron' 'mm' etc.

.. note:: Other units related header lines are also *conditionally required* for all other :ref:`table-reference-label` in case relevant metrics are reported (e.g., the ``##Time_Unit=`` field is required if a time measure is reported).

:ref:`core`, :ref:`demultiplexing`, :ref:`rna`, :ref:`quality` and :ref:`rna_quality` tables
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
Finally, the following header lines are required for the :ref:`core`, :ref:`demultiplexing`, :ref:`rna`, :ref:`quality` and :ref:`rna_quality` tables.

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

.. note:: All Software related header lines are also *conditionally required* for all other :ref:`table-reference-label` in case Software is used for producing the reported results.


.. _columns-reference-label:
Data Columns
------------

- Tables contain **required**, *conditionally-required*, and optional columns.
- Conditionally-required columns are columns that are required when certain
  conditions are met (e.g., ``Cell_ID`` is required any time the experiment
  involves the identification of Cell boundaries).
- Column names should use the underscore ``_`` as a word separator (e.g., ``Spot_ID``).
- The first column is always either ``Spot_ID`` or another relevant ID (i.e., ``Trace_ID``, ``Cell_ID``, etc.). 
- The following tables have additional mandatory columns that do need to be specified in the header, :ref:`core`, :ref:`demultiplexing`, :ref:`rna` and :ref:`mapping`
- Unless otherwise specified, the order of all Optional Columns is at user's discretion.
- The order of the rows is at user's discretion.

