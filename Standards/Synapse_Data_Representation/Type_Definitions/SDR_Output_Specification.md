## SDR_Output_Specification

**SDR Type Name:** [[SDR_Output_Specification]]

**Description:** Describes the expected format, structure, and nature of the output(s) from a task or operation.

**Fields:**

| Field Name             | Data Type                 | Multiplicity | Description                                                                                                         |
| :--------------------- | :------------------------ | :----------- | :------------------------------------------------------------------------------------------------------------------ |
| `Output_Spec_UID`      | `Synapse_UID`             | `1`          | Unique identifier for this output specification instance.                                                           |
| `Expected_SDR_Type`    | `Synapse_String`          | `1`          | The primary SDR type name expected for the output (e.g., "SDR_Narrative_Document", "SDR_Trend_Analysis_Report").    |
| `Output_Description`   | `[[SDR_Text_Block]]`      | `0..1`       | UID of an SDR_Text_Block. A human-readable description of what the output should represent.                         |
| `Delivery_Format`      | `[[SDR_Semantic_Tag]]`    | `0..1`       | UID of an SDR_Semantic_Tag. Specifies if there's a particular delivery format (e.g., "SummaryOnly", "FullDataSet"). |
| `Validation_Criteria`  | `List<[[SDR_Criterion]]>` | `0..*`       | UID list of SDR_Criterion instances. Criteria that the output must meet to be considered valid/acceptable.          |
| `Output_Spec_Metadata` | `[[SDR_Metadata_Block]]`  | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this output specification.                                      |