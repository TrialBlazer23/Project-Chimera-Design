## SDR_Numeric_Range

**SDR Type Name:** [[SDR_Numeric_Range]]

**Description:** Defines a range between two numeric values, often used for specifying optimal values, thresholds, or query constraints.

**Fields:**

| Field Name             | Data Type                  | Multiplicity | Description                                                                                                  |
| :--------------------- | :------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------- |
| `Numeric_Range_UID`    | `Synapse_UID`              | `1`          | Unique identifier for this specific numeric range instance.                                                  |
| `Minimum_Value`        | `Synapse_Float`            | `1`          | The minimum value of the range.                                                                              |
| `Maximum_Value`        | `Synapse_Float`            | `1`          | The maximum value of the range.                                                                              |
| `Min_Is_Inclusive`     | `Synapse_Boolean`          | `0..1`       | If true, the minimum value is included in the range. Default is true.                                        |
| `Max_Is_Inclusive`     | `Synapse_Boolean`          | `0..1`       | If true, the maximum value is included in the range. Default is true.                                        |
| `Unit_Of_Measure_UID`  | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` or `[[SDR_Text_Block]]` if the range values have a specific unit.         |
| `Numeric_Range_Metadata`| `[[SDR_Metadata_Block]]`  | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this numeric range.                                      |