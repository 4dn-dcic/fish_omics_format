Cell/ROI Mapping table (optional)
---------------------------------

This table is used to provide the boundaries of Cells and other ROIs
identified as part of this experiment.

The table is organized on a Cell/ROI basis via a Cell/ROI ID and
provides the Cell/ROI boundaries in global coordinates as specified by
the OME ROI data model
(https://docs.openmicroscopy.org/ome-model/5.6.3/developers/roi.html).

This table might be organized in one of the following manner:

-  Cell_ID → Cell boundaries in global coordinates (following the OME
   Data Model for Polygon - ROI, the Cell boundaries are defined as a
   list of comma separated x,y coordinates separated by spaces like
   "x1,y1 x2,y2 x3,y3" e.g. "0,0 1,2 3,5").
-  Sub_Cell_ROI_ID → Sub-cellular ROI (e.g., Nuclear feature, Nucleolus,
   etc.,) boundaries x/y/z in global coordinates (following the OME Data
   Model for Polygon - Sub_Cell ROI, boundaries are defined as a list of
   comma separated x,y coordinates separated by spaces like "x1,y1 x2,y2
   x3,y3" e.g. "0,0 1,2 3,5"). This table might also report the feature
   brightness.
-  Extra_Cell_ROI_ID → Extracellular ROI boundaries (e.g., Tissue) in
   global coordinates (following the OME Data Model for Polygon - ROI,
   Super-Cell ROI boundaries are defined as a list of comma separated
   x,y coordinates separated by spaces like "x1,y1 x2,y2 x3,y3" e.g.
   "0,0 1,2 3,5").

In addition, this table might be used to report additional vectorial
properties such as:

-  Lists of RNA Spot x/y/z in global coordinates,
-  Lists of barcode sequence ID
-  Lists of channels

Example
~~~~~~~

.. code::

  ##FOF-CT_version=v0.1
  ##XYZ_unit=micron
  ##intensity_unit=a.u.
  ##Sub_Cell_ROI_type=PML_body
  ##ROI_boundaries_format=(X1,Y1, X2,Y2 Xn,Yn)
  #^ROI_volume: the volume of this ROI expressed in micron^3.
  #^ROI_intensity: the integrated average signal intensity measured within the boundaries of this ROI, of the marker used to identify this nuclear feature.
  #additional_tables: DNA_Spot/Trace_Data.csv, RNA_Spot_Data.csv, Global_Trace_Data.csv
  #columns=(Sub_Cell_ROI_ID, Cell_ID, ROI_boundaries, ROI_volume, ROI_intensity)
  1, 1, (0,0 1,2 3,5)
  2, 1, (0,0 2,3 4,6)
  3, 2, (0,0 3,2 7,5)
  4, 3, (0,0 9,2 9,5)

Specifications
~~~~~~~~~~~~~~

.. list-table:: File Header
  :header-rows: 1

  * - Name
    - Description
    - Example
    - Conditional requirement conditions
  * - **##FOF-CT_version=**
    - Version of the FOF format used in this case.
    - v0.1
    -
  * - **##Table_namespace=**
    - 4dn_FOF-CT_mapping
    -
    -
  * - #lab_name:
    - name of the lab where the experiment was performed.
    - Nobel
    -
  * - #experimenter_name:
    - name of the person performing the experiment.
    - John Doe
    -
  * - **#experimenter_contact:**
    - email address of the person performing the experiment.
    - john.doe@email.com
    -
  * - **#description:**
    - A free-text, description of the experiment and of the data recorded in this table. This description should provide a clear understanding of the process utilized to produce the data and contain sufficient details to ensure interpretation and reproducibility.
    -
    -
  * - **#Software_Title:**
    - The name of the Software(s) that were used in this case for localizing individual FISH-omics bright Spots and/or to produce three-dimensional (3D) polymeric chromatin Traces.
    - ChrTracer3
    -
  * - **#Software_Type:**
    - The type of this Software. Allowed values: SpotLoc, Tracing, SpotLoc+Tracing, Segmentation, QC, Other
    - SpotLoc+Tracing
    -
  * - **#Software_Authors:**
    - The Name(s) of the individual Author(s) of this Software. In case there are more than one Authors, individual names should be listed as follows, Doe, John; Smith, Jane; etc,.
    - Mateo, LJ; Sinnott-Armstrong, N; Boettiger, AN
    -
  * - **#Software_Description:**
    - A free-text, description of this Software. This description should provide a detailed understanding of the algortithm and of the analysis parameters that were used, in order to guarantee interpretation and reproducibility.
    - ChrTracer3 software was developed for analysis of raw DNA labeled images. As an input, it takes an.xlsx table containing information and folder names of the DNA experiment. As an output, it returns tab delimited.txt ﬁles with drift-corrected x, y, z positions for all labeled barcodes. These can be used directly to calculate the nm scale distances between all pairs of labeled loci. The current version of the software as of this writing is ChrTracer3.
    -
  * - **#Software_Repository:**
    - The URL of any repository or archive where the Software executable release can be obtained.
    - https://github.com/BoettigerLab/ORCA-public
    -
  * - **#Software_PreferredCitationID:**
    - The Unique Identifier for the preferred/primary publication describing this Software. Examples include, Digital Object Identifier (DOI), PubMed Central Identifier (PMCID), ArXiv.org ID etc,.
    - https://doi.org/10.1038/s41596-020-00478-x
    -
  * - **#additional_tables:**
    - list of the additional tables being submitted. Note: use a comma to separate each table name from the next.
    - DNA_Spot/Trace_Data.csv, RNA_Spot_Data.csv, Spot_Quality_Data.csv, Spot_Biological_Data.csv, Global_Trace_Data.csv
    -
  * - *#Intensity_measurement_method:*
    - If relevant, the method that was used to performed intensity measurements. In particular, sufficient information should be provided to document how digital intensity signals were converted in Photon conunts.
    - Spot centroid intensity.
    - Conditional requirement: this MUST be reported if any intensity metrics are reported.
  * - #^optional_column_1:
    - optional column 1 description
    -
    -
  * - #^optional_column_2:
    - optional column 2 description
    -
    -
  * - #^optional_column_3:
    - optional column 3 description
    -
    -
  * - **##XYZ_unit=**
    - If relevant, the unit used to represent XYZ locations or distances in this table. Note: use micron (instead of µm) to avoid problem with special, Greek symbols. Other allowed values are: nm, mm etc.
    - micron
    -
  * - *##time_unit=*
    - If relevant, the unit used to represent a time interval. Note: use “sec” for seconds, “msec” for milliseconds, “min” for minutes, and “hr” for hours.
    - sec
    - Conditional requirement: this MUST be reported if any time metrics are reported.
  * - *##intensity_unit=*
    - If relevant, the unit used to represent intensity measurements.
    - a.u.
    - Conditional requirement: this MUST be reported if any intensity metrics are reported.
  * - *##Sub_Cell_ROI_type=*
    - This field records the type of extracellular structure ROIs used in this table represent. The value utilized should belong to this list: Nucleolus, NL, PML_body, Cajal_body, Chromosome_Domain, Other
    - Nucleolus
    - Conditional requirement: this MUST be reported in any Sub_Cell ROI is idenfied as part of this experiment.
  * - *##Extra_Cell_ROI_type=*
    - This field records the type of extracellular structure ROIs used in this table represent. The value utilized should belong to this list: Tissue, Organoid, Other
    - Tissue
    - Conditional requirement: this MUST be reported in any Super_Cell ROI is idenfied as part of this experiment.
  * - **##ROI_boundaries_format=**
    - This field describes the format that is used to record the boundaries of the ROI in global coordinates. It is strongly recommended ot use the format defined by the OME Data Model to describe ROI (https://docs.openmicroscopy.org/ome-model/5.6.3/developers/roi.html).
    - (X1,Y1, X2,Y2 Xn,Yn)
    -
  * - **##columns=**
    - list of the data column headers used in the table. Note: enclose the column headers and use a comma to separate each header name from the next.
    - (Spot_ID, X, Y, Z)
    -

.. list-table:: Data Columns
  :header-rows: 1

  * - Name
    - Description
    - Example
    - Conditional requirement conditions
  * - *Sub_Cell_ROI_ID*
    - This fields reports the unique identifier for a Region of Interest (ROI) that represents the boundaries of a sub-cellular structure identified as part of this experiment. Note: this is used to connect all Spots, and Traces that belong to the same ROI.
    - 1
    - Conditional requirement: This table must have at least one of the ID columns. Sub_Cell_ROI_ID MUST be reported if this table contains subcellular ROI data
  * - *Cell_ID*
    - This fields reports the unique identifier for Region of Interest (ROI) that represent the boundaries of a Cell identified as part of this experiment. Note: this is used to connect individual Spots or Traces that are part of the same Cell.
    - 1
    - Conditional requirement: This table must have at least one of the ID columns. Cell_ID MUST be reported if this table contains Cell data
  * - *Extra_Cell_ROI_ID*
    - This fields reports the unique identifier for a Region of Interest (ROI) that represents the boundaries of a extracellular structure (e.g., Tissue) identified as part of this experiment. Note: this is used to connect all Spots, and Traces that belong to the same ROI.
    - 1
    - Conditional requirement: This table must have at least one of the ID columns. Extra_Cell_ROI_ID MUST be reported if this table contains extracellular ROI data.
  * - optional_column_1
    -
    -
    -
  * - optional_column_2
    -
    -
    -
  * - optional_column_3
    -
    -
    -
