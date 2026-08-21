.. _IN_DEL-reference-label:
  
Instructions for when the genome under study is modified
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Instructions for reporting the location of Single Molecule (SM) Localization events, DNA Spots and Traces in case the genome under study contains insertions or deletions:

#. Add the ``custom-build`` prefix to the genome build name and introduce a descriptive name detailing the nature of the genome modification.
#. Insert the following additional fields in the File header
#. ``##Modification=`` to indicate the nature and location of the modification
#. ``##VCF_File_Name=`` to indicate the name of the mandatory `Variant Call Format (VCF) <https://samtools.github.io/hts-specs/VCFv4.2.pdf>`_ file to be included with the FOF-CT dataset to report the nature and location of the genome modification.
#. ``##VCF_Version=`` to indicate the VCF version used for the VCF file describing the nature and location of the genome modification.

   - Attach a separate `VCF <https://samtools.github.io/hts-specs/VCFv4.2.pdf>`_ file with your FOF-CT dataset to describe the nature and location of the genome modification.
   - In the ``Chrom`` column insert the name of the inserted or deleted DNA fragment.
   - In the ``Chrom_Start`` and ``Chrom_End`` columns insert the Start and End coordinates of the target chromosome segment with respect to the INSERTION or DELETION.