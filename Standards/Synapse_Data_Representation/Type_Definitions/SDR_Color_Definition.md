## SDR_Color_Definition

**SDR Type Name:** [[SDR_Color_Definition]]

**Description:** Provides a detailed definition of a single color, allowing for representation in various color models (Hex, RGB, CMYK) and including optional usage notes.

**Fields:**

| Field Name                 | Data Type                  | Multiplicity | Description                                                                                                      |
| :------------------------- | :------------------------- | :----------- | :--------------------------------------------------------------------------------------------------------------- |
| `Color_Def_UID`            | `Synapse_UID`              | `1`          | Unique identifier for this specific color definition.                                                            |
| `Color_Name_UID`           | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` providing a common name for the color (e.g., "SkyBlue", "ForestGreen"). |
| `Hex_Code_Value`         | `Synapse_String`           | `0..1`       | The hexadecimal color code (e.g., "#FF0000", "00FF00").                                                          |
| `RGB_Value_SDR_UID`        | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_RGB_Color_Value]]` instance if RGB values are specified. *(Introduces `SDR_RGB_Color_Value`)* |
| `CMYK_Value_SDR_UID`       | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_CMYK_Color_Value]]` instance if CMYK values are specified. *(Introduces `SDR_CMYK_Color_Value`)* |
| `Pantone_Reference_Text`   | `Synapse_String`           | `0..1`       | Pantone Matching System (PMS) reference number, if applicable.                                                   |
| `Opacity_Alpha_Value`    | `Synapse_Float`            | `0..1`       | Opacity or alpha channel value (e.g., 0.0 for fully transparent to 1.0 for fully opaque). Assumed 1.0 if not specified. |
| `Usage_Notes_Text_UID`     | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` with notes on typical usage or context for this color within a palette.         |
| `Color_Def_Metadata`       | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this color definition.                                                    |