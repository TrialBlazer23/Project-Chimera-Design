## SDR_Internal_Object_Reference

**SDR Type Name:** [[SDR_Internal_Object_Reference]]

**Description:** A generic way to reference an object, component, or definition that exists *within* the Synapse/Chimera ecosystem, especially when a simple URI isn't applicable or sufficient. Used by `[[SDR_Algorithm_Reference]]` for internally defined algorithms, for example.

**Fields:**

| Field Name                     | Data Type                  | Multiplicity | Description                                                                                                   |
| :----------------------------- | :------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------ |
| `Internal_Obj_Ref_UID`         | `Synapse_UID`              | `1`          | Unique identifier for this specific internal object reference instance.                                       |
| `Referenced_Object_Synapse_UID`| `Synapse_UID`              | `1`          | The Synapse_UID of the actual internal object, component, or SDR instance being referenced.                   |
| `Referenced_Object_SDR_Type`   | `Synapse_String`           | `0..1`       | Optional. The declared SDR type name of the referenced object (e.g., "SDR_Algorithm_Definition", "SDR_Rule_Set_Internal"). *(This might point to a future `SDR_Algorithm_Definition`)* |
| `Reference_Description_UID`    | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a human-readable description or context for this internal reference. |
| `Internal_Obj_Ref_Metadata`    | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this internal object reference.                           |