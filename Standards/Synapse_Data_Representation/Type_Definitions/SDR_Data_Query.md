## SDR_Data_Query

**SDR Type Name:** [[SDR_Data_Query]]

**Description:** A structured representation of a query submitted to the Archivist (or potentially other data-holding models) to retrieve specific information.

**Fields:**

| Field Name              | Data Type                         | Multiplicity | Description                                                                                                                             |
| :---------------------- | :-------------------------------- | :----------- | :-------------------------------------------------------------------------------------------------------------------------------------- |
| `Query_UID`             | `Synapse_UID`                     | `1`          | Unique identifier for this specific query instance.                                                                                     |
| `Query_Language`        | `Synapse_String`                  | `0..1`       | Specifies the query language used if it's a formal language (e.g., "SPARQL", "SQL-like", "SynapsePath"). Defaults to "NaturalLanguageOrKeywords" for simpler queries. |
| `Query_Content_SDR_UID` | `Synapse_UID`                     | `1`          | UID of an SDR (e.g., [[SDR_Text_Block]] for natural language, or a more structured [[SDR_Structured_Query_Block]] for formal queries) containing the query itself. |
| `Target_Data_Scope_UIDs`| `List<Synapse_UID>`               | `0..*`       | Optional list of UIDs pointing to specific datasets, knowledge graph subsets, or [[SDR_Vocabulary_Definition]] UIDs to constrain the search scope. |
| `Desired_Output_Format` | `[[SDR_Output_Specification]]`    | `0..1`       | UID of an SDR_Output_Specification. Describes the preferred format or structure for the query results.                                   |
| `Max_Results`           | `Synapse_Integer`                 | `0..1`       | Optional limit on the number of results to return.                                                                                      |
| `Query_Parameters`      | `[[SDR_Parameter_Set]]`           | `0..1`       | UID of an SDR_Parameter_Set. Optional parameters to be used in query execution (e.g., date ranges, specific filters).                  |
| `Query_Metadata`        | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Metadata associated with this query (e.g., who issued it, priority).                                       |