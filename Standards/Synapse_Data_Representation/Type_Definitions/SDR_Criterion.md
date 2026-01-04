## SDR_Criterion

**SDR Type Name:** [[SDR_Criterion]]

**Description:** Defines a specific condition or standard that can be evaluated to determine if a certain state has been met, a goal achieved, or an output is valid. Often used in goal specifications or validation checks.

**Fields:**

| Field Name              | Data Type                  | Multiplicity | Description                                                                                                |
| :---------------------- | :------------------------- | :----------- | :--------------------------------------------------------------------------------------------------------- |
| `Criterion_UID`         | `Synapse_UID`              | `1`          | Unique identifier for this specific criterion instance.                                                    |
| `Criterion_Description` | `[[SDR_Text_Block]]`       | `1`          | UID of an SDR_Text_Block. A clear and unambiguous description of the criterion.                            |
| `Evaluation_Method`     | `[[SDR_Text_Block]]`       | `0..1`       | UID of an SDR_Text_Block. Description of how this criterion is to be evaluated or measured.                |
| `Target_Value_SDR_UID`  | `Synapse_UID`              | `0..1`       | UID of an SDR instance representing the target value or state for this criterion (e.g., an SDR_Numeric_Value, SDR_Boolean_Value). |
| `Operator`              | `Synapse_String`           | `0..1`       | The logical operator to use for evaluation if applicable (e.g., "EQUALS", "GREATER_THAN", "CONTAINS").    |
| `Tolerance_SDR_UID`     | `Synapse_UID`              | `0..1`       | UID of an SDR instance defining acceptable tolerance if the target value is not exact.                   |
| `Criterion_Metadata`    | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata associated with this criterion.                            |