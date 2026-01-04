## SDR_Vocabulary_Term

**SDR Type Name:** [[SDR_Vocabulary_Term]]

**Description:** Represents a single term or entry within an [[SDR_Vocabulary_Definition]].

**Fields:**

| Field Name              | Data Type              | Multiplicity | Description                                                                                                  |
| :---------------------- | :--------------------- | :----------- | :----------------------------------------------------------------------------------------------------------- |
| `Term_UID`              | `Synapse_UID`          | `1`          | Unique identifier for this specific vocabulary term instance.                                                |
| `Parent_Vocabulary_UID` | `Synapse_UID`          | `1`          | UID of the [[SDR_Vocabulary_Definition]] this term belongs to.                                               |
| `Term_Value`            | `Synapse_String`       | `1`          | The actual string value of the term (e.g., "InProgress", "HighlyConfidential").                              |
| `Term_Label`            | [[SDR_Text_Block]]     | `0..1`       | UID of an SDR_Text_Block. An optional human-readable label for the term, if different from Term_Value.       |
| `Term_Description`      | [[SDR_Text_Block]]     | `0..1`       | UID of an SDR_Text_Block. A definition or explanation of the term's meaning and usage within the vocabulary. |
| `Term_Metadata`         | [[SDR_Metadata_Block]] | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata associated with this vocabulary term.                        |