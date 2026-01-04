## SDR_Example_Case

**SDR Type Name:** [[SDR_Example_Case]]

**Description:** Provides a concrete example or instance that illustrates (or counter-illustrates) an `[[SDR_Abstract_Concept_Representation]]` or an `[[SDR_Ethical_Guideline]]`.

**Fields:**

| Field Name               | Data Type                  | Multiplicity | Description                                                                                                   |
| :----------------------- | :------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------ |
| `Example_Case_UID`       | `Synapse_UID`              | `1`          | Unique identifier for this specific example case instance.                                                    |
| `Case_Description_UID`   | `Synapse_UID`              | `1`          | UID of an `[[SDR_Text_Block]]` or another relevant SDR (e.g., `[[SDR_NarrativeElement]]`) describing the case. |
| `Illustrates_Concept_UID`| `Synapse_UID`              | `1`          | UID of the `[[SDR_Abstract_Concept_Representation]]` or `[[SDR_Ethical_Guideline]]` this case pertains to. |
| `Example_Type`           | `Synapse_String`           | `1`          | Type of example: "Illustrative" (positive example) or "Counter" (negative example).                           |
| `Explanation_UID`        | `Synapse_UID`              | `0..1`       | UID of an `[[SDR_Text_Block]]` explaining how this case illustrates or counters the concept/guideline.       |
| `Example_Case_Metadata`  | `[[SDR_Metadata_Block]]`   | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata for this example case.                                      |