## SDR_Recommended_Action

**SDR Type Name:** [[SDR_Recommended_Action]]

**Description:** Describes a specific action recommended by the Diagnostician (or potentially another analytical model) in response to an issue, often as part of an `[[SDR_Root_Cause_Analysis_Output]]` or for preventative maintenance.

**Fields:**

| Field Name                    | Data Type                         | Multiplicity | Description                                                                                                                                   |
| :---------------------------- | :-------------------------------- | :----------- | :-------------------------------------------------------------------------------------------------------------------------------------------- |
| `Recommended_Action_UID`      | `Synapse_UID`                     | `1`          | Unique identifier for this specific recommended action instance.                                                                              |
| `Action_Title_UID`            | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a concise title for the recommended action (e.g., "RevertConfigurationChangeX", "RetrainModelY").      |
| `Action_Detailed_Description_UID`| `Synapse_UID`                    | `1`          | UID of an `[[SDR_Text_Block]]` providing a detailed explanation of what the action entails.                                                  |
| `Action_Type_UID`             | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` specifying the type of action (e.g., "Modify_Configuration", "Execute_Recovery_Protocol", "Escalate_To_Human", "Log_For_Learning", "No_Action_Required"). |
| `Target_Component_UID`        | `Synapse_UID`                     | `0..1`       | Optional UID of the specific AI family member, module, or system component that this action targets.                                         |
| `Action_Parameters_SDR_UID`   | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Parameter_Set]]` if the action requires specific parameters for execution.                                                  |
| `Rationale_For_Action_UID`    | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Causal_Factor_Description]]` explaining why this action is recommended.                                |
| `Expected_Outcome_UID`        | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` describing the anticipated positive outcome if this action is successfully implemented.                         |
| `Urgency_Priority_Level_UID`  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` (e.g., "Immediate", "High", "Medium", "Low") or a `Synapse_Integer` indicating urgency/priority.        |
| `Estimated_Effort_UID`        | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Qualitative_Assessment]]` estimating the effort or resources required.                               |
| `Recommended_Action_Metadata` | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this recommended action.                                                                  |