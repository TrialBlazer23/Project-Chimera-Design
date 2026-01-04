## SDR_Storyboard_Panel

**SDR Type Name:** [[SDR_Storyboard_Panel]]

**Description:** Defines a single panel or frame within a storyboard, outlining the visual composition, character actions, camera work, and other key elements for a shot or moment in a sequence.

**Fields:**

| Field Name                          | Data Type                         | Multiplicity | Description                                                                                                                                 |
| :---------------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
| `Storyboard_Panel_UID`              | `Synapse_UID`                     | `1`          | Unique identifier for this storyboard panel.                                                                                                |
| `Parent_Storyboard_SDR_UID`         | `Synapse_UID`                     | `1`          | UID of the parent `[[SDR_Storyboard_Definition]]` this panel belongs to. *(Introduces `SDR_Storyboard_Definition`)* |
| `Panel_Sequence_Number`             | `Synapse_Integer`                 | `1`          | The sequential number of this panel within the storyboard.                                                                                |
| `Associated_Scene_Description_UID`  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Scene_Description]]` this panel helps visualize.                                                                         |
| `Shot_Description_Text_UID`         | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` describing the shot composition, framing, and key visual focus.                                            |
| `Camera_Angle_Suggestion_Text_UID`  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` suggesting camera angle (e.g., "LowAngle", "OverTheShoulder", "WideShot").     |
| `Camera_Movement_Suggestion_Text_UID`| `Synapse_UID`                    | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` suggesting camera movement (e.g., "PanLeft", "DollyIn", "Static").         |
| `Character_Actions_In_Panel_Text_UIDs`| `List<Synapse_UID>`              | `0..*`       | List of UIDs, each pointing to an `[[SDR_Text_Block]]` describing actions of specific characters visible in the panel.                   |
| `Dialogue_Or_Caption_Text_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Dialogue_Segment]]` reference for any dialogue or caption associated with this panel.        |
| `Visual_Effects_Notes_Text_UID`     | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` noting any VFX planned for this shot.                                                                      |
| `Sound_Notes_Text_UID`              | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` with brief notes on key sounds or music cues.                                                              |
| `Panel_Duration_Estimate_UID`       | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Time_Duration]]` estimating the on-screen duration of this shot.                                                           |
| `Panel_Image_Placeholder_Ref_UID`   | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Data_Reference]]` that can later point to the generated image for this panel.                                          |
| `Storyboard_Panel_Metadata`         | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this panel.                                                                                        |