## SDR_Condition_Clause

**SDR Type Name:** [[SDR_Condition_Clause]]

**Description:** Represents a single logical clause or statement within an [[SDR_Applicability_Condition]] or other conditional logic structures. It typically involves evaluating a piece of data against a certain value or state.

**Fields:**

| Field Name                | Data Type                  | Multiplicity | Description                                                                                                                              |
| :------------------------ | :------------------------- | :----------- | :--------------------------------------------------------------------------------------------------------------------------------------- |
| `Clause_UID`              | `Synapse_UID`              | `1`          | Unique identifier for this specific condition clause instance.                                                                           |
| `Subject_Data_Path_UID`   | `Synapse_UID`              | `1`          | UID of an `[[SDR_Data_Path_Expression]]` or `[[SDR_Semantic_Tag]]` that specifies the data element or property being evaluated (e.g., "Task.Status", "Environment.Temperature"). |
| `Comparison_Operator_UID` | `Synapse_UID`              | `1`          | UID of an `[[SDR_Vocabulary_Term]]` representing the comparison operator (e.g., "EQUALS", "NOT_EQUALS", "GREATER_THAN", "LESS_THAN", "CONTAINS", "EXISTS", "IS_TYPE_OF"). |
| `Target_Value_SDR_UID`    | `Synapse_UID`              | `0..1`       | UID of an SDR instance representing the value to compare against (e.g., an `[[SDR_Text_Block]]`, `[[SDR_Numeric_Value]]`, `[[SDR_Boolean_Value]]`). Not needed if operator is "EXISTS", etc. |
| `Clause_Negated`          | `Synapse_Boolean`          | `0..1`       | Optional. If true, the logical value of this clause is negated. Default is false.                                                        |
| `Clause_Metadata`         | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this condition clause.                                                               |