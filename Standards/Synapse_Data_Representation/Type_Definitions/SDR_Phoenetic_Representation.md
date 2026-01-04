## SDR_Phonetic_Representation

**SDR Type Name:** [[SDR_Phonetic_Representation]]

**Description:** Provides a standardized way to represent the pronunciation of a name, word, or phrase, often used within `[[SDR_Personal_Name]]` or for dialogue coaching notes.

**Fields:**

| Field Name                   | Data Type                  | Multiplicity | Description                                                                                                                                |
| :--------------------------- | :------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| `Phonetic_Rep_UID`         | `Synapse_UID`              | `1`          | Unique identifier for this specific phonetic representation instance.                                                                      |
| `Representation_Text_UID`    | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` containing the phonetic string (e.g., "/fəˈnɛtɪk/").                                                        |
| `Phonetic_System_Name_UID` | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` indicating the phonetic alphabet or system used (e.g., "IPA_InternationalPhoneticAlphabet", "X-SAMPA", "Arpabet", "SimplifiedInternal"). |
| `Language_Context_UID`     | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` specifying the language or dialect this pronunciation applies to (e.g., "en-US_GeneralAmerican", "en-GB_RP"). |
| `Audio_Pronunciation_Ref_UID`| `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Data_Reference]]` pointing to an audio file containing a recording of the pronunciation.                                |
| `Phonetic_Rep_Metadata`    | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this phonetic representation.                                                                       |