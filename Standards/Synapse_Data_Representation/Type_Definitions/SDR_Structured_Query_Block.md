## SDR_Structured_Query_Block

**SDR Type Name:** [[SDR_Structured_Query_Block]]

**Description:** Contains a query formulated in a specific, formal query language (e.g., SPARQL, SQL). This is referenced by `[[SDR_Data_Query]]` when `Query_Language` is not natural language.

**Fields:**

| Field Name                 | Data Type                  | Multiplicity | Description                                                                                              |
| :------------------------- | :------------------------- | :----------- | :------------------------------------------------------------------------------------------------------- |
| `Structured_Query_UID`     | `Synapse_UID`              | `1`          | Unique identifier for this specific structured query block.                                              |
| `Query_Language_Used_UID`  | `Synapse_UID`              | `1`          | UID of an `[[SDR_Vocabulary_Term]]` specifying the query language (e.g., "SPARQL", "Cypher", "SQL").         |
| `Query_String`             | `Synapse_String`           | `1`          | The full query string formulated in the specified query language.                                        |
| `Query_Validation_Status`  | `[[SDR_Validation_Result]]`| `0..1`       | UID of an SDR_Validation_Result. Optional result from validating the query syntax against its language. *(Introduces `SDR_Validation_Result`)* |
| `Structured_Query_Metadata`| `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this structured query.                               |