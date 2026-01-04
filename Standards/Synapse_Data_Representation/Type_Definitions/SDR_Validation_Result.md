## SDR_Validation_Result

**SDR Type Name:** [[SDR_Validation_Result]]

**Description:** Represents the outcome of a validation process performed on a piece of data, a query, or another SDR instance against a defined schema or set of rules.

**Fields:**

| Field Name                 | Data Type                         | Multiplicity | Description                                                                                                                                  |
| :------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| `Validation_Result_UID`    | `Synapse_UID`                     | `1`          | Unique identifier for this specific validation result instance.                                                                              |
| `Validation_Status_UID`    | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` indicating the overall result (e.g., "Valid", "Invalid", "ValidWithWarnings", "NotValidated").             |
| `Timestamp_Validated`      | `Synapse_Timestamp`               | `1`          | The exact date and time when the validation was performed.                                                                                   |
| `Validated_Item_SDR_UID`   | `Synapse_UID`                     | `1`          | UID of the SDR instance that was validated.                                                                                                  |
| `Schema_Or_Rules_Used_UID` | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Schema_Reference]]` or `[[SDR_Rule_Set_Reference]]` that was used for validation. *(Introduces `SDR_Rule_Set_Reference`)* |
| `Validation_Messages_UIDs` | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Validation_Message]]` detailing specific errors, warnings, or informational messages. *(Introduces `SDR_Validation_Message`)* |
| `Validation_Result_Metadata`| `[[SDR_Metadata_Block]]`         | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this validation result.                                                                  |