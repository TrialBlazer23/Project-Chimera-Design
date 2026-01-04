## SDR_Story_Arc

**SDR Type Name:** [[SDR_Story_Arc]]

**Description:** Defines a major plotline or character journey within the overall narrative, outlining its progression and key turning points.

**Fields:**

| Field Name                   | Data Type                         | Multiplicity | Description                                                                                                                              |
| :--------------------------- | :-------------------------------- | :----------- | :--------------------------------------------------------------------------------------------------------------------------------------- |
| `Story_Arc_UID`              | `Synapse_UID`                     | `1`          | Unique identifier for this specific story arc.                                                                                           |
| `Arc_Title_Or_Summary_UID`   | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a title or concise summary of the arc.                                                          |
| `Arc_Type_UID`               | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` indicating the type of arc (e.g., "MainPlot", "SubPlot", "CharacterArc_Protagonist", "RomanceArc").     |
| `Key_Plot_Points_SDR_UIDs`   | `List<Synapse_UID>`               | `1..*`       | List of UIDs, each pointing to an `[[SDR_Plot_Point]]` that defines the critical events and turning points in this arc.                  |
| `Primary_Characters_Involved_UIDs` | `List<Synapse_UID>`           | `0..*`       | List of UIDs pointing to `[[SDR_Character_Profile]]` UIDs for characters central to this arc.                                           |
| `Thematic_Contribution_Text_UID`| `Synapse_UID`                  | `0..1`       | UID of an `[[SDR_Text_Block]]` explaining how this arc contributes to the overall themes of the narrative.                               |
| `Arc_Resolution_Desc_UID`    | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` describing the intended resolution or outcome of this arc.                                                |
| `Story_Arc_Metadata`         | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this story arc.                                                                                   |