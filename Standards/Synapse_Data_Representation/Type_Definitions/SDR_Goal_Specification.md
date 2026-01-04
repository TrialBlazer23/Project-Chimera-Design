## SDR_Goal_Specification

**SDR Type Name:** [[SDR_Goal_Specification]]

**Description:** A detailed description of a goal or objective, often used within task definitions or mission statements. It outlines what needs to be achieved and may include success criteria.

**Fields:**

| Field Name              | Data Type                         | Multiplicity | Description                                                                                |
| :---------------------- | :-------------------------------- | :----------- | :----------------------------------------------------------------------------------------- |
| `Goal_Spec_UID`         | `Synapse_UID`                     | `1`          | Unique identifier for this goal specification instance.                                    |
| `Goal_Summary`          | `[[SDR_Text_Block]]`              | `1`          | UID of an SDR_Text_Block. A concise summary statement of the goal.                       |
| `Goal_Details`          | `[[SDR_Text_Block]]`              | `0..1`       | UID of an SDR_Text_Block. More detailed elaboration of the goal, if necessary.             |
| `Success_Criteria`      | `List<[[SDR_Criterion]]>`         | `0..*`       | UID list of SDR_Criterion instances. Specific, measurable criteria for determining goal achievement. |
| `Key_Performance_Indicators`| `List<[[SDR_KPI_Descriptor]]>` | `0..*`       | UID list of SDR_KPI_Descriptors. Indicators that will be tracked to measure progress/success. |
| `Target_Outcome_SDR_UID`| `Synapse_UID`                     | `0..1`       | UID of an SDR instance representing the desired state or outcome upon goal completion.   |
| `Goal_Metadata`         | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Optional metadata associated with this goal specification.    |