## SDR_Mission_Definition

**SDR Type Name:** [[SDR_Mission_Definition]]

**Description:** Defines a high-level mission or overarching objective for the AI family, typically set by the Nexus-Mind. It provides strategic context for one or more `[[SDR_Task_Definition]]` instances.

**Fields:**

| Field Name                    | Data Type                         | Multiplicity | Description                                                                                                                                 |
| :---------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------ |
| `Mission_UID`                 | `Synapse_UID`                     | `1`          | Unique identifier for this specific mission definition instance.                                                                            |
| `Mission_Name_Text_UID`       | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a concise, human-readable name for the mission (e.g., "AnalyzeQ2MarketTrends", "DevelopEthicalProtocolX"). |
| `Overall_Goal_Specification_UID`| `Synapse_UID`                   | `1`          | UID of an `[[SDR_Goal_Specification]]` detailing the primary strategic goal of the mission.                                                 |
| `Strategic_Importance_UID`    | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Qualitative_Assessment]]` or `[[SDR_Vocabulary_Term]]` indicating the mission's strategic importance or priority.       |
| `Applicable_Ethical_Guidelines_UIDs`| `List<Synapse_UID>`           | `0..*`       | List of UIDs pointing to `[[SDR_Ethical_Guideline]]` instances that must be adhered to during this mission.                               |
| `Key_Stakeholder_UIDs`        | `List<Synapse_UID>`               | `0..*`       | Optional list of UIDs pointing to `[[SDR_Entity_Reference]]` (e.g., for human overseers or specific AI models with a vested interest). *(Introduces `SDR_Entity_Reference`)* |
| `Associated_Task_UIDs`        | `List<Synapse_UID>`               | `0..*`       | List of UIDs for `[[SDR_Task_Definition]]` instances that are part of this mission. This list might be populated as tasks are decomposed.      |
| `Expected_Mission_Duration_UID`| `Synapse_UID`                    | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Time_Duration]]` estimating the expected duration. *(Introduces `SDR_Time_Duration`)* |
| `Mission_Status_UID`          | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` indicating the current status of the mission (e.g., "Planned", "Active", "Completed", "Aborted").      |
| `Mission_Metadata`            | `[[SDR_Metadata_Block]]`          | `1`          | UID of an `[[SDR_Metadata_Block]]` for this mission.                                                                                      |