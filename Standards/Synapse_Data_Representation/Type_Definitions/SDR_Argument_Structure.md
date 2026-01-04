## SDR_Argument_Structure

**SDR Type Name:** [[SDR_Argument_Structure]]

**Description:** Represents a logical argument, including its premises, conclusion, and the structure of its reasoning. Used by the Philosopher for constructing and evaluating arguments.

**Fields:**

| Field Name                | Data Type                       | Multiplicity | Description                                                                                                   |
| :------------------------ | :------------------------------ | :----------- | :------------------------------------------------------------------------------------------------------------ |
| `Argument_UID`            | `Synapse_UID`                   | `1`          | Unique identifier for this specific argument structure instance.                                              |
| `Conclusion_Statement_UID`| `Synapse_UID`                   | `1`          | UID of an [[SDR_Proposition_Statement]] representing the main claim or conclusion of the argument.          |
| `Premise_Statements_UIDs` | `List<Synapse_UID>`             | `1..*`       | List of UIDs, each pointing to an [[SDR_Proposition_Statement]] that serves as a premise supporting the conclusion. |
| `Logical_Form_UID`        | `Synapse_UID`                   | `0..1`       | UID of an [[SDR_Text_Block]] or [[SDR_Vocabulary_Term]] describing the logical form (e.g., "Modus Ponens", "Inductive"). |
| `Supporting_Evidence_UIDs`| `List<Synapse_UID>`             | `0..*`       | List of UIDs pointing to [[SDR_Data_Reference]] or other SDRs that provide evidence for the premises.       |
| `Counter_Arguments_UIDs`  | `List<Synapse_UID>`             | `0..*`       | List of UIDs pointing to other [[SDR_Argument_Structure]] instances that represent counter-arguments.        |
| `Argument_Strength_UID`   | `Synapse_UID`                   | `0..1`       | UID of an [[SDR_Confidence_Score_Item]] or [[SDR_Qualitative_Assessment]] assessing the argument's strength. |
| `Argument_Context_UID`    | `Synapse_UID`                   | `0..1`       | UID of an [[SDR_Text_Block]] providing context for the argument.                                            |
| `Argument_Metadata`       | `[[SDR_Metadata_Block]]`        | `0..1`       | UID of an SDR_Metadata_Block. Metadata for this argument structure.                                           |