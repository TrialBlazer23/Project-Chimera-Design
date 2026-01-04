## SDR_Soundscape_Brief

**SDR Type Name:** [[SDR_Soundscape_Brief]]

**Description:** A structured brief for the Visionary to design an immersive soundscape for a specific scene, environment, or narrative moment. This includes ambient sounds, key sound effects, and potential musical integration notes.

**Fields:**

| Field Name                        | Data Type                         | Multiplicity | Description                                                                                                                                  |
| :-------------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| `Soundscape_Brief_UID`            | `Synapse_UID`                     | `1`          | Unique identifier for this soundscape brief.                                                                                                 |
| `Target_Scene_Or_Environment_UID` | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Scene_Description]]` or `[[SDR_Setting_Description]]` this soundscape is intended for.                                   |
| `Overall_Atmosphere_Goal_UID`     | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` or `[[SDR_Qualitative_Assessment]]` describing the desired mood and atmosphere (e.g., "TenseSuspense", "PeacefulNature", "ChaoticBattle"). |
| `Ambient_Noise_Profile_UID`       | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Ambient_Sound_Profile]]` detailing background environmental sounds. *(Introduces `SDR_Ambient_Sound_Profile`)* |
| `Key_Sound_Effects_UIDs`          | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Sound_Effect_Descriptor]]` for specific, prominent sound effects. *(Introduces `SDR_Sound_Effect_Descriptor`)* |
| `Dynamic_Sound_Event_Triggers_UIDs`| `List<Synapse_UID>`              | `0..*`       | List of UIDs, each pointing to an `[[SDR_Event_Trigger_Sound_Link]]` describing sounds that change based on narrative events or interactions. *(Introduces `SDR_Event_Trigger_Sound_Link`)* |
| `Musical_Integration_Notes_UID`   | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` with notes on how music (if any, from `[[SDR_Music_Composition_Brief]]`) should blend with the soundscape. |
| `Inspirational_Audio_Ref_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Data_Reference]]` instances (e.g., links to existing soundscapes, specific sound examples).                  |
| `Technical_Delivery_Specs_UID`    | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` outlining technical requirements (e.g., "Stereo", "5.1Surround", "AdaptiveLooping").                       |
| `Soundscape_Brief_Metadata`       | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this brief.                                                                                         |