## SDR_Metadata_Block

**SDR Type Name:** [[SDR_Metadata_Block]]

**Description:** A standardized block of metadata fields that can be included in other SDR structures to provide common contextual information about the data payload it's associated with.

**Fields:**

| Field Name                | Data Type                       | Multiplicity | Description                                                                                                   |
| :------------------------ | :------------------------------ | :----------- | :------------------------------------------------------------------------------------------------------------ |
| `Metadata_UID`            | `Synapse_UID`                   | `1`          | Unique identifier for this specific instance of metadata.                                                     |
| `Parent_SDR_UID`          | `Synapse_UID`                   | `1`          | The UID of the SDR instance this metadata block belongs to.                                                   |
| `Source_Model_UID`        | `Synapse_UID`                   | `0..1`       | The UID of the AI family member that originated or is the primary source of the parent SDR data.              |
| `External_Source_ID`      | `[[SDR_Text_Block]]`            | `0..1`       | UID of an SDR_Text_Block. Identifier for an external source if the data originated outside the AI family.     |
| `Creation_Timestamp`      | `Synapse_Timestamp`             | `1`          | The exact date and time when the parent SDR data instance was created.                                        |
| `Last_Modified_Timestamp` | `Synapse_Timestamp`             | `0..1`       | The exact date and time when the parent SDR data instance was last modified.                                  |
| `Version_Number`          | `Synapse_Integer`               | `0..1`       | Version number for the parent SDR data, if applicable (e.g., for evolving documents or concepts).             |
| `Confidence_Score`        | `[[SDR_Confidence_Score_Item]]` | `0..1`       | UID of an SDR_Confidence_Score_Item. The assessed confidence in the accuracy/validity of the parent SDR data. |
| `Access_Control_Tags`     | `List<[[SDR_Access_Tag]]>`      | `0..*`       | UID list of SDR_Access_Tags. Optional tags for future access control or sensitivity handling.                 |
| `Processing_Log_UIDs`     | `List<Synapse_UID>`             | `0..*`       | List of UIDs pointing to [[SDR_Processing_Log_Entry]] instances detailing significant processing steps.       |