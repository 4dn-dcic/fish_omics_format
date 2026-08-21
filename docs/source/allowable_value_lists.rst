Allowable value lists
=====================
The following is a list of fields whose values have to be drawn from allowable values lists.

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
    - ``Software_Type``
    - The type of this Software used to produce results recorded in this table.
    - Distance Calculation, DriftCorrection, Precision Assessment, Segmentation, Single Molecule Localization, SpotLoc, SpotLoc+Tracing, Tracing, Other
    - Not Applicable
    - Not Applicable
  * - 3
    - ``Time_unit``
    - The unit used to represent a time interval.
    - SI units of `Time <https://en.wikipedia.org/wiki/SI_base_unit>`_
    - ms, s, min, hr, etc.
    - s
  * - 4
    - ``Cell_Type``
    - The type of cells reported in the :ref:`cell`.
    - It is recommended to use an ontology term for example from the `EFO <http://www.ebi.ac.uk/efo/EFO_0000324>`_ ontology  
    - Primary cell line, Immortal cell line, Induced pluripotent stem (IPS) cell, Cell in tissue, Cell in organoid, Other.
    - Not Applicable
  * - 5
    - ``Sub_Cell_ROI_Type``
    - The type of sub-cellular structure ROIs reported in the :ref:`subcell`.
    - It is recommended to use an ontology term such as a child of the `GO 'cellular_component' term <http://purl.obolibrary.org/obo/GO_0005575>`_  
    - Nucleolus, Nuclear Lamina (NL), Nuclear Pore Complex (NPC) PML_body, Cajal_body, Chromosome_Domain, etc.
    - Not Applicable
  * - 6
    - ``Extra_Cell_ROI_Type``
    - The type of extracellular structure ROIs reported in the :ref:`extracell`.
    - It is recommended to use an ontology term such as a child of the `EFO 'organism part' term <http://www.ebi.ac.uk/efo/EFO_0000635>`_  
    - Tissue, Organoid, etc.
    - Not Applicable
  * - 7
    - ``ROI_Boundaries_Format_Type``
    - The type of ROI boundaries reporting format used in the :ref:`mapping`.
    - OME_Polygon, OME_Mask, Mesh_OBJ, Mesh_STL, Mesh_PLY, GeoJSON, WKT, Label_Mask_Image, Other
    - Not Applicable
    - OME_Polygon