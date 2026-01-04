## SDR_Narrative_Blueprint

**SDR Type Name:** [[SDR_Narrative_Blueprint]]

**Description:** An overarching structure that contains all the primary components and guiding principles for a complete narrative or story. This is often the main output or working document for the Narrator.

**Fields:**

| Field Name                     | Data Type                         | Multiplicity | Description                                                                                                                                 |
| :----------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
| `Narrative_Blueprint_UID`      | `Synapse_UID`                     | `1`          | Unique identifier for this narrative blueprint.                                                                                             |
| `Title_Text_UID`               | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` containing the working or final title of the narrative.                                                      |
| `Logline_Text_UID`             | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` containing a concise one or two-sentence summary of the narrative (the logline).                             |
| `Core_Themes_UIDs`             | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Abstract_Concept_Representation]]` or `[[SDR_Text_Block]]` outlining the core themes.          |
| `Target_Audience_Desc_UID`     | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` describing the intended target audience.                                                                     |
| `Overall_Tone_And_Style_UID`   | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Qualitative_Assessment]]` or `[[SDR_Text_Block]]` describing the desired tone and stylistic approach.                   |
| `Primary_Setting_Desc_UID`   | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Setting_Description]]` that details the main world or environment of the narrative. *(Introduces `SDR_Setting_Description`)* |
| `Character_Bible_SDR_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Character_Bible]]` which contains a collection of character profiles. *(Introduces `SDR_Character_Bible`)* |
| `Story_Arcs_SDR_UIDs`          | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Story_Arc]]` that make up the narrative structure. |
| `Narrative_Structure_Notes_UID`| `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` containing notes on the overall narrative structure (e.g., three-act, episodic).                            |
| `Narrative_Metadata`           | `[[SDR_Metadata_Block]]`          | `1`          | UID of an `[[SDR_Metadata_Block]]` for this narrative blueprint.                                                                          |