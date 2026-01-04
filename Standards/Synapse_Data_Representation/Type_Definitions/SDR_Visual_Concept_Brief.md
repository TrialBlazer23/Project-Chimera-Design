## SDR_Visual_Concept_Brief

**SDR Type Name:** [[SDR_Visual_Concept_Brief]]

**Description:** A structured brief for the Visionary to generate concept art or visual designs for characters, environments, objects, or specific moods/themes.

**Fields:**

| Field Name                        | Data Type                         | Multiplicity | Description                                                                                                                                  |
| :-------------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| `Visual_Concept_Brief_UID`        | `Synapse_UID`                     | `1`          | Unique identifier for this visual concept brief.                                                                                             |
| `Brief_Title_Text_UID`            | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a concise title for the concept (e.g., "ProtagonistMainOutfit", "AlienHomeworldVista", "MysticalArtifactDesign"). |
| `Subject_Description_Text_UID`    | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` detailing what needs to be visualized (e.g., character description, scene summary, object function).          |
| `Visual_Style_References_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` describing desired artistic styles (e.g., "Photorealistic", "Impressionistic", "Cyberpunk", "ArtDeco") or specific artist/work references. |
| `Color_Palette_Description_UID`   | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Color_Palette_Definition]]` describing the desired color scheme, key colors, or color relationships. *(Introduces `SDR_Color_Palette_Definition`)* |
| `Mood_And_Atmosphere_Target_UID`  | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Qualitative_Assessment]]` or `[[SDR_Text_Block]]` describing the intended mood and atmosphere (e.g., "Ominous", "Serene", "HighEnergy"). |
| `Key_Elements_To_Include_Text_UIDs`| `List<Synapse_UID>`              | `0..*`       | List of UIDs, each pointing to an `[[SDR_Text_Block]]` listing specific visual elements, symbols, or details that must be included.        |
| `Things_To_Avoid_Text_UIDs`       | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Text_Block]]` listing any visual clichés, styles, or elements to be avoided.                     |
| `Inspirational_Material_Ref_UIDs` | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Data_Reference]]` instances (e.g., links to images, videos, existing art) for inspiration.             |
| `Intended_Usage_Context_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` describing where or how this visual concept will be used (e.g., "PromotionalArt", "InGameAsset", "CinematicMattePainting"). |
| `Visual_Concept_Metadata`         | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this brief.                                                                                         |