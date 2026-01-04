## SDR_Color_Palette_Definition

**SDR Type Name:** [[SDR_Color_Palette_Definition]]

**Description:** Defines a specific color palette, including primary, secondary, and accent colors, potentially with notes on color harmony. Referenced by `[[SDR_Visual_Concept_Brief]]`.

**Fields:**

| Field Name                       | Data Type                         | Multiplicity | Description                                                                                                                                  |
| :------------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| `Color_Palette_Def_UID`        | `Synapse_UID`                     | `1`          | Unique identifier for this color palette definition.                                                                                         |
| `Palette_Name_UID`             | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a name for this palette (e.g., "HeroicPrimaryTones", "ForestNocturne").                             |
| `Palette_Description_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` describing the intended mood, usage, or rationale for this palette.                                         |
| `Primary_Colors_SDR_UIDs`      | `List<Synapse_UID>`               | `1..*`       | List of UIDs, each pointing to an `[[SDR_Color_Definition]]` representing the dominant colors.                                               |
| `Secondary_Colors_SDR_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Color_Definition]]` representing supporting colors.                                               |
| `Accent_Colors_SDR_UIDs`       | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Color_Definition]]` representing colors for highlights or specific emphasis.                       |
| `Neutral_Colors_SDR_UIDs`      | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Color_Definition]]` representing neutral tones (grays, whites, blacks, beiges) used in the palette. |
| `Color_Harmony_Rule_Text_UID`  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` describing the color harmony principle employed (e.g., "Analogous", "Complementary", "Triadic"). |
| `Color_Palette_Def_Metadata`   | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this color palette definition.                                                                      |