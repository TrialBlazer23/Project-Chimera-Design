## SDR_Character_Bible

**SDR Type Name:** [[SDR_Character_Bible]]

**Description:** A collection of `[[SDR_Character_Profile]]` instances for a given narrative, serving as a central repository for all character information. Referenced by `[[SDR_Narrative_Blueprint]]`.

**Fields:**

| Field Name                    | Data Type                         | Multiplicity | Description                                                                                             |
| :---------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------ |
| `Character_Bible_UID`         | `Synapse_UID`                     | `1`          | Unique identifier for this character bible.                                                             |
| `Associated_Narrative_Blueprint_UID`| `Synapse_UID`               | `1`          | UID of the `[[SDR_Narrative_Blueprint]]` this character bible belongs to.                                |
| `Character_Profiles_SDR_UIDs` | `List<Synapse_UID>`               | `1..*`       | List of UIDs, each pointing to an `[[SDR_Character_Profile]]` instance.                               |
| `Overall_Cast_Notes_Text_UID` | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` for general notes about the cast, their interconnections, or casting ideas. |
| `Character_Bible_Metadata`    | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this character bible.                                            |