## SDR_Sound_Element_Descriptor

**SDR Type Name:** [[SDR_Sound_Element_Descriptor]]

**Description:** Describes a specific component or layer of an ambient soundscape, which might be a continuous sound, a recurring motif, or an environmental characteristic. Similar to `[[SDR_Sound_Effect_Descriptor]]` but often used for background or environmental sounds.

**Fields:**

| Field Name                             | Data Type                         | Multiplicity | Description                                                                                                                                 |
| :------------------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
| `Sound_Element_Descriptor_UID`       | `Synapse_UID`                     | `1`          | Unique identifier for this sound element descriptor.                                                                                        |
| `Element_Name_Or_Type_UID`           | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a name or type for the sound element (e.g., "WindHowl_Low", "DistantTrafficRumble", "GentleStream"). |
| `Element_Detailed_Description_UID`   | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` detailing the desired sound qualities and characteristics.                                                 |
| `Element_Category_UID`               | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` categorizing the element (e.g., "Weather", "Fauna", "Machinery", "RoomTone").                          |
| `Desired_Acoustic_Qualities_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Qualitative_Assessment]]` or `[[SDR_Vocabulary_Term]]` (e.g., "Subtle", "Broadband", "LoopedSeamlessly"). |
| `Periodicity_Or_Behavior_Notes_UID`  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` describing its behavior (e.g., "ConstantLowHum", "IntermittentGusts", "FadesInOut").                         |
| `Reference_Audio_File_SDR_UID`       | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Data_Reference]]` if a specific audio sample exists as a reference or base.                                              |
| `Sound_Element_Descriptor_Metadata`  | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this sound element descriptor.                                                                     |