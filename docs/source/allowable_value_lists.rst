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
    - nm, micron, mm (closed list)
    - nm, micron, mm
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
    - ms, msec, s, sec, min, hr (closed list)
    - ms, msec, s, sec, min, hr
    - sec
  * - 4
    - ``Cell_Type``
    - The type of cells reported in the :ref:`cell`.
    - MUST be reported as an ontology term ID (CURIE) followed by its human-readable label in parentheses, in the format ``ID (Label)`` -- for example from the `EFO <http://www.ebi.ac.uk/efo/EFO_0000324>`_ ontology -- or the literal value ``Other`` when no ontology term applies
    - ``EFO:XXXXXXX`` (Primary cell line), ``EFO:XXXXXXX`` (Immortal cell line), ``EFO:XXXXXXX`` (Induced pluripotent stem (IPS) cell), ``EFO:XXXXXXX`` (Cell in tissue), ``EFO:XXXXXXX`` (Cell in organoid), ``Other``
    - Not Applicable
  * - 5
    - ``Sub_Cell_ROI_Type``
    - The type of sub-cellular structure ROIs reported in the :ref:`subcell`.
    - MUST be reported as an ontology term ID (CURIE) followed by its human-readable label in parentheses, in the format ``ID (Label)`` -- such as a child of the `GO 'cellular_component' term <http://purl.obolibrary.org/obo/GO_0005575>`_ -- or the literal value ``Other`` when no ontology term applies
    - ``GO:0005730`` (Nucleolus), ``GO:0005652`` (Nuclear Lamina (NL)), ``GO:0005643`` (Nuclear Pore Complex (NPC)), ``GO:0016605`` (PML_body), ``GO:0015030`` (Cajal_body), ``GO:XXXXXXX`` (Chromosome_Domain), ``Other``
    - Not Applicable
  * - 6
    - ``Extra_Cell_ROI_Type``
    - The type of extracellular structure ROIs reported in the :ref:`extracell`.
    - MUST be reported as an ontology term ID (CURIE) followed by its human-readable label in parentheses, in the format ``ID (Label)`` -- such as a child of the `EFO 'organism part' term <http://www.ebi.ac.uk/efo/EFO_0000635>`_ (terms in this branch carry UBERON, not EFO, identifiers) -- or the literal value ``Other`` when no ontology term applies
    - ``UBERON:0000479`` (Tissue), ``EFO:XXXXXXX`` (Organoid), ``Other``
    - Not Applicable
  * - 7
    - ``ROI_Boundaries_Format_Type``
    - The type of ROI boundaries reporting format used in the :ref:`mapping`.
    - OME_Polygon, OME_Mask, Mesh_OBJ, Mesh_STL, Mesh_PLY, GeoJSON, WKT, Label_Mask_Image, Other
    - Not Applicable
    - OME_Polygon