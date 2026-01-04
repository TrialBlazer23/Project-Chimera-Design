##Primarily Diagnostician & Nexus-Mind

[[ACKNOWLEDGE_MESSAGE]]

- **Purpose:** Confirms receipt and basic validation of an [[SCC]] message. Essential for reliable communication.

- **Parameters:** [[Acknowledged_Message_UID]], [[Acknowledgement_Status_Code]] (e.g., [[Received_OK]], [[Parse_Error]], [[Invalid_Command]]).

- **Typical Flow:** Any recipient model back to the sender.

[[ISSUE_ALERT]]

- **Purpose:** To flag a critical issue, anomaly, or urgent situation.

- **Parameters:** [[Issuing_Model_UID]], [[Alert_Code]] (Standardized list, e.g., [[Model_Unresponsive]], [[Ethical_Boundary_Violation]], [[Resource_Depletion]]), [[Severity_Level]], [[Affected_Component_UID_Optional]], [[Diagnostic_Info_UID_SDR_Optional]].

- **Typical Flow:** Diagnostician to Nexus-Mind; any model detecting a critical error to Diagnostician and/or Nexus-Mind.

[[REQUEST_DIAGNOSTIC_CHECK]]

- **Purpose:** To initiate a health or performance check on a component.

- **Parameters:** [[Requesting_Model_UID]], [[Target_Component_UID]] (Could be a sub-model, a specific process, or even a Synapse channel), [[Diagnostic_Routine_UID_Optional]].

- **Typical Flow:** Nexus-Mind to Diagnostician; Diagnostician to itself or other components.

[[INITIATE_RECOVERY_ACTION]]

- **Purpose:** To trigger a predefined recovery or corrective procedure.

- **Parameters:** [[Issuing_Model_UID]] (Usually Diagnostician), [[Target_Component_UID]], [[Recovery_Protocol_UID]], [[Execution_Parameters_SDR]].

- **Typical Flow:** Diagnostician to an affected model or system service.
