## SDR_Text_Block

**SDR Type Name:** [[SDR_Text_Block]]

**Description:** A standardized structure for holding textual information. This allows for consistent handling of text across different parts of the Synapse protocol, including support for language tagging and semantic annotations if needed in the future.

**Fields:**

| Field Name         | Data Type                   | Multiplicity | Description                                                                          |
| :----------------- | :-------------------------- | :----------- | :----------------------------------------------------------------------------------- |
| `Text_Block_UID`   | `Synapse_UID`               | `1`          | Unique identifier for this specific instance of a text block.                        |
| `Text_Content`     | `Synapse_String`            | `1`          | The actual textual content.                                                          |
| `Language_Code`    | `Synapse_String`            | `0..1`       | Language code for the text (e.g., "en-US", "de-DE") following IETF BCP 47 standard.    |
| `Encoding`         | `Synapse_String`            | `0..1`       | Text encoding if not standard (e.g., UTF-8 is assumed default).                      |
| `Semantic_Type`    | `[[SDR_Semantic_Tag]]`      | `0..1`       | UID of an SDR_Semantic_Tag. Optional tag indicating the type of text (e.g., "Name", "Description", "Instruction"). |
| `Text_Metadata`    | `[[SDR_Metadata_Block]]`    | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata associated with this text block.       |