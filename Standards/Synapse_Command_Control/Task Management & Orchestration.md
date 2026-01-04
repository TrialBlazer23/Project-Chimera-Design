##Primarily driven by the [[The Nexus Mind]]

[[DEFINE_MISSION]]

Purpose: Establishes a high-level objective for the entire AI family or a significant subset.

- **Parameters:** [[Mission_UID]] (Unique ID for this mission), [[HighLevelGoal_Descriptor_SDR]] (Pointer to an SDR structure detailing the goal), [[Constraints_Bundle_SDR]] (Pointer to SDR for any operational constraints, ethical guidelines from Philosopher, etc.), [[Priority_Level]].

- **Typical Flow:** Nexus-Mind broadcasts or self-addresses to internalize the overarching mission.

[[INITIATE_TASK]]

Purpose: The Nexus-Mind assigns a specific, decomposed task to a family member.

Parameters: [[TargetModel_UID]] (e.g., Archivist, Narrator), [[Task_UID, Parent_Mission_UID_Optional]], [[Goal_Descriptor_SDR]], [[Input_Data_UIDs_SDR_Optional]] (Pointers to necessary data), [[Operational_Parameters_SDR]], [[Priority_Level]], [[Deadline_Timestamp_Optional]].

Typical Flow: Nexus-Mind to a specific Sub-Model.

[[CANCEL_TASK]]

**Purpose:** To halt an ongoing task.

- **Parameters:** [[Task_UID]], [[Reason_Code_Optional]].

- **Typical Flow:** Nexus-Mind to a Sub-Model.

[[MODIFY_TASK_PARAMETERS]]

- **Purpose:** To adjust the parameters of an ongoing task.

- **Parameters:** [[Task_UID]], [[Updated_Parameters_SDR]].

- **Typical Flow:** Nexus-Mind to a Sub-Model.