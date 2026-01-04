## SDR_Sound_Effect_Descriptor

**SDR Type Name:** [[SDR_Sound_Effect_Descriptor]]

**Description:** Defines a specific, discrete sound effect (SFX), including its characteristics and intended use. Referenced by `[[SDR_Soundscape_Brief]]`.

**Fields:**

| Field Name                          | Data Type                         | Multiplicity | Description                                                                                                                                  |
| :---------------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| `SFX_Descriptor_UID`                | `Synapse_UID`                     | `1`          | Unique identifier for this sound effect descriptor.                                                                                          |
| `SFX_Name_Or_Event_UID`             | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a name for the SFX or describing the event it represents (e.g., "LaserBlast_Heavy", "Footstep_Wood", "DoorCreak_Old"). |
| `SFX_Detailed_Description_UID`      | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` detailing the desired sound qualities, emotional impact, and context.                                       |
| `SFX_Category_UID`                  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` categorizing the SFX (e.g., "Impact", "Mechanical", "Environmental", "UI_Feedback", "CreatureVocalization"). |
| `Source_Material_Suggestion_Text_UID`| `Synapse_UID`                    | `0..1`       | UID of an `[[SDR_Text_Block]]` suggesting source materials or recording techniques (e.g., "Metallic impact on hollow object", "Actual cat purr"). |
| `Desired_Acoustic_Qualities_UIDs`   | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Qualitative_Assessment]]` or `[[SDR_Vocabulary_Term]]` (e.g., "SharpAttack", "MuffledDecay", "HighReverb", "Distorted"). |
| `Reference_Audio_File_SDR_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Data_Reference]]` if a specific audio sample exists as a reference or base.                                               |
| `Variations_Required_Count`         | `Synapse_Integer`                 | `0..1`       | Number of variations needed for this sound effect to avoid repetition (e.g., for footsteps).                                               |
| `SFX_Descriptor_Metadata`           | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this sound effect descriptor.                                                                       |