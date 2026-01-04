## SDR_Visual_Suggestion

**SDR Type Name:** [[SDR_Visual_Suggestion]]

**Description:** A specific suggestion from the Narrator to the Visionary regarding visual elements for a scene or narrative moment, as per the Narrator's capability to propose visual storytelling enhancements. Referenced by `[[SDR_Scene_Description]]`.

**Fields:**

| Field Name                          | Data Type                  | Multiplicity | Description                                                                                                                                  |
| :---------------------------------- | :------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| `Visual_Suggestion_UID`             | `Synapse_UID`              | `1`          | Unique identifier for this visual suggestion.                                                                                                |
| `Target_Scene_Or_Element_Text_UID`  | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` (or `[[SDR_Data_Path_Expression]]` to a specific part of an `[[SDR_Scene_Description]]`) indicating what this suggestion applies to. |
| `Suggestion_Description_Text_UID`   | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` detailing the visual suggestion (e.g., "moody lighting", "close-up on character's reaction", "specific symbolism"). |
| `Purpose_Of_Suggestion_Text_UID`    | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` explaining the narrative purpose (e.g., "to enhance suspense", "to foreshadow event X", "to reveal character's emotion"). |
| `Reference_Image_Concept_SDR_UID`   | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Data_Reference]]` if the Narrator has a specific visual reference or concept in mind (e.g., a link to an image, or an existing concept art piece). |
| `Desired_Emotional_Impact_UID`      | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` or `[[SDR_Text_Block]]` specifying the desired emotional impact of the visual element.               |
| `Visual_Suggestion_Metadata`        | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this visual suggestion.                                                                             |