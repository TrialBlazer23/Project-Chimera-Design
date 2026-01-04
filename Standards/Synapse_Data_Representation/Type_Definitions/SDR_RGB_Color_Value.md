## SDR_RGB_Color_Value

**SDR Type Name:** [[SDR_RGB_Color_Value]]

**Description:** Represents a color using the Red, Green, Blue (RGB) additive color model.

**Fields:**

| Field Name          | Data Type                  | Multiplicity | Description                                                                                                 |
| :------------------ | :------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------- |
| `RGB_Value_UID`     | `Synapse_UID`              | `1`          | Unique identifier for this specific RGB color value instance.                                               |
| `Red_Value`         | `Synapse_Integer`          | `1`          | Red component value, typically ranging from 0 to 255.                                                       |
| `Green_Value`       | `Synapse_Integer`          | `1`          | Green component value, typically ranging from 0 to 255.                                                     |
| `Blue_Value`        | `Synapse_Integer`          | `1`          | Blue component value, typically ranging from 0 to 255.                                                      |
| `Alpha_Channel_Value`| `Synapse_Float`           | `0..1`       | Optional alpha channel value for transparency (0.0 for fully transparent to 1.0 for fully opaque). Defaults to 1.0 if linked from an `SDR_Color_Definition` that doesn't specify its own opacity. |
| `RGB_Value_Metadata`| `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this RGB value.                                                      |