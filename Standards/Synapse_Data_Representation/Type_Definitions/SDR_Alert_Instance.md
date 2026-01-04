## SDR_Alert_Instance

**SDR Type Name:** [[SDR_Alert_Instance]]

**Description:** Represents a specific alert generated within the AI system, indicating a notable event, potential issue, or condition requiring attention or action. While SCC commands might trigger alerts, this SDR provides a persistent, structured record of the alert itself.

**Fields:**

| Field Name                | Data Type                         | Multiplicity | Description                                                                                                                                 |
| :------------------------ | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
| `Alert_Instance_UID`      | `Synapse_UID`                     | `1`          | Unique identifier for this specific alert instance.                                                                                         |
| `Alert_Code_UID`          | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` that uniquely identifies the type of alert (e.g., "ResourceThresholdExceeded", "EthicalConflictDetected", "TaskDeadlineMissed"). |
| `Severity_Level_UID`      | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` indicating the severity (e.g., "Critical", "Warning", "Information", "Emergency").                         |
| `Timestamp_Generated`     | `Synapse_Timestamp`               | `1`          | The exact date and time when this alert was generated.                                                                                      |
| `Generating_Component_UID`| `Synapse_UID`                     | `1`          | UID of the AI family member, module, or system process that generated the alert.                                                            |
| `Alert_Message_Text_UID`  | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a human-readable message detailing the alert.                                                      |
| `Affected_Components_UIDs`| `List<Synapse_UID>`               | `0..*`       | List of UIDs for components primarily affected by or related to this alert.                                                                 |
| `Contextual_Data_Ref_UIDs`| `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Data_Reference]]` instances (e.g., log entries, anomaly reports) providing context for the alert.            |
| `Recommended_Action_Text_UID`| `Synapse_UID`                  | `0..1`       | UID of an `[[SDR_Text_Block]]` suggesting an immediate recommended action (could also point to an `[[SDR_Recommended_Action]]`).            |
| `Alert_Status_UID`        | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` indicating the current status of the alert (e.g., "Active", "Acknowledged", "Resolved", "Superseded"). |
| `Alert_Metadata`          | `[[SDR_Metadata_Block]]`          | `1`          | UID of an `[[SDR_Metadata_Block]]` for this alert instance.                                                                                 |