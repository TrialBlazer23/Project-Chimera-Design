## SDR_Proposition_Statement

**SDR Type Name:** [[SDR_Proposition_Statement]]

**Description:** Represents a declarative statement that can be asserted as a claim, premise, or conclusion within an [[SDR_Argument_Structure]]. It can have an associated truth value or degree of belief.

**Fields:**

| Field Name                  | Data Type                  | Multiplicity | Description                                                                                                |
| :-------------------------- | :------------------------- | :----------- | :--------------------------------------------------------------------------------------------------------- |
| `Proposition_UID`           | `Synapse_UID`              | `1`          | Unique identifier for this specific proposition statement instance.                                        |
| `Statement_Text_UID`        | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` containing the content of the statement.                                  |
| `Asserted_Truth_Value`      | `Synapse_String`           | `0..1`       | The asserted truth value (e.g., "True", "False", "Uncertain", "Probable"). From an `[[SDR_Vocabulary_Term]]`. |
| `Degree_Of_Belief_UID`      | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Confidence_Score_Item]]` representing the system's or source's degree of belief in this proposition. |
| `Epistemic_Status_UID`      | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` indicating its epistemic status (e.g., "Fact", "Hypothesis", "Opinion"). |
| `Proposition_Metadata`      | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this proposition statement.                            |