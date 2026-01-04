## SDR_Performance_Metric_Definition

**SDR Type Name:** [[SDR_Performance_Metric_Definition]]

**Description:** Provides a detailed definition for a specific performance metric, going beyond a general KPI descriptor if more specific calculation logic, thresholds, or data sources are needed.

**Fields:**

| Field Name                     | Data Type                         | Multiplicity | Description                                                                                                                               |
| :----------------------------- | :-------------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------- |
| `Perf_Metric_Def_UID`          | `Synapse_UID`                     | `1`          | Unique identifier for this specific performance metric definition.                                                                        |
| `Metric_Name_UID`              | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` providing the unique name of the metric.                                     |
| `Metric_Description_UID`       | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` detailing what the metric measures, its importance, and context.                                           |
| `Unit_Of_Measure_UID`          | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` or `[[SDR_Text_Block]]` defining the unit (e.g., "ms", "requests/sec", "%", "count").                  |
| `Calculation_Methodology_UID`  | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` or `[[SDR_Algorithm_Reference]]` describing how the metric is calculated or derived. *(Introduces `SDR_Algorithm_Reference`)* |
| `Data_Source_Path_UIDs`        | `List<Synapse_UID>`               | `1..*`       | List of UIDs, each pointing to an `[[SDR_Data_Path_Expression]]`, indicating where the raw data for this metric is sourced.            |
| `Optimal_Value_Range_SDR_UID`  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Numeric_Range]]` or `[[SDR_Qualitative_Assessment]]` defining the optimal or target range for this metric. *(Introduces `SDR_Numeric_Range`)* |
| `Threshold_Warning_SDR_UID`    | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Criterion]]` defining the threshold at which a warning should be triggered for this metric.                              |
| `Threshold_Critical_SDR_UID`   | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Criterion]]` defining the threshold at which a critical alert should be triggered.                                     |
| `Perf_Metric_Def_Metadata`     | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this metric definition.                                                               |