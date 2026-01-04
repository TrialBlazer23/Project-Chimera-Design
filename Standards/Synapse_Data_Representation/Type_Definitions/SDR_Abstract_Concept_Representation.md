## SDR_Abstract_Concept_Representation

**SDR Type Name:** [[SDR_Abstract_Concept_Representation]]

**Description:** A structured representation of an abstract concept, developed or analyzed by the Philosopher. This includes its definition, relationships to other concepts, and illustrative examples.

**Fields:**

| Field Name                 | Data Type                         | Multiplicity | Description                                                                                                     |
| :------------------------- | :-------------------------------- | :----------- | :-------------------------------------------------------------------------------------------------------------- |
| `Concept_Rep_UID`          | `Synapse_UID`                     | `1`          | Unique identifier for this specific abstract concept representation instance.                                     |
| `Concept_Name_UID`         | `Synapse_UID`                     | `1`          | UID of an [[SDR_Text_Block]] or [[SDR_Vocabulary_Term]] providing the primary name for the concept.              |
| `Definition_Text_UID`      | `Synapse_UID`                     | `1`          | UID of an [[SDR_Text_Block]] containing a detailed, nuanced definition of the concept.                          |
| `Alternative_Definitions_UIDs`| `List<Synapse_UID>`             | `0..*`       | List of UIDs, each pointing to an [[SDR_Text_Block]] containing alternative or historical definitions.          |
| `Core_Attributes_UIDs`     | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an [[SDR_Property_Item]] that describes essential attributes of the concept.     |
| `Related_Concepts_UIDs`    | `List<[[SDR_Concept_Relationship]]>`| `0..*`       | UID list of SDR_Concept_Relationships. Describes how this concept relates to others (e.g., "IsA", "PartOf", "OppositeOf"). |
| `Illustrative_Examples_UIDs`| `List<Synapse_UID>`              | `0..*`       | List of UIDs, each pointing to an [[SDR_Example_Case]] that illustrates the concept.                            |
| `Counter_Examples_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs, each pointing to an [[SDR_Example_Case]] that illustrates what the concept is *not*.             |
| `Philosophical_Context_UID`| `Synapse_UID`                     | `0..1`       | UID of an [[SDR_Text_Block]] providing context from philosophical literature or schools of thought.             |
| `Concept_Metadata`         | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Metadata for this concept representation.                                       |