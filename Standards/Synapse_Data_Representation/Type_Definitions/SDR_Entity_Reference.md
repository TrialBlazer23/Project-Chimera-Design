## SDR_Entity_Reference

**SDR Type Name:** [[SDR_Entity_Reference]]

**Description:** Provides a standardized way to refer to an entity, which could be an AI model, a human user, an external system, or any other identifiable actor or component relevant to Project Chimera.

**Fields:**

| Field Name             | Data Type                  | Multiplicity | Description                                                                                                 |
| :--------------------- | :------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------- |
| `Entity_Ref_UID`       | `Synapse_UID`              | `1`          | Unique identifier for this specific entity reference instance.                                              |
| `Referenced_Entity_UID`| `Synapse_UID`              | `1`          | The unique identifier of the actual entity being referenced.                                                |
| `Entity_Type_UID`      | `Synapse_UID`              | `1`          | UID of an `[[SDR_Vocabulary_Term]]` specifying the type of entity (e.g., "AI_Model_Instance", "Human_User_ID", "External_System_ID", "Organization_ID"). |
| `Entity_Name_UID`      | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a human-readable name or label for the referenced entity.          |
| `Entity_Role_UID`      | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` describing the role of this entity in the current context.              |
| `Entity_Ref_Metadata`  | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this entity reference.                                  |