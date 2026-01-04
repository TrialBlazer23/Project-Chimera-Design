## SDR_Vocabulary_Definition

**SDR Type Name:** [[SDR_Vocabulary_Definition]]

**Description:** Defines a controlled vocabulary, which is a set of preferred terms, tags, or codes used for consistent categorization or description within a specific domain. Often referenced by `[[SDR_Semantic_Tag]]`.

**Fields:**

| Field Name              | Data Type                         | Multiplicity | Description                                                                                                  |
| :---------------------- | :-------------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------- |
| `Vocabulary_UID`        | `Synapse_UID`                     | `1`          | Unique identifier for this specific vocabulary definition instance.                                          |
| `Vocabulary_Name`       | `[[SDR_Text_Block]]`              | `1`          | UID of an SDR_Text_Block. The human-readable name of the vocabulary (e.g., "Task Status Codes", "Content Sensitivity Levels"). |
| `Vocabulary_Description`| `[[SDR_Text_Block]]`              | `0..1`       | UID of an SDR_Text_Block. A more detailed description of the vocabulary's purpose and scope.                |
| `Managed_By_Model_UID`  | `Synapse_UID`                     | `0..1`       | Optional UID of the AI family member responsible for maintaining or curating this vocabulary.                |
| `Term_List_UIDs`        | `List<Synapse_UID>`               | `0..*`       | List of UIDs, where each UID points to an [[SDR_Vocabulary_Term]] instance belonging to this vocabulary.    |
| `Vocabulary_Metadata`   | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata associated with this vocabulary definition.                  |