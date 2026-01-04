## SDR_Rule_Set_Reference

**SDR Type Name:** [[SDR_Rule_Set_Reference]]

**Description:** Provides a reference to a defined set of rules, often used for validation (`[[SDR_Validation_Result]]`), decision-making logic, or operational constraints.

**Fields:**

| Field Name               | Data Type                  | Multiplicity | Description                                                                                               |
| :----------------------- | :------------------------- | :----------- | :-------------------------------------------------------------------------------------------------------- |
| `Rule_Set_Ref_UID`       | `Synapse_UID`              | `1`          | Unique identifier for this specific rule set reference instance.                                          |
| `Rule_Set_Name_UID`      | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a human-readable name for the rule set.                        |
| `Rule_Set_Identifier_URI`| `Synapse_String`           | `0..1`       | A URI or other persistent identifier pointing to the rule set definition if it's managed externally.      |
| `Internal_Rule_Set_SDR_UID`| `Synapse_UID`            | `0..1`       | UID of an internal SDR instance (e.g., an `[[SDR_Rule_Collection]]`) that defines the rule set within Synapse. *(Introduces `SDR_Rule_Collection`)* |
| `Rule_Set_Version`       | `Synapse_String`           | `0..1`       | Optional version string for the referenced rule set.                                                      |
| `Rule_Set_Description_UID`| `Synapse_UID`             | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a brief description of the rule set's purpose or scope.        |
| `Rule_Set_Ref_Metadata`  | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR