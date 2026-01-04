## SDR_Fact_Assertion

**SDR Type Name:** [[SDR_Fact_Assertion]]

**Description:** Represents a piece of factual information or a statement asserted as true (or otherwise qualified) within the narrative context. Referenced by `[[SDR_Plot_Point]]` for information revealed.

**Fields:**

| Field Name                      | Data Type                  | Multiplicity | Description                                                                                                                                |
| :------------------------------ | :------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| `Fact_Assertion_UID`            | `Synapse_UID`              | `1`          | Unique identifier for this fact assertion.                                                                                                 |
| `Statement_Text_UID`            | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` containing the factual statement.                                                                           |
| `Source_In_Narrative_Desc_UID`  | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Character_Profile]]` UID describing how or by whom this fact is revealed or known within the narrative. |
| `Truth_Status_In_Narrative_UID` | `Synapse_UID`              | `1`          | UID of an `[[SDR_Vocabulary_Term]]` indicating its status within the narrative (e.g., "ObjectivelyTrue_InWorld", "BelievedBy_CharacterX", "Rumor_Unconfirmed", "Misinformation"). |
| `Supporting_Evidence_Ref_UIDs`  | `List<Synapse_UID>`        | `0..*`       | List of UIDs pointing to `[[SDR_Data_Reference]]`s or other facts within the narrative that support this assertion.                           |
| `Relevance_To_Plot_Text_UID`    | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` explaining its relevance or importance to the plot.                                                           |
| `Fact_Assertion_Metadata`       | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this fact assertion.                                                                                |