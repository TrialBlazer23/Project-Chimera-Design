## SDR_Data_Path_Expression

**SDR Type Name:** [[SDR_Data_Path_Expression]]

**Description:** Represents a structured path to a specific data field or element within an SDR instance, or potentially within the broader AI knowledge context. It typically uses dot notation for navigating through nested structures and bracket notation for accessing elements in lists or maps.

**Fields:**

| Field Name                 | Data Type                | Multiplicity | Description                                                                                                                                                        |
| :------------------------- | :----------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Path_Expression_UID`      | `Synapse_UID`            | `1`          | Unique identifier for this specific data path expression instance.                                                                                                 |
| `Path_String`              | `Synapse_String`         | `1`          | The actual path expression string (e.g., "Task_UID.Status_Code", "Input_Data_References[0].Referenced_SDR_UID", "KnowledgeGraph.Node[Concept_X].Property[Color]"). |
| `Root_Context_SDR_UID`     | `Synapse_UID`            | `0..1`       | Optional UID of the root SDR instance or a well-known context (e.g., "Current_Task_SDR") to which this path is relative. If absent, context might be implicit.     |
| `Path_Semantics`           | `[[SDR_Text_Block]]`     | `0..1`       | UID of an SDR_Text_Block. Optional human-readable description of what the path is intended to point to or how it should be interpreted.                            |
| `Path_Expression_Metadata` | `[[SDR_Metadata_Block]]` | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this data path expression.                                                                                     |

**Notes on `Path_String` Syntax:**

* **Dot Notation:** Used to access fields within an SDR object (e.g., `MyTask.Task_UID`).
* **Bracket Notation for Lists:** Used to access elements in a list by index (e.g., `MyTask.Input_Data_References[0]`). Indices would typically be zero-based.
* **Bracket Notation for Maps/Keys (Future):** If we define SDR structures that are key-value maps, bracket notation could also be used with string keys (e.g., `MyConcept.Properties["Color"]`).
* The exact parsing rules and supported features of this path language would be part of the Synapse Definition Framework (SDF).