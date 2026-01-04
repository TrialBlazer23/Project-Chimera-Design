## SDR_Parameter_Set

**SDR Type Name:** [[SDR_Parameter_Set]]

**Description:** A collection of named parameters (key-value pairs) that configure or control the execution of a task, operation, or model.

**Fields:**

| Field Name          | Data Type                         | Multiplicity | Description                                                                     |
| :------------------ | :-------------------------------- | :----------- | :------------------------------------------------------------------------------ |
| `Param_Set_UID`     | `Synapse_UID`                     | `1`          | Unique identifier for this parameter set instance.                            |
| `Parameters`        | `List<[[SDR_Parameter_Item]]>`    | `1..*`       | UID list of SDR_Parameter_Item instances. The actual list of parameters.    |
| `Context_Description`| `[[SDR_Text_Block]]`             | `0..1`       | UID of an SDR_Text_Block. Optional description of the context for these parameters. |
| `Param_Set_Metadata`| `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this parameter set.         |