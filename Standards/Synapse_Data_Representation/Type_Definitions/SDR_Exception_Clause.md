## SDR_Exception_Clause

**SDR Type Name:** [[SDR_Exception_Clause]]

**Description:** Defines a specific condition or set of circumstances under which a rule or [[SDR_Ethical_Guideline]] does not apply, or where its application might be modified.

**Fields:**

| Field Name                 | Data Type                  | Multiplicity | Description                                                                                                 |
| :------------------------- | :------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------- |
| `Exception_Clause_UID`   | `Synapse_UID`              | `1`          | Unique identifier for this specific exception clause instance.                                              |
| `Exception_Description_UID`| `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` describing the nature of the exception.                                    |
| `Exception_Condition_UID`  | `Synapse_UID`              | `1`          | UID of an `[[SDR_Applicability_Condition]]` that specifies when this exception is triggered.                |
| `Impact_On_Guideline_UID`  | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` describing how the original guideline is modified when this exception applies. |
| `Exception_Metadata`     | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this exception clause.                                  |