## SDR_Property_Item

**SDR Type Name:** [[SDR_Property_Item]]

**Description:** Represents a single key-value pair used to describe a property or attribute of an `[[SDR_Knowledge_Graph_Element]]` (Node or Edge) or potentially other SDR structures that need flexible, itemized properties.

**Fields:**

| Field Name             | Data Type                  | Multiplicity | Description                                                                                                                               |
| :--------------------- | :------------------------- | :----------- | :---------------------------------------------------------------------------------------------------------------------------------------- |
| `Property_Item_UID`    | `Synapse_UID`              | `1`          | Unique identifier for this specific property item instance.                                                                               |
| `Property_Key_UID`     | `Synapse_UID`              | `1`          | UID of an [[SDR_Semantic_Tag]] or [[SDR_Vocabulary_Term]] representing the name or type of the property (e.g., "Color", "PopulationSize", "CreationDate"). |
| `Property_Value_Type`  | `Synapse_String`           | `1`          | Indicates the data type of `Property_Value_Content` (e.g., "Synapse_String", "Synapse_Integer", "Synapse_Boolean", "Synapse_UID", "SDR_Reference"). |
| `Property_Value_Content`| `Synapse_String`           | `1`          | The actual value of the property, stored as a string. Its interpretation depends on `Property_Value_Type`. If type is "SDR_Reference", this holds a Synapse_UID pointing to another SDR instance. |
| `Unit_Of_Measure_UID`  | `Synapse_UID`              | `0..1`       | UID of an [[SDR_Vocabulary_Term]] or [[SDR_Text_Block]] if the property value is numerical and has a unit (e.g., "meters", "kilograms").     |
| `Property_Metadata`    | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this property item (e.g., source of this specific property value, timestamp).              |