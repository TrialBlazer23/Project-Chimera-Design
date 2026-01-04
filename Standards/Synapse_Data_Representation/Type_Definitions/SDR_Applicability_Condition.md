## SDR_Applicability_Condition

**SDR Type Name:** [[SDR_Applicability_Condition]]

**Description:** Defines a set of conditions that determine when a rule, guideline (like an `[[SDR_Ethical_Guideline]]`), or policy is applicable. This can involve logical combinations of situational factors or properties.

**Fields:**

| Field Name                  | Data Type                         | Multiplicity | Description                                                                                                     |
| :-------------------------- | :-------------------------------- | :----------- | :-------------------------------------------------------------------------------------------------------------- |
| `Applicability_Cond_UID`    | `Synapse_UID`                     | `1`          | Unique identifier for this specific applicability condition instance.                                             |
| `Condition_Description_UID` | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a human-readable summary of the condition.                           |
| `Logical_Operator`          | `Synapse_String`                  | `0..1`       | For complex conditions: "AND", "OR", "NOT". If absent, implies a single condition group.                        |
| `Condition_Clauses_UIDs`    | `List<Synapse_UID>`               | `1..*`       | List of UIDs, each pointing to an `[[SDR_Condition_Clause]]` or another nested `[[SDR_Applicability_Condition]]`. |
| `Applicability_Metadata`    | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this applicability condition.                               |