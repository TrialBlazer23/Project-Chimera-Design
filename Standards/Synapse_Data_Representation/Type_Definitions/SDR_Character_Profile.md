## SDR_Character_Profile

**SDR Type Name:** [[SDR_Character_Profile]]

**Description:** A detailed profile for a character within the narrative, outlining their attributes, motivations, relationships, and development arc.

**Fields:**

| Field Name                        | Data Type                         | Multiplicity | Description                                                                                                                                |
| :-------------------------------- | :-------------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| `Character_Profile_UID`           | `Synapse_UID`                     | `1`          | Unique identifier for this character profile.                                                                                              |
| `Character_Name_UID`              | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` (or a more structured `[[SDR_Personal_Name]]`) for the character's name(s). *(Introduces `SDR_Personal_Name`)* |
| `Character_Archetype_UID`         | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` or `[[SDR_Text_Block]]` describing their archetype (e.g., "Hero", "Mentor", "Trickster").             |
| `Physical_Description_Text_UID`   | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` detailing physical appearance.                                                                            |
| `Personality_Traits_UIDs`       | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Text_Block]]` or `[[SDR_Qualitative_Assessment]]` describing personality traits.               |
| `Backstory_Summary_Text_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` summarizing the character's backstory.                                                                    |
| `Motivations_UIDs`                | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Goal_Specification]]` or `[[SDR_Text_Block]]` describing motivations.                           |
| `Primary_Goals_In_Narrative_UIDs`| `List<Synapse_UID>`              | `0..*`       | List of UIDs, each pointing to an `[[SDR_Goal_Specification]]` for goals within this specific narrative.                                  |
| `Character_Arc_Summary_UID`       | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` describing the character's intended development or change throughout the narrative.                           |
| `Relationships_SDR_UIDs`        | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Character_Relationship]]` instance. *(Introduces `SDR_Character_Relationship`)* |
| `Key_Dialogue_Style_Notes_UID`  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` with notes on their typical speech patterns or dialogue style.                                              |
| `Character_Metadata`              | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this character profile.                                                                           |