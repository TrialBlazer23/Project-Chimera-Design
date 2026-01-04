## SDR_Storyboard_Definition

**SDR Type Name:** [[SDR_Storyboard_Definition]]

**Description:** A collection of `[[SDR_Storyboard_Panel]]` instances that together form a visual sequence for a scene, act, or entire narrative. Referenced by `[[SDR_Storyboard_Panel]]` (as parent).

**Fields:**

| Field Name                       | Data Type                         | Multiplicity | Description                                                                                                                                |
| :------------------------------- | :-------------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| `Storyboard_Def_UID`             | `Synapse_UID`                     | `1`          | Unique identifier for this storyboard definition.                                                                                          |
| `Storyboard_Title_Or_Sequence_Name_UID` | `Synapse_UID`                | `1`          | UID of an `[[SDR_Text_Block]]` providing a title for the storyboard or naming the sequence it represents (e.g., "OpeningChaseSequence", "Act1Storyboard"). |
| `Associated_Narrative_Context_UID`| `Synapse_UID`                    | `0..1`       | UID of an `[[SDR_Narrative_Blueprint]]`, `[[SDR_Story_Arc]]`, or `[[SDR_Scene_Description]]` that this storyboard visualizes.           |
| `Storyboard_Description_Text_UID`| `Synapse_UID`                    | `0..1`       | UID of an `[[SDR_Text_Block]]` providing an overall description or purpose for this storyboard.                                          |
| `Panel_Order_SDR_UIDs`           | `List<Synapse_UID>`               | `1..*`       | Ordered list of UIDs, each pointing to an `[[SDR_Storyboard_Panel]]` instance in the correct sequence.                                   |
| `Storyboard_Version`             | `Synapse_String`                  | `0..1`       | Optional version identifier for this storyboard (e.g., "v1.0", "RoughDraft_v2").                                                         |
| `Storyboard_Def_Metadata`        | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this storyboard definition.                                                                       |