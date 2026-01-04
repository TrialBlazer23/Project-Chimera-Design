## SDR_CMYK_Color_Value

**SDR Type Name:** [[SDR_CMYK_Color_Value]]

**Description:** Represents a color using the Cyan, Magenta, Yellow, Key/Black (CMYK) subtractive color model, typically used in printing.

**Fields:**

| Field Name           | Data Type                  | Multiplicity | Description                                                                                                 |
| :------------------- | :------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------- |
| `CMYK_Value_UID`     | `Synapse_UID`              | `1`          | Unique identifier for this specific CMYK color value instance.                                              |
| `Cyan_Value`         | `Synapse_Float`            | `1`          | Cyan component value, typically as a percentage (0.0 to 100.0).                                             |
| `Magenta_Value`      | `Synapse_Float`            | `1`          | Magenta component value, typically as a percentage (0.0 to 100.0).                                          |
| `Yellow_Value`       | `Synapse_Float`            | `1`          | Yellow component value, typically as a percentage (0.0 to 100.0).                                           |
| `Key_Black_Value`    | `Synapse_Float`            | `1`          | Key (Black) component value, typically as a percentage (0.0 to 100.0).                                      |
| `CMYK_Value_Metadata`| `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an `[[SDR_Metadata_Block]]` for this CMYK value.                                                     |