## SDR_VFX_Plan_Element

**SDR Type Name:** [[SDR_VFX_Plan_Element]]

**Description:** Details a specific visual effect (VFX) required for a shot or scene, including its description, type, complexity, and integration notes. This supports the Visionary's role in planning VFX integration.

**Fields:**

| Field Name                      | Data Type                         | Multiplicity | Description                                                                                                                                  |
| :------------------------------ | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| `VFX_Plan_Element_UID`          | `Synapse_UID`                     | `1`          | Unique identifier for this VFX plan element.                                                                                                 |
| `Associated_Shot_Or_Scene_UID`  | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Storyboard_Panel]]` or `[[SDR_Scene_Description]]` where this VFX is required.                                            |
| `Effect_Description_Text_UID`   | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a detailed description of the visual effect and its desired appearance.                             |
| `Effect_Type_UID`               | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` categorizing the type of effect (e.g., "ParticleSystem_Explosion", "MattePainting_Sky", "CreatureAnimation_RigRemoval", "Compositing_GreenScreen"). |
| `Complexity_Estimate_UID`       | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Qualitative_Assessment]]` or `[[SDR_Vocabulary_Term]]` (e.g., "Low", "Medium", "High", "VeryComplex") estimating the difficulty. |
| `Required_Assets_Input_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Data_Reference]]` instances for any 3D models, textures, plates, or other assets needed to create the effect. |
| `Software_Tool_Suggestions_UIDs`| `List<Synapse_UID>`              | `0..*`       | List of UIDs pointing to `[[SDR_Vocabulary_Term]]` suggesting preferred software or tools.                                               |
| `Integration_Notes_Text_UID`    | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` with notes on how the effect should be integrated with live-action footage or other CG elements.           |
| `Art_Direction_Reference_UIDs`  | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Visual_Concept_Brief]]` UIDs or `[[SDR_Data_Reference]]`s providing art direction.                     |
| `VFX_Plan_Element_Metadata`     | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this VFX plan element.                                                                              |