## SDR_Performance_Log_Entry

**SDR Type Name:** [[SDR_Performance_Log_Entry]]

**Description:** Records a specific performance metric for a monitored component or process at a point in time. This is used by the Diagnostician for continuous performance monitoring. (This can also serve the purpose of the `SDR_Processing_Log_Entry` previously mentioned for `SDR_Metadata_Block` if a processing step has associated performance metrics.)

**Fields:**

| Field Name                  | Data Type                         | Multiplicity | Description                                                                                                                               |
| :-------------------------- | :-------------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------- |
| `Perf_Log_Entry_UID`        | `Synapse_UID`                     | `1`          | Unique identifier for this specific performance log entry.                                                                                |
| `Timestamp_Recorded`        | `Synapse_Timestamp`               | `1`          | The exact date and time when this performance data was recorded.                                                                          |
| `Monitored_Component_UID`   | `Synapse_UID`                     | `1`          | UID of the AI family member, specific module, task, or process being monitored.                                                           |
| `Monitored_Component_Type`  | `[[SDR_Vocabulary_Term]]`         | `0..1`       | UID of an SDR_Vocabulary_Term. Type of component being monitored (e.g., "AI_Model", "Task_Instance", "Synapse_Channel").                 |
| `Metric_Descriptor_UID`     | `Synapse_UID`                     | `1`          | UID of an `[[SDR_KPI_Descriptor]]` or a more specific `[[SDR_Performance_Metric_Definition]]` that defines the metric being recorded. |
| `Metric_Value_SDR_UID`      | `Synapse_UID`                     | `1`          | UID of an SDR instance (e.g., `[[SDR_Numeric_Value]]`, `[[SDR_Text_Block]]`) holding the actual measured value of the metric.            |
| `Status_At_Measurement_UID` | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]`. Optional status of the component at the time of measurement (e.g., "Idle", "Processing", "ErrorState"). |
| `Correlated_Event_UIDs`     | `List<Synapse_UID>`               | `0..*`       | List of UIDs for any significant events (e.g., Task_Start_UID, Alert_UID) correlated with this performance reading.                   |
| `Perf_Log_Metadata`         | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata associated with this log entry.                                                           |