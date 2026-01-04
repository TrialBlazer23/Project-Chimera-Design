## SDR_KPI_Descriptor

**SDR Type Name:** [[SDR_KPI_Descriptor]]

**Description:** (Key Performance Indicator Descriptor) Defines a measurable value that demonstrates how effectively a system, model, or process is achieving key objectives. Used in goal specification and performance monitoring.

**Fields:**

| Field Name               | Data Type                | Multiplicity | Description                                                                                                 |
| :----------------------- | :----------------------- | :----------- | :---------------------------------------------------------------------------------------------------------- |
| `KPI_Descriptor_UID`     | `Synapse_UID`            | `1`          | Unique identifier for this KPI descriptor instance.                                                         |
| `KPI_Name`               | `[[SDR_Text_Block]]`     | `1`          | UID of an SDR_Text_Block. The human-readable name of the KPI (e.g., "TaskCompletionRate", "AccuracyScore"). |
| `KPI_Description`        | `[[SDR_Text_Block]]`     | `1`          | UID of an SDR_Text_Block. A detailed description of what the KPI measures and why it's important.           |
| `Measurement_Unit`       | `[[SDR_Text_Block]]`     | `0..1`       | UID of an SDR_Text_Block. The unit of measurement for the KPI (e.g., "%", "ms", "count").                   |
| `Measurement_Method`     | `[[SDR_Text_Block]]`     | `1`          | UID of an SDR_Text_Block. How this KPI is calculated or measured.                                           |
| `Target_Value_SDR_UID`   | `Synapse_UID`            | `0..1`       | UID of an SDR instance representing the target value for this KPI.                                          |
| `Threshold_Good_SDR_UID` | `Synapse_UID`            | `0..1`       | UID of an SDR instance defining the threshold above/below which performance is considered "good".           |
| `Threshold_Poor_SDR_UID` | `Synapse_UID`            | `0..1`       | UID of an SDR instance defining the threshold above/below which performance is considered "poor".           |
| `Reporting_Frequency`    | `[[SDR_Text_Block]]`     | `0..1`       | UID of an SDR_Text_Block. How often this KPI should be reported (e.g., "EndOfTask", "Hourly").              |
| `KPI_Metadata`           | `[[SDR_Metadata_Block]]` | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata associated with this KPI descriptor.                        |