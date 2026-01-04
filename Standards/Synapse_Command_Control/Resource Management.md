##Primarily Nexus-Mind

[[ALLOCATE_COMPUTE_RESOURCE]]

- **Purpose:** To assign processing power, memory, or other computational assets.

- **Parameters:** [[Target_Model_UID]] or [[Task_UID]], [[Resource_Type_Code]], [[Amount_Specification]], [[Duration_Limit_Optional]], [[Priority_Flag]].

- **Typical Flow:** Nexus-Mind to the underlying system or directly to models if they manage their own fine-grained resources.

[[RELEASE_COMPUTE_RESOURCE]]

- **Purpose:** To free up allocated resources.

- **Parameters:** [[Resource_Allocation_UID]] (ID of the allocation to be released).

- **Typical Flow:** Nexus-Mind or model upon task completion.

