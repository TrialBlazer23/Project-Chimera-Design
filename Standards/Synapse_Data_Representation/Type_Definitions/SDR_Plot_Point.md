## SDR_Plot_Point

**SDR Type Name:** [[SDR_Plot_Point]]

**Description:** Represents a specific event, scene, or significant moment within a story arc that advances the plot or develops characters.

**Fields:**

| Field Name                      | Data Type                         | Multiplicity | Description                                                                                                                                |
| :------------------------------ | :-------------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| `Plot_Point_UID`                | `Synapse_UID`                     | `1`          | Unique identifier for this plot point.                                                                                                     |
| `Plot_Point_Summary_UID`        | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a concise summary of what happens at this plot point.                                             |
| `Associated_Scene_SDR_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Scene_Description]]` if this plot point corresponds directly to a single scene.                                         |
| `Sequence_In_Arc`               | `Synapse_Integer`                 | `0..1`       | Optional numerical order of this plot point within its parent `[[SDR_Story_Arc]]`.                                                          |
| `Impact_On_Narrative_Text_UID`  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` describing the significance of this plot point to the story arc or overall narrative.                     |
| `Emotional_Beat_Target_UID`     | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` or `[[SDR_Text_Block]]` describing the intended emotional impact on the audience (e.g., "Suspense", "Relief", "Joy"). |
| `Key_Information_Revealed_UIDs` | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Text_Block]]`s or `[[SDR_Fact_Assertion]]`s detailing crucial info revealed. *(Introduces `SDR_Fact_Assertion`)* |
| `Plot_Point_Metadata`           | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this plot point.                                                                                    |