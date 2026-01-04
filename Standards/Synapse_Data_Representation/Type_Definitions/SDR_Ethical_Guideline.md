## SDR_Ethical_Guideline

**SDR Type Name:** [[SDR_Ethical_Guideline]]

**Description:** A formal representation of an ethical rule, principle, or heuristic formulated or applied by the Philosopher. This structure helps in ethical decision-making and analysis.

**Fields:**

| Field Name                  | Data Type                         | Multiplicity | Description                                                                                                   |
| :-------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------ |
| `Guideline_UID`             | `Synapse_UID`                     | `1`          | Unique identifier for this specific ethical guideline instance.                                               |
| `Guideline_Statement_UID`   | `Synapse_UID`                     | `1`          | UID of an [[SDR_Text_Block]] containing the core statement of the guideline (e.g., "MinimizeHarm").            |
| `Guideline_Elaboration_UID` | `Synapse_UID`                     | `0..1`       | UID of an [[SDR_Text_Block]] providing a detailed explanation, interpretation, or operationalization.        |
| `Applicability_Scope_UID`   | `Synapse_UID`                     | `0..1`       | UID of an [[SDR_Applicability_Condition]] describing the contexts or conditions where this guideline applies. |
| `Underlying_Principles_UIDs`| `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to other [[SDR_Ethical_Principle]] or [[SDR_Abstract_Concept_Representation]] instances that form the basis for this guideline. |
| `Potential_Conflicts_UIDs`  | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to other [[SDR_Ethical_Guideline]] instances with which this guideline might conflict. |
| `Exception_Clauses_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to [[SDR_Exception_Clause]] instances detailing exceptions to the guideline.         |
| `Strength_Or_Weight`        | `[[SDR_Confidence_Score_Item]]`   | `0..1`       | UID of an SDR_Confidence_Score_Item. Optional measure of the guideline's imperative strength or priority.       |
| `Guideline_Metadata`        | `[[SDR_Metadata_Block]]`          | `0..1`       | UID of an SDR_Metadata_Block. Metadata for this ethical guideline.                                            |