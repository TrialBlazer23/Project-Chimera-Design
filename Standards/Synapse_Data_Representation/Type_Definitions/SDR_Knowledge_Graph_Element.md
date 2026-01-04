## SDR_Knowledge_Graph_Element

**SDR Type Name:** [[SDR_Knowledge_Graph_Element]]

**Description:** Represents a single element within the Archivist's knowledge graph, which can be either a Node (representing an entity or concept) or an Edge (representing a relationship between two nodes).

**Fields:**

| Field Name              | Data Type                         | Multiplicity | Description                                                                                                                               |
| :---------------------- | :-------------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------- |
| `KG_Element_UID`        | `Synapse_UID`                     | `1`          | Unique identifier for this specific knowledge graph element instance.                                                                     |
| `Element_Type`          | `Synapse_String`                  | `1`          | Indicates the type of KG element: "Node" or "Edge".                                                                                       |
| `Node_Type_UID`         | `Synapse_UID`                     | `0..1`       | *(Applicable if Element_Type is "Node")* UID of an [[SDR_Semantic_Tag]] or [[SDR_Vocabulary_Term]] specifying the type of node (e.g., "Person", "Location", "AbstractConcept"). |
| `Node_Label`            | `[[SDR_Text_Block]]`              | `0..1`       | *(Applicable if Element_Type is "Node")* UID of an SDR_Text_Block. A primary human-readable label for the node.                             |
| `Edge_Type_UID`         | `Synapse_UID`                     | `0..1`       | *(Applicable if Element_Type is "Edge")* UID of an [[SDR_Semantic_Tag]] or [[SDR_Vocabulary_Term]] specifying the type of relationship (e.g., "LocatedIn", "HasProperty", "Causes"). |
| `Source_Node_UID`       | `Synapse_UID`                     | `0..1`       | *(Applicable if Element_Type is "Edge")* The UID of the source/subject `SDR_Knowledge_Graph_Element` (which must be a Node).                |
| `Target_Node_UID`       | `Synapse_UID`                     | `0..1`       | *(Applicable if Element_Type is "Edge")* The UID of the target/object `SDR_Knowledge_Graph_Element` (which must be a Node).                 |
| `Is_Directed_Edge`      | `Synapse_Boolean`                 | `0..1`       | *(Applicable if Element_Type is "Edge")* True if the relationship is directed (source -> target), False if undirected. Default is true.    |
| `Properties`            | `List<[[SDR_Property_Item]]>`     | `0..*`       | UID list of SDR_Property_Item instances. Key-value pairs describing attributes of the Node or Edge.                                        |
| `KG_Element_Metadata`   | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Metadata for this KG element (e.g., source of this fact, confidence, timestamp of assertion).                |