## SDR_Time_Duration

**SDR Type Name:** [[SDR_Time_Duration]]

**Description:** Represents a span of time or a duration.

**Fields:**

| Field Name           | Data Type                  | Multiplicity | Description                                                                                                   |
| :------------------- | :------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------ |
| `Time_Duration_UID`  | `Synapse_UID`              | `1`          | Unique identifier for this specific time duration instance.                                                   |
| `Duration_Value`     | `Synapse_Float`            | `1`          | The numerical value of the duration.                                                                          |
| `Duration_Unit_UID`  | `Synapse_UID`              | `1`          | UID of an `[[SDR_Vocabulary_Term]]` specifying the unit of the duration (e.g., "Seconds", "Milliseconds", "Minutes", "Hours", "Days", "Weeks", "Months", "Years"). |
| `Start_Timestamp_Ref`| `Synapse_Timestamp`        | `0..1`       | Optional. If the duration is anchored to a specific start time.                                             |
| `End_Timestamp_Ref`  | `Synapse_Timestamp`        | `0..1`       | Optional. If the duration is anchored to a specific end time.                                               |
| `Duration_Description_UID`| `Synapse_UID`          | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a human-readable description (e.g., "Approximately 3 hours").      |
| `Time_Duration_Metadata`| `[[SDR_Metadata_Block]]`| `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this time duration.                                     |