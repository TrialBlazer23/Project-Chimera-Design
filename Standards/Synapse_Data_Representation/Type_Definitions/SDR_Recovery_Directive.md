## SDR_Recovery_Directive

**SDR Type Name:** [[SDR_Recovery_Directive]]

**Description:** A structured directive, typically issued by the Diagnostician, to initiate a specific recovery protocol or set of actions in response to an issue.

**Fields:**

| Field Name                    | Data Type                         | Multiplicity | Description                                                                                                                               |
| :---------------------------- | :-------------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------- |
| `Recovery_Directive_UID`      | `Synapse_UID`                     | `1`          | Unique identifier for this specific recovery directive.                                                                                   |
| `Triggering_Event_UID`        | `Synapse_UID`                     | `1`          | UID of the event that triggered this directive (e.g., `[[SDR_Anomaly_Report_UID]]`, `[[SDR_Alert_UID]]`).                                  |
| `Target_Component_UID`        | `Synapse_UID`                     | `1`          | UID of the component to which the recovery actions should be applied.                                                                     |
| `Recovery_Protocol_Name_UID`  | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` or `[[SDR_Text_Block]]` identifying the specific pre-defined recovery protocol to be executed.          |
| `Execution_Parameters_SDR_UID`| `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Parameter_Set]]` providing any specific parameters needed for this execution of the recovery protocol.                   |
| `Issuing_Model_UID`           | `Synapse_UID`                     | `1`          | UID of the model issuing the directive (usually Diagnostician).                                                                           |
| `Execution_Priority`          | `Synapse_Integer`                 | `0..1`       | Priority level for executing this recovery directive.                                                                                     |
| `Directive_Status_UID`        | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` indicating current status (e.g., "PendingExecution", "InProgress", "CompletedSuccess", "CompletedFailure", "Aborted"). |
| `Recovery_Directive_Metadata` | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this directive.                                                                       |