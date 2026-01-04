## SDR_Root_Cause_Analysis_Output

**SDR Type Name:** [[SDR_Root_Cause_Analysis_Output]]

**Description:** Structures the findings of a root cause analysis performed by the Diagnostician in response to an anomaly or system issue.

**Fields:**

| Field Name                    | Data Type                         | Multiplicity | Description                                                                                                                                |
| :---------------------------- | :-------------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| `RCA_Output_UID`              | `Synapse_UID`                     | `1`          | Unique identifier for this specific root cause analysis output.                                                                            |
| `Related_Anomaly_Report_UID`  | `Synapse_UID`                     | `1`          | UID of the `[[SDR_Anomaly_Report]]` that triggered this analysis.                                                                          |
| `Analysis_Start_Timestamp`    | `Synapse_Timestamp`               | `1`          | Timestamp when the root cause analysis began.                                                                                              |
| `Analysis_End_Timestamp`      | `Synapse_Timestamp`               | `1`          | Timestamp when the root cause analysis concluded.                                                                                          |
| `Identified_Root_Causes_UIDs` | `List<Synapse_UID>`               | `1..*`       | List of UIDs, each pointing to an `[[SDR_Causal_Factor_Description]]` detailing an identified root cause.                                  |
| `Analysis_Methodology_UID`    | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` describing the methodology or diagnostic routines used for the analysis.                                      |
| `Confidence_In_Findings_UID`  | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Confidence_Score_Item]]` indicating the Diagnostician's confidence in the identified root causes.                           |
| `Recommended_Actions_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Recommended_Action]]` (e.g., initiate recovery, log for learning, modify configuration).           |
| `Preventative_Measures_UIDs`  | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an `[[SDR_Recommended_Action]]` specifically aimed at preventing recurrence.                                |
| `RCA_Output_Metadata`         | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this analysis output.                                                                  |