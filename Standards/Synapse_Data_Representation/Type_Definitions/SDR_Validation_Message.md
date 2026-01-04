## SDR_Validation_Message

**SDR Type Name:** [[SDR_Validation_Message]]

**Description:** Represents a single message (e.g., error, warning, informational) generated as part of an `[[SDR_Validation_Result]]`.

**Fields:**

| Field Name                    | Data Type                  | Multiplicity | Description                                                                                                                               |
| :---------------------------- | :------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------- |
| `Validation_Msg_UID`          | `Synapse_UID`              | `1`          | Unique identifier for this specific validation message instance.                                                                          |
| `Message_Code_UID`            | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` providing a standardized code for the message type (e.g., "SyntaxError", "ValueOutOfRange", "MissingRequiredField"). |
| `Severity_Level_UID`          | `Synapse_UID`              | `1`          | UID of an `[[SDR_Vocabulary_Term]]` indicating the severity of the message (e.g., "Error", "Warning", "Information", "Debug").               |
| `Message_Text_UID`            | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` containing the human-readable content of the validation message.                                             |
| `Affected_Data_Path_SDR_UID`  | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Data_Path_Expression]]` pinpointing the specific data element or field within the validated item that this message pertains to. |
| `Suggested_Resolution_Text_UID`| `Synapse_UID`             | `0..1`       | UID of an `[[SDR_Text_Block]]` offering a suggestion on how to resolve the issue identified by the message.                               |
| `Validation_Msg_Metadata`     | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this validation message.                                                                |