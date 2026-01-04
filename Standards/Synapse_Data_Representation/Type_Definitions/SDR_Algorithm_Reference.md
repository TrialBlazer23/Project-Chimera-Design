## SDR_Algorithm_Reference

**SDR Type Name:** [[SDR_Algorithm_Reference]]

**Description:** Provides a reference to a specific algorithm or computational method, potentially including its version and source or specification. Used by `[[SDR_Performance_Metric_Definition]]` to specify calculation methods.

**Fields:**

| Field Name                 | Data Type                  | Multiplicity | Description                                                                                                  |
| :------------------------- | :------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------- |
| `Algorithm_Ref_UID`        | `Synapse_UID`              | `1`          | Unique identifier for this specific algorithm reference instance.                                            |
| `Algorithm_Name_UID`       | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` providing the name of the algorithm.             |
| `Algorithm_Version`        | `Synapse_String`           | `0..1`       | Optional version identifier for the algorithm.                                                               |
| `Specification_Source_UID` | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` (e.g., a URI to a paper, documentation) or `[[SDR_Internal_Object_Reference]]` if defined within Synapse. *(Introduces `SDR_Internal_Object_Reference`)* |
| `Algorithm_Description_UID`| `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` briefly describing the algorithm's purpose or function.                     |
| `Algorithm_Parameters_SDR_UID`| `Synapse_UID`           | `0..1`       | UID of an `[[SDR_Parameter_Set]]` if this reference implies a specific configuration of the algorithm.        |
| `Algorithm_Ref_Metadata`   | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this algorithm reference.                                |