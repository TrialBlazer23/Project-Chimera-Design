## SDR_System_Health_Metric

**SDR Type Name:** [[SDR_System_Health_Metric]]

**Description:** Represents a specific metric related to the overall health of the AI system or one of its major components. This is a consolidated or derived metric often used for high-level monitoring.

**Fields:**

| Field Name                 | Data Type                         | Multiplicity | Description                                                                                                                              |
| :------------------------- | :-------------------------------- | :----------- | :--------------------------------------------------------------------------------------------------------------------------------------- |
| `Sys_Health_Metric_UID`    | `Synapse_UID`                     | `1`          | Unique identifier for this specific system health metric reading.                                                                        |
| `Metric_Descriptor_UID`    | `Synapse_UID`                     | `1`          | UID of an `[[SDR_KPI_Descriptor]]` defining the metric (e.g., "OverallSystemStability", "AverageTaskSuccessRate", "NexusMind_Workload").   |
| `Metric_Value_SDR_UID`     | `Synapse_UID`                     | `1`          | UID of an SDR instance (e.g., `[[SDR_Numeric_Value]]`, `[[SDR_Qualitative_Assessment]]`) holding the current value of the health metric. |
| `Timestamp_Calculated`     | `Synapse_Timestamp`               | `1`          | The time at which this health metric value was calculated or aggregated.                                                                 |
| `Target_Component_Scope_UID`| `Synapse_UID`                    | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` or `[[SDR_Semantic_Tag]]` indicating the scope (e.g., "SystemWide", "NexusMind", "ArchivistCluster"). |
| `Trend_Indicator_UID`      | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` indicating the recent trend of this metric (e.g., "Stable", "Improving", "Degrading", "Fluctuating"). |
| `Supporting_Data_Ref_UIDs` | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to underlying `[[SDR_Performance_Log_Entry]]` instances or other data used to derive this health metric.        |
| `Sys_Health_Metric_Metadata`| `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this system health metric.                                                           |