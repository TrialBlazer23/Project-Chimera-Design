## SDR_Data_Reference

**SDR Type Name:** [[SDR_Data_Reference]]

**Description:** A pointer to a specific SDR data instance that is required as input, output, or context for a task or operation. It may include information on how to access or interpret the referenced data.

**Fields:**

| Field Name            | Data Type                     | Multiplicity | Description                                                                                        |
| :-------------------- | :---------------------------- | :----------- | :------------------------------------------------------------------------------------------------- |
| `Data_Ref_UID`        | `Synapse_UID`                 | `1`          | Unique identifier for this data reference instance.                                                |
| `Referenced_SDR_UID`  | `Synapse_UID`                 | `1`          | The UID of the actual SDR data instance being referenced.                                          |
| `Referenced_SDR_Type` | `Synapse_String`              | `1`          | The declared SDR type name of the referenced data (e.g., "SDR_Knowledge_Graph_Element", "SDR_Image_Data"). Useful for validation. |
| `Role_In_Context`     | `[[SDR_Semantic_Tag]]`        | `0..1`       | UID of an SDR_Semantic_Tag. Describes the role of this data in the current context (e.g., "PrimaryInput", "SupportingEvidence"). |
| `Access_Instructions` | `[[SDR_Text_Block]]`          | `0..1`       | UID of an SDR_Text_Block. Optional instructions on how to access or query a subset of the referenced data. |
| `Data_Ref_Metadata`   | `[[SDR_Metadata_Block]]`      | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata associated with this data reference.             |