## SDR_Personal_Name

**SDR Type Name:** [[SDR_Personal_Name]]

**Description:** A structured representation of a character's or entity's name, allowing for components like given name, family name, titles, and nicknames. Used by `[[SDR_Character_Profile]]`.

**Fields:**

| Field Name                | Data Type                  | Multiplicity | Description                                                                                                |
| :------------------------ | :------------------------- | :----------- | :--------------------------------------------------------------------------------------------------------- |
| `Personal_Name_UID`       | `Synapse_UID`              | `1`          | Unique identifier for this personal name instance.                                                         |
| `Full_Name_Text_UID`      | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` for the complete formal name.                                               |
| `Given_Name_Text_UID`     | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` for the first/given name(s).                                                |
| `Family_Name_Text_UID`    | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` for the surname(s)/family name(s).                                          |
| `Nicknames_Text_UIDs`     | `List<Synapse_UID>`        | `0..*`       | List of UIDs, each pointing to an `[[SDR_Text_Block]]` for any nicknames or aliases.                       |
| `Titles_Text_UIDs`        | `List<Synapse_UID>`        | `0..*`       | List of UIDs, each pointing to an `[[SDR_Text_Block]]` for titles (e.g., "Dr.", "Captain", "Lord").         |
| `Pronunciation_Guide_UID` | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Phonetic_Representation]]` for pronunciation. *(Introduces `SDR_Phonetic_Representation`)* |
| `Name_Origin_Culture_UID` | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` indicating cultural origin or meaning of the name. |
| `Personal_Name_Metadata`  | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this personal name.                                                 |