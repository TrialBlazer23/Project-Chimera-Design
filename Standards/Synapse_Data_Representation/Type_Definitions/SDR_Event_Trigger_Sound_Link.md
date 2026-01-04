## SDR_Event_Trigger_Sound_Link

**SDR Type Name:** [[SDR_Event_Trigger_Sound_Link]]

**Description:** Links a specific narrative, game, or system event to a sound action (e.g., playing a sound effect, modifying an ambient profile). Referenced by `[[SDR_Soundscape_Brief]]`.

**Fields:**

| Field Name                         | Data Type                         | Multiplicity | Description                                                                                                                                  |
| :--------------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| `Event_Sound_Link_UID`             | `Synapse_UID`                     | `1`          | Unique identifier for this event-sound link.                                                                                                 |
| `Triggering_Event_Description_UID` | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]`, `[[SDR_Plot_Point]]` UID, or `[[SDR_Data_Path_Expression]]` (pointing to a state change) that describes the triggering event. |
| `Sound_Asset_Or_Profile_SDR_UID`   | `Synapse_UID`                     | `1`          | UID of the `[[SDR_Sound_Effect_Descriptor]]`, `[[SDR_Ambient_Sound_Profile]]`, or `[[SDR_Music_Composition_Brief]]` to be affected.       |
| `Sound_Action_To_Take_UID`         | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` specifying the action (e.g., "Play_OneShot", "Start_Loop", "Stop_Loop", "FadeIn_OverTime", "FadeOut_OverTime", "Modify_Parameter"). |
| `Action_Parameters_SDR_UID`        | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Parameter_Set]]` providing parameters for the action (e.g., fade duration, target volume, parameter to modify and its new value). |
| `Delay_Before_Action_SDR_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Time_Duration]]` if there's a delay between the trigger and the sound action.                                               |
| `Cooldown_After_Action_SDR_UID`    | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Time_Duration]]` specifying a cooldown period before this link can be triggered again.                                    |
| `Event_Sound_Link_Metadata`        | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this event-sound link.                                                                              |