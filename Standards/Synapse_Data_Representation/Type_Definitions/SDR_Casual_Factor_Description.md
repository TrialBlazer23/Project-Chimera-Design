## SDR_Causal_Factor_Description

**SDR Type Name:** [[SDR_Causal_Factor_Description]]

**Description:** Details a specific factor identified by the Diagnostician as a contributing cause to an anomaly, error, or system issue. This is a key component of `[[SDR_Root_Cause_Analysis_Output]]`.

**Fields:**

| Field Name                    | Data Type                         | Multiplicity | Description                                                                                                                               |
| :---------------------------- | :-------------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------- |
| `Causal_Factor_UID`           | `Synapse_UID`                     | `1`          | Unique identifier for this specific causal factor description instance.                                                                   |
| `Factor_Description_UID`      | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a detailed explanation of the causal factor and how it contributed to the issue.                 |
| `Contributing_Elements_UIDs`  | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to specific components (`[[SDR_Vocabulary_Term]]` for model UIDs, task UIDs, etc.), data (`[[SDR_Data_Reference]]`), or processes involved in this cause. |
| `Confidence_In_Causation_UID` | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Confidence_Score_Item]]` indicating the Diagnostician's confidence that this factor was indeed causal.                  |
| `Supporting_Evidence_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Performance_Log_Entry]]` instances, `[[SDR_Anomaly_Report]]` details, or other data that supports this causal determination. |
| `Factor_Type_UID`             | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` categorizing the type of cause (e.g., "SoftwareBug", "HardwareFailure", "DataCorruption", "ConfigurationError", "ExternalInfluence"). |
| `Causal_Factor_Metadata`      | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this causal factor description.                                                       |