##Used by all family members

[[REQUEST_DATA]]

- **Purpose:** To ask for specific information.

- **Parameters:** [[Query_Descriptor_SDR]] (Detailed query), [[Desired_Format_SDR_Optional]], [[Requester_UID]], [[Urgency_Flag]].

- **Typical Flow:** Any model to Archivist, or between any models for intermediary data.

[[PROVIDE_DATA]]

- **Purpose:** To send data, either in response to a [[REQUEST_DATA]] or proactively.

- **Parameters:** [[Origin_Request_UID_Optional]] (Links to the original request if applicable), [[Data_Payload_UID_SDR]] (Pointer to the actual data in SDR format), [[Confidence_Score_Optional]], [[Metadata_SDR]].

- **Typical Flow:** Archivist to requester, or any model sharing processed information.

[[SHARE_INSIGHT]]

- **Purpose:** To distribute a derived understanding, concept, or pattern.

- **Parameters:** [[Insight_Payload_UID_SDR]] (The insight itself), [[Source_Model_UID]], [[Evidence_UIDs_SDR_Optional]], [[Relevance_Tags_SDR]].

- **Typical Flow:** Philosopher sharing ethical implications, Archivist sharing trend analysis, Narrator sharing a thematic concept.

[[REPORT_STATUS_PROGRESS]]

- **Purpose:** To update on the current state of a task or general well-being.

- **Parameters:** [[Reporting_Model_UID]], [[Task_UID_Optional]], [[Current_Status_Code]] (e.g., InProgress, Blocked, Completed), [[Progress_Metric_Optional]] (e.g., 75% done), [[ETA_Timestamp_Optional]], [[Issues_Log_UID_SDR_Optional]].

- **Typical Flow:** Sub-Model to Nexus-Mind; Diagnostician reporting on system health.

[[REPORT_FINDINGS_OUTPUT]]

- **Purpose:** To deliver the final or intermediate results of a task.

- **Parameters:** [[Reporting_Model_UID]], [[Task_UID]], [[Output_Payload_UID_SDR]] (Pointer to the result), [[Summary_Descriptor_SDR]].

- **Typical Flow:** Sub-Model to Nexus-Mind or to another Sub-Model if part of a chained task.