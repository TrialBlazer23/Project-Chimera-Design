## SDR_Anomaly_Report

**SDR Type Name:** [[SDR_Anomaly_Report]]

**Description:** A structured report detailing an anomaly, error, or significant deviation from expected behavior detected within the AI system. Generated primarily by the Diagnostician.

**Fields:**

| Field Name                  | Data Type                | Multiplicity | Description                                                                                                                                               |
| :-------------------------- | :----------------------- | :----------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Anomaly_Report_UID`        | `Synapse_UID`            | `1`          | Unique identifier for this specific anomaly report.                                                                                                       |
| `Timestamp_Detected`        | `Synapse_Timestamp`      | `1`          | The exact date and time when the anomaly was first detected.                                                                                              |
| `Reporting_Model_UID`       | `Synapse_UID`            | `1`          | UID of the AI family member reporting the anomaly (usually the Diagnostician).                                                                            |
| `Affected_Component_UID`    | `Synapse_UID`            | `1`          | UID of the AI family member, module, task, or process primarily affected by or exhibiting the anomaly.                                                    |
| `Anomaly_Description_UID`   | `Synapse_UID`            | `1`          | UID of an `[[SDR_Text_Block]]` providing a human-readable description of the anomaly.                                                                     |
| `Observed_Behavior_SDR_UID` | `Synapse_UID`            | `1`          | UID of an SDR instance (e.g., `[[SDR_Performance_Log_Entry]]`, `[[SDR_Text_Block]]`, `[[SDR_Data_Reference]]`) detailing the observed anomalous behavior. |
| `Expected_Behavior_SDR_UID` | `Synapse_UID`            | `0..1`       | UID of an SDR instance detailing the expected behavior against which the anomaly was identified.                                                          |
| `Severity_Level_UID`        | `Synapse_UID`            | `1`          | UID of an `[[SDR_Vocabulary_Term]]` indicating the assessed severity of the anomaly (e.g., "Critical", "High", "Medium", "Low", "Informational").         |
| `Diagnostic_Data_Ref_UIDs`  | `List<Synapse_UID>`      | `0..*`       | List of UIDs pointing to relevant `[[SDR_Performance_Log_Entry]]` instances, `[[SDR_Data_Reference]]`s, or other data used for initial diagnosis.         |
| `Suggested_Next_Action_UID` | `Synapse_UID`            | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` (e.g., "InitiateRootCauseAnalysis", "TriggerRecoveryProtocol_X", "Monitor").                                          |
| `Anomaly_Report_Metadata`   | `[[SDR_Metadata_Block]]` | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this report.                                                                                          |