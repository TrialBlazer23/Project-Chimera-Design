## SDR_Data_Source_Descriptor

**SDR Type Name:** [[SDR_Data_Source_Descriptor]]

**Description:** Provides a detailed description of an external or internal source from which the Archivist ingests or manages data. This helps in tracking data provenance, reliability, and update cycles.

**Fields:**

| Field Name                   | Data Type                         | Multiplicity | Description                                                                                                                                |
| :--------------------------- | :-------------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| `Data_Source_UID`            | `Synapse_UID`                     | `1`          | Unique identifier for this specific data source descriptor.                                                                                |
| `Source_Name_UID`            | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` giving a human-readable name for the data source (e.g., "NASA Exoplanet Archive API", "InternalSystemLogStream"). |
| `Source_Type_UID`            | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` categorizing the source (e.g., "External_API", "Database_Internal", "Document_Repository", "Stream_Feed"). |
| `Source_Location_URI_UID`    | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` containing the URI, connection string, or path to access the data source.                                   |
| `Access_Credentials_Ref_UID` | `Synapse_UID`                     | `0..1`       | UID pointing to a secure reference for access credentials if required (actual credentials would not be stored here).                       |
| `Data_Format_Description_UID`| `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Schema_Reference]]` describing the format of the data from this source (e.g., JSON, CSV, XML, specific API schema). *(Introduces `SDR_Schema_Reference`)* |
| `Update_Frequency_UID`       | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` describing how often the data is updated (e.g., "RealTime", "Daily", "AdHoc"). |
| `Data_Reliability_Score_UID` | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Qualitative_Assessment]]` or `[[SDR_Confidence_Score_Item]]` assessing the general reliability of this source.         |
| `Data_Owner_Steward_UID`     | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Entity_Reference]]` indicating the owner or steward of the data source.                                                 |
| `Last_Ingest_Timestamp`      | `Synapse_Timestamp`               | `0..1`       | Timestamp of the last successful data ingestion from this source.                                                                          |
| `Data_Source_Metadata`       | `[[SDR_Metadata_Block]]`          | `1`          | UID of an `[[SDR_Metadata_Block]]` for this data source descriptor.                                                                        |