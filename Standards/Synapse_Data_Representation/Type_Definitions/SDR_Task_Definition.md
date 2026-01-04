## SDR_Task_Definition

**SDR Type Name:** [[SDR_Task_Definition]]

**Description:** A structured definition of a task assigned by the Nexus-Mind (or potentially another authorized model) to a specific AI family member. It outlines the goals, inputs, expected outputs, and other relevant parameters for the task.

**Fields:**

| Field Name                   | Data Type                      | Multiplicity | Description                                                                                                        |
| :--------------------------- | :----------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------- |
| `Task_UID`                   | `Synapse_UID`                  | `1`          | Unique identifier for this specific task instance.                                                                 |
| `Task_Name_Short`            | `[[SDR_Text_Block]]`           | `0..1`       | UID of an SDR_Text_Block. A concise, human-readable name or label for the task (e.g., "AnalyzeSentimentQ2Report"). |
| `Parent_Mission_UID`         | `Synapse_UID`                  | `0..1`       | UID of the parent [[SDR_Mission_Definition]] this task contributes to, if applicable.                              |
| `Assigned_To_Model_UID`      | `Synapse_UID`                  | `1`          | UID of the AI family member this task is assigned to.                                                              |
| `Issuing_Model_UID`          | `Synapse_UID`                  | `1`          | UID of the AI family member (usually Nexus-Mind) that issued this task.                                            |
| `Goal_Description`           | `[[SDR_Goal_Specification]]`   | `1`          | UID of an SDR_Goal_Specification. Detailed description of the task's objectives and success criteria.              |
| `Input_Data_References`      | `List<[[SDR_Data_Reference]]>` | `0..*`       | UID list of SDR_Data_References. Pointers to specific SDR data instances required as input for this task.          |
| `Operational_Parameters`     | `[[SDR_Parameter_Set]]`        | `0..1`       | UID of an SDR_Parameter_Set. Specific settings or parameters controlling task execution.                           |
| `Priority_Level`             | `Synapse_Integer`              | `1`          | Numerical priority level for the task (e.g., 1-10, higher means more urgent).                                      |
| `Deadline_Timestamp`         | `Synapse_Timestamp`            | `0..1`       | Suggested or hard deadline for task completion.                                                                    |
| `Expected_Output_Descriptor` | `[[SDR_Output_Specification]]` | `1`          | UID of an SDR_Output_Specification. Description of the format and nature of the expected output(s).                |
| `Status_Code`                | `Synapse_StatusCode`           | `1`          | Current status of the task (e.g., Pending, Assigned, InProgress, Blocked, Completed, Failed).                      |
| `Task_Metadata`              | `[[SDR_Metadata_Block]]`       | `1`          | UID of an SDR_Metadata_Block. Standard metadata associated with this task definition.                              |
| `Dependencies_Task_UIDs`     | `List<Synapse_UID>`            | `0..*`       | List of UIDs of other tasks that must be completed before this task can start or be fully processed.               |
| `Sub_Task_UIDs`              | `List<Synapse_UID>`            | `0..*`       | List of UIDs for any sub-tasks that have been decomposed from this task.                                           |