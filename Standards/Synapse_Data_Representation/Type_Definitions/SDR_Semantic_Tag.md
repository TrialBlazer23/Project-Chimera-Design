## SDR_Semantic_Tag

**SDR Type Name:** [[SDR_Semantic_Tag]]

**Description:** A standardized tag used to convey semantic meaning or categorization for a piece of data or an entity. This helps in understanding the role, nature, or context of the tagged item. Tags could be from a controlled vocabulary or defined within the SDF.

**Fields:**

| Field Name          | Data Type                  | Multiplicity | Description                                                                                                |
| :------------------ | :------------------------- | :----------- | :--------------------------------------------------------------------------------------------------------- |
| `Semantic_Tag_UID`  | `Synapse_UID`              | `1`          | Unique identifier for this specific semantic tag instance.                                                 |
| `Tag_Value`         | `Synapse_String`           | `1`          | The actual value of the tag (e.g., "Name", "Description", "PrimaryInput", "EthicalConsideration", "SummaryOnly"). |
| `Tag_Vocabulary_UID`| `Synapse_UID`              | `0..1`       | Optional UID pointing to an [[SDR_Vocabulary_Definition]] if this tag belongs to a specific controlled vocabulary. |
| `Tag_Description`   | `[[SDR_Text_Block]]`       | `0..1`       | UID of an SDR_Text_Block. Optional human-readable description of the tag's meaning or intended use.       |
| `Tag_Metadata`      | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata associated with this semantic tag instance.                |