## SDR_Parameter_Item

**SDR Type Name:** [[SDR_Parameter_Item]]

**Description:** Represents a single named parameter within an `SDR_Parameter_Set`. This structure allows for flexibility in defining various types of parameters (e.g., string, number, boolean, or even a reference to another SDR structure).

**Fields:**

| Field Name            | Data Type                  | Multiplicity | Description                                                                                                   |
| :-------------------- | :------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------ |
| `Param_Item_UID`      | `Synapse_UID`              | `1`          | Unique identifier for this specific parameter item instance.                                                  |
| `Parameter_Name`      | `Synapse_String`           | `1`          | The name of the parameter (key).                                                                              |
| `Parameter_Value_Type`| `Synapse_String`           | `1`          | Indicates the data type of `Parameter_Value_Content` (e.g., "Synapse_String", "Synapse_Integer", "Synapse_Boolean", "Synapse_UID", "SDR_Reference"). |
| `Parameter_Value_Content`| `Synapse_String`        | `1`          | The actual value of the parameter, stored as a string. Interpretation depends on `Parameter_Value_Type`. If type is "SDR_Reference", this holds a Synapse_UID. |
| `Parameter_Description`| `[[SDR_Text_Block]]`      | `0..1`       | UID of an SDR_Text_Block. Optional description of the parameter's purpose or meaning.                      |
| `Unit_Of_Measure`     | `[[SDR_Text_Block]]`      | `0..1`       | UID of an SDR_Text_Block. Unit if the parameter is numerical and has one (e.g., "ms", "pixels", "iterations"). |
| `Is_Optional`         | `Synapse_Boolean`          | `0..1`       | Indicates if this parameter is optional for the operation (default could be `false` meaning mandatory).    |
| `Param_Item_Metadata` | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata associated with this parameter item.                        |