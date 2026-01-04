## SDR_Schema_Reference

**SDR Type Name:** [[SDR_Schema_Reference]]

**Description:** Provides a reference to a data schema definition, which could be an internal Synapse SDR definition or an external schema language (e.g., JSON Schema, XSD). Used by `[[SDR_Data_Source_Descriptor]]` to describe the format of ingested data.

**Fields:**

| Field Name               | Data Type                  | Multiplicity | Description                                                                                               |
| :----------------------- | :------------------------- | :----------- | :-------------------------------------------------------------------------------------------------------- |
| `Schema_Ref_UID`         | `Synapse_UID`              | `1`          | Unique identifier for this specific schema reference instance.                                            |
| `Schema_Name_UID`        | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` providing a human-readable name for the schema.                          |
| `Schema_Language_UID`    | `Synapse_UID`              | `1`          | UID of an `[[SDR_Vocabulary_Term]]` specifying the schema language (e.g., "Synapse_SDF", "JSON_Schema", "XSD", "Avro"). |
| `Schema_Identifier_URI`  | `Synapse_String`           | `0..1`       | A URI or other persistent identifier pointing to the schema definition itself, if external.             |
| `Schema_Version`         | `Synapse_String`           | `0..1`       | Optional version string for the referenced schema.                                                        |
| `Internal_SDR_Type_Name` | `Synapse_String`           | `0..1`       | If Schema_Language is "Synapse_SDF", this field holds the name of the referenced SDR type (e.g., "SDR_MyCustomData"). |
| `Schema_Ref_Metadata`    | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this schema reference.                                |