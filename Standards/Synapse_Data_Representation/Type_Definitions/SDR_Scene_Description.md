## SDR_Scene_Description

**SDR Type Name:** [[SDR_Scene_Description]]

**Description:** Provides a detailed breakdown of a single scene within the narrative, including its setting, characters present, summary of action, and pacing notes.

**Fields:**

| Field Name                          | Data Type                         | Multiplicity | Description                                                                                                                               |
| :---------------------------------- | :-------------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------- |
| `Scene_Description_UID`             | `Synapse_UID`                     | `1`          | Unique identifier for this scene description.                                                                                             |
| `Scene_Number_Or_Identifier_Text_UID`| `Synapse_UID`                    | `0..1`       | UID of an `[[SDR_Text_Block]]` for a scene number (e.g., "Scene 1.2") or unique identifier.                                                |
| `Setting_SDR_UID`                   | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Setting_Description]]` detailing the location and time of the scene.                                                   |
| `Characters_Present_SDR_UIDs`       | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Character_Profile]]` for characters present in the scene.                                       |
| `Scene_Summary_Text_UID`            | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` summarizing the key actions and events that occur in the scene.                                          |
| `Time_Of_Day_Or_Scene_Time_UID`     | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Time_Duration]]` specifying the time within the narrative world.                               |
| `Scene_Duration_Estimate_UID`       | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Time_Duration]]` estimating the screen time or reading time for the scene.                                               |
| `Pacing_Notes_Text_UID`             | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` containing notes on the intended pacing of the scene (e.g., "fast-paced action", "slow, reflective").   |
| `Visual_Storytelling_Suggestion_UIDs`| `List<Synapse_UID>`              | `0..*`       | List of UIDs, each pointing to an `[[SDR_Visual_Suggestion]]` for the Visionary, as per Narrator's capability. *(Introduces `SDR_Visual_Suggestion`)* |
| `Sound_Soundscape_Notes_UID`        | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` with initial notes or suggestions for sound design or music relevant to this scene.                          |
| `Scene_Metadata`                    | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this scene description.                                                                          |