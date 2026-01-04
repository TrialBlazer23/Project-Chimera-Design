## SDR_Concept_Relationship

**SDR Type Name:** [[SDR_Concept_Relationship]]

**Description:** Defines a specific relationship between two abstract concepts, often used within `[[SDR_Abstract_Concept_Representation]]`.

**Fields:**

| Field Name                  | Data Type                  | Multiplicity | Description                                                                                                   |
| :-------------------------- | :------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------ |
| `Concept_Rel_UID`           | `Synapse_UID`              | `1`          | Unique identifier for this specific concept relationship instance.                                            |
| `Source_Concept_UID`        | `Synapse_UID`              | `1`          | UID of the `[[SDR_Abstract_Concept_Representation]]` that is the source or subject of the relationship.       |
| `Relationship_Type_UID`     | `Synapse_UID`              | `1`          | UID of an `[[SDR_Vocabulary_Term]]` or `[[SDR_Semantic_Tag]]` defining the type of relationship (e.g., "IsA", "PartOf", "Causes", "Influences", "OppositeOf"). |
| `Target_Concept_UID`        | `Synapse_UID`              | `1`          | UID of the `[[SDR_Abstract_Concept_Representation]]` that is the target or object of the relationship.        |
| `Relationship_Strength`     | `[[SDR_Confidence_Score_Item]]`| `0..1`       | UID of an SDR_Confidence_Score_Item. Optional measure of the strength or certainty of this relationship.     |
| `Relationship_Context_UID`  | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` providing any specific context for this relationship.                        |
| `Relationship_Metadata`     | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this concept relationship.                              |