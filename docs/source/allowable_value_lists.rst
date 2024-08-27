Allowable value lists
=====================
Τhe following is a list of fields whose values have to be drawn from allowable values lists.

.. list-table::
  :header-rows: 1

  * - Number
    - Field Name
    - Description
    - Allowable Values
    - Example Values
    - Default Value
  * - 1
    - ``XYZ_unit``
    - The unit used to represent XYZ locations or distances. 
    - SI units of `Length <https://en.wikipedia.org/wiki/SI_base_unit>`_
    - nm, micron, mm, etc.
    - micron
  * - 2
    - ``Time_unit``
    - The unit used to represent a time interval.
    - SI units of `Time <https://en.wikipedia.org/wiki/SI_base_unit>`_
    - ms, s, min, hr, etc.
    - s
  * - 3
    - ``Cell_Type``
    - The type of cells reported in this table.
    - It is recommended to use an ontology term for example from the `EFO <http://www.ebi.ac.uk/efo/EFO_0000324>`_ ontology  
    - Primary cell line, Immortal cell line, Induced pluripotent stem (IPS) cell, Cell in tissue, Cell in organoid, Other.
    - Not Applicable
  * - 4
    - ``Sub-Cell_ROI_Type``
    - The type of sub-cellular structure ROIs reported in this table.
    - It is recommended to use an ontology term such as a child of the `EFO 'cellular_component' term <http://purl.obolibrary.org/obo/GO_0005575>`_  
    - Nucleolus, Nuclear Lamina (NL), Nuclear Pore Complex (NPC) PML_body, Cajal_body, Chromosome_Domain, etc.
    - Not Applicable
  * - 5
    - ``Extra-Cell_ROI_Type``
    - The type of extracellular structure ROIs reported in this table.
    - It is recommended to use an ontology term such as a child of the `EFO 'organism part' term <http://www.ebi.ac.uk/efo/EFO_0000635>`_  
    - Tissue, Organoid, etc.
    - Not Applicable