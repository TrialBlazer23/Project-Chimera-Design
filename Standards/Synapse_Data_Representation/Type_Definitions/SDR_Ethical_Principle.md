## SDR_Ethical_Principle

**SDR Type Name:** [[SDR_Ethical_Principle]]

**Description:** Represents a fundamental ethical principle or value that can underpin more specific `[[SDR_Ethical_Guideline]]` instances. It's often a broad normative statement.

**Fields:**

| Field Name                   | Data Type                  | Multiplicity | Description                                                                                                |
| :--------------------------- | :------------------------- | :----------- | :--------------------------------------------------------------------------------------------------------- |
| `Ethical_Principle_UID`    | `Synapse_UID`              | `1`          | Unique identifier for this specific ethical principle instance.                                            |
| `Principle_Name_UID`         | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` or `[[SDR_Vocabulary_Term]]` providing a concise name (e.g., "Beneficence", "Justice"). |
| `Principle_Statement_UID`    | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` containing the core statement of the principle.                           |
| `Principle_Elaboration_UID`  | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` providing further explanation or interpretation.                            |
| `Philosophical_Basis_UID`    | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` or reference to `[[SDR_Abstract_Concept_Representation]]` describing its philosophical origins or justifications. |
| `Ethical_Principle_Metadata` | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this ethical principle.                                |