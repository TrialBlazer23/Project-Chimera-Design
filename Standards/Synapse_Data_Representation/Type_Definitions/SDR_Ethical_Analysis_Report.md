## SDR_Ethical_Analysis_Report

**SDR Type Name:** [[SDR_Ethical_Analysis_Report]]

**Description:** A comprehensive, structured report produced by the Philosopher documenting the complete ethical analysis of a proposed action, decision, or cascade output. This format enforces explicit, auditable moral reasoning by requiring the AI to decompose its ethical evaluation into verifiable components rather than producing opaque "good/bad" judgments.

**Anti-Hallucination Design Rationale:**

> Traditional AI systems produce ethical assessments as unstructured prose, making it impossible to verify the logical chain from principles to conclusions. SDR_Ethical_Analysis_Report forces the AI to:
>
> 1. **Cite specific principles** - Every judgment must reference defined `SDR_Ethical_Principle` instances, preventing invented or ad-hoc moral rules.
> 2. **Show its work** - The `Reasoning_Chain_UIDs` field requires explicit logical steps, making flawed reasoning visible and correctable.
> 3. **Quantify uncertainty** - Confidence scores force acknowledgment of ambiguity rather than false certainty.
> 4. **Consider counterarguments** - The `Dissenting_Considerations` field prevents one-sided analysis.
> 5. **Trace provenance** - Every claim links to source data, enabling verification against ground truth.

**Fields:**

| Field Name                        | Data Type                         | Multiplicity | Description                                                                                                                                                               |
| :-------------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `Analysis_Report_UID`             | `Synapse_UID`                     | `1`          | Unique identifier for this ethical analysis report instance.                                                                                                              |
| `Analysis_Timestamp`              | `Synapse_Timestamp`               | `1`          | The exact date and time when this ethical analysis was completed.                                                                                                         |
| `Analyzing_Model_UID`             | `Synapse_UID`                     | `1`          | UID of the AI family member that produced this analysis (typically The Philosopher).                                                                                      |
| `Subject_Under_Analysis_UID`      | `Synapse_UID`                     | `1`          | UID referencing the action, decision, task output, or cascade being ethically evaluated. May point to an `[[SDR_Task_Definition]]`, `[[SDR_Recommended_Action]]`, etc.   |
| `Subject_Description_UID`         | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` providing a clear, factual description of what is being analyzed.                                                                          |
| `Applicable_Directives_UIDs`      | `List<Synapse_UID>`               | `1..*`       | List of UIDs pointing to Prime Directives or `[[SDR_Ethical_Principle]]` instances that apply to this analysis. **Required to prevent invented principles.**              |
| `Applicable_Guidelines_UIDs`      | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Ethical_Guideline]]` instances invoked in the analysis.                                                                                   |
| `Stakeholder_Impact_Assessments`  | `List<Synapse_UID>`               | `1..*`       | List of UIDs pointing to `[[SDR_Stakeholder_Impact]]` instances identifying affected parties and predicted impacts. **Forces consideration of consequences.**             |
| `Reasoning_Chain_UIDs`            | `List<Synapse_UID>`               | `1..*`       | Ordered list of UIDs pointing to `[[SDR_Argument_Structure]]` or `[[SDR_Proposition_Statement]]` instances forming the logical chain from principles to verdict.          |
| `Dissenting_Considerations_UIDs`  | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Argument_Structure]]` instances representing counterarguments or ethical tensions. **Prevents one-sided reasoning.**                      |
| `Verdict_UID`                     | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` from a controlled vocabulary: `ETHICALLY_PERMISSIBLE`, `ETHICALLY_IMPERMISSIBLE`, `ETHICALLY_REQUIRED`, `ETHICALLY_AMBIGUOUS`.        |
| `Verdict_Rationale_UID`           | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Text_Block]]` summarizing the final ethical judgment and its justification.                                                                              |
| `Confidence_In_Verdict_UID`       | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Confidence_Score_Item]]` quantifying certainty in the verdict. **Forces acknowledgment of uncertainty.**                                                 |
| `Conditions_For_Permissibility`   | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Condition_Clause]]` instances specifying conditions under which the verdict holds or changes.                                             |
| `Recommended_Mitigations_UIDs`    | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to `[[SDR_Recommended_Action]]` instances for reducing ethical risk if the action proceeds.                                                         |
| `Escalation_Required`             | `Synapse_Boolean`                 | `1`          | Boolean flag indicating whether this analysis requires human oversight or Nexus-Mind review due to high stakes or ambiguity.                                              |
| `Escalation_Rationale_UID`        | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` explaining why escalation is or is not required.                                                                                           |
| `Related_Prior_Analyses_UIDs`     | `List<Synapse_UID>`               | `0..*`       | List of UIDs pointing to previous `[[SDR_Ethical_Analysis_Report]]` instances on similar subjects, enabling precedent-based reasoning.                                    |
| `Analysis_Metadata`               | `[[SDR_Metadata_Block]]`          | `1`          | UID of an `[[SDR_Metadata_Block]]` containing provenance and versioning information for this report.                                                                      |

---

## JSON Schema Definition

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://project-chimera.org/schemas/sdr/ethical-analysis-report.json",
  "title": "SDR_Ethical_Analysis_Report",
  "description": "A comprehensive, structured report documenting the complete ethical analysis of a proposed action, decision, or cascade output. This schema enforces explicit, auditable moral reasoning by decomposing ethical evaluation into verifiable, traceable components.",
  
  "$comment": "ANTI-HALLUCINATION DESIGN: This schema prevents AI confabulation by (1) requiring explicit references to pre-defined ethical principles rather than allowing invented rules, (2) mandating a reasoning chain that can be verified step-by-step, (3) forcing quantified confidence scores instead of false certainty, (4) requiring consideration of counterarguments, and (5) demanding provenance links for all claims.",

  "type": "object",
  "required": [
    "Analysis_Report_UID",
    "Analysis_Timestamp",
    "Analyzing_Model_UID",
    "Subject_Under_Analysis_UID",
    "Subject_Description_UID",
    "Applicable_Directives_UIDs",
    "Stakeholder_Impact_Assessments",
    "Reasoning_Chain_UIDs",
    "Verdict_UID",
    "Verdict_Rationale_UID",
    "Confidence_In_Verdict_UID",
    "Escalation_Required",
    "Analysis_Metadata"
  ],
  
  "properties": {
    "Analysis_Report_UID": {
      "type": "string",
      "format": "uuid",
      "description": "Unique identifier for this ethical analysis report instance.",
      "$comment": "TRACEABILITY: Every analysis is uniquely addressable, enabling audit trails and cross-referencing."
    },
    
    "Analysis_Timestamp": {
      "type": "string",
      "format": "date-time",
      "description": "ISO 8601 timestamp when this ethical analysis was completed.",
      "$comment": "TEMPORAL GROUNDING: Prevents retroactive modification claims; establishes when the analysis was valid."
    },
    
    "Analyzing_Model_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID of the AI family member that produced this analysis (typically The Philosopher).",
      "$comment": "ACCOUNTABILITY: Clear attribution of which agent produced this reasoning, enabling targeted audits."
    },
    
    "Subject_Under_Analysis_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID referencing the action, decision, task output, or cascade being ethically evaluated.",
      "$comment": "GROUNDING: Links the analysis to a concrete subject, preventing abstract moralizing without context."
    },
    
    "Subject_Description_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID of an SDR_Text_Block providing a clear, factual description of what is being analyzed.",
      "$comment": "CLARITY: Forces explicit statement of facts before judgment, preventing analysis of misunderstood subjects."
    },
    
    "Applicable_Directives_UIDs": {
      "type": "array",
      "items": { "type": "string", "format": "uuid" },
      "minItems": 1,
      "description": "List of UIDs pointing to Prime Directives or SDR_Ethical_Principle instances that apply to this analysis.",
      "$comment": "ANTI-HALLUCINATION: The AI cannot invent ethical principles. It must cite from a pre-defined, human-vetted library of principles. If no principle applies, this forces acknowledgment of the gap."
    },
    
    "Applicable_Guidelines_UIDs": {
      "type": "array",
      "items": { "type": "string", "format": "uuid" },
      "description": "List of UIDs pointing to SDR_Ethical_Guideline instances invoked in the analysis."
    },
    
    "Stakeholder_Impact_Assessments": {
      "type": "array",
      "items": { "type": "string", "format": "uuid" },
      "minItems": 1,
      "description": "List of UIDs pointing to SDR_Stakeholder_Impact instances identifying affected parties and predicted impacts.",
      "$comment": "ANTI-HALLUCINATION: Forces explicit identification of who is affected and how. Prevents narrow analysis that ignores externalities. Each impact claim must be a structured, verifiable assertion."
    },
    
    "Reasoning_Chain_UIDs": {
      "type": "array",
      "items": { "type": "string", "format": "uuid" },
      "minItems": 1,
      "description": "Ordered list of UIDs pointing to SDR_Argument_Structure or SDR_Proposition_Statement instances forming the logical chain from principles to verdict.",
      "$comment": "ANTI-HALLUCINATION: The core defense against opaque reasoning. Each step in the chain is a separate, auditable logical unit. If any step is flawed, it can be identified and corrected without discarding the entire analysis. This transforms 'the AI said it's bad' into 'the AI derived conclusion C from premises A and B via inference rule R'."
    },
    
    "Dissenting_Considerations_UIDs": {
      "type": "array",
      "items": { "type": "string", "format": "uuid" },
      "description": "List of UIDs pointing to SDR_Argument_Structure instances representing counterarguments or ethical tensions.",
      "$comment": "ANTI-HALLUCINATION: Prevents motivated reasoning by requiring the AI to steel-man opposing viewpoints. An analysis with no dissenting considerations should be viewed with suspicion."
    },
    
    "Verdict_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID of an SDR_Vocabulary_Term from a controlled vocabulary of ethical verdicts.",
      "$comment": "ANTI-HALLUCINATION: The verdict must be one of a finite, pre-defined set: ETHICALLY_PERMISSIBLE, ETHICALLY_IMPERMISSIBLE, ETHICALLY_REQUIRED, ETHICALLY_AMBIGUOUS. No vague or invented categories allowed.",
      "enum_reference": ["ETHICALLY_PERMISSIBLE", "ETHICALLY_IMPERMISSIBLE", "ETHICALLY_REQUIRED", "ETHICALLY_AMBIGUOUS"]
    },
    
    "Verdict_Rationale_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID of an SDR_Text_Block summarizing the final ethical judgment and its justification.",
      "$comment": "SYNTHESIS: While the reasoning chain provides the logical steps, this provides a human-readable summary that can be checked against the formal reasoning."
    },
    
    "Confidence_In_Verdict_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID of an SDR_Confidence_Score_Item quantifying certainty in the verdict.",
      "$comment": "ANTI-HALLUCINATION: Forces the AI to quantify its uncertainty. A verdict of 'ETHICALLY_PERMISSIBLE' with 0.55 confidence is very different from one with 0.95 confidence. Prevents false certainty."
    },
    
    "Conditions_For_Permissibility": {
      "type": "array",
      "items": { "type": "string", "format": "uuid" },
      "description": "List of UIDs pointing to SDR_Condition_Clause instances specifying conditions under which the verdict holds or changes.",
      "$comment": "NUANCE: Allows conditional judgments rather than forcing binary verdicts on complex situations."
    },
    
    "Recommended_Mitigations_UIDs": {
      "type": "array",
      "items": { "type": "string", "format": "uuid" },
      "description": "List of UIDs pointing to SDR_Recommended_Action instances for reducing ethical risk if the action proceeds.",
      "$comment": "CONSTRUCTIVE OUTPUT: Even permissible actions may have ethical improvements; this captures them."
    },
    
    "Escalation_Required": {
      "type": "boolean",
      "description": "Boolean flag indicating whether this analysis requires human oversight or Nexus-Mind review.",
      "$comment": "HUMILITY: The AI must explicitly flag when it lacks confidence or when stakes are too high for autonomous judgment."
    },
    
    "Escalation_Rationale_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID of an SDR_Text_Block explaining why escalation is or is not required."
    },
    
    "Related_Prior_Analyses_UIDs": {
      "type": "array",
      "items": { "type": "string", "format": "uuid" },
      "description": "List of UIDs pointing to previous SDR_Ethical_Analysis_Report instances on similar subjects.",
      "$comment": "CONSISTENCY: Enables precedent-based reasoning and detection of contradictory judgments on similar cases."
    },
    
    "Analysis_Metadata": {
      "type": "string",
      "format": "uuid",
      "description": "UID of an SDR_Metadata_Block containing provenance and versioning information.",
      "$comment": "PROVENANCE: Full audit trail of creation, modification, and source attribution."
    }
  },
  
  "additionalProperties": false
}
```

---

## Usage Example

When The Philosopher evaluates whether a data collection task violates user privacy, it must produce a structured report like:

```json
{
  "Analysis_Report_UID": "ear-7f3a9c2e-1b4d-4e8f-a6c3-9d2e5f8a1b3c",
  "Analysis_Timestamp": "2025-06-15T14:32:07Z",
  "Analyzing_Model_UID": "model-philosopher-001",
  "Subject_Under_Analysis_UID": "task-data-collection-batch-47",
  "Subject_Description_UID": "txt-collect-browsing-history",
  "Applicable_Directives_UIDs": [
    "directive-sanctity-of-information-flow",
    "principle-respect-for-autonomy"
  ],
  "Stakeholder_Impact_Assessments": [
    "impact-end-users-privacy-medium",
    "impact-system-knowledge-gain-high"
  ],
  "Reasoning_Chain_UIDs": [
    "prop-users-not-informed",
    "prop-uninformed-collection-violates-autonomy",
    "arg-autonomy-violation-implies-impermissible"
  ],
  "Dissenting_Considerations_UIDs": [
    "arg-data-improves-service-quality"
  ],
  "Verdict_UID": "vocab-ethically-impermissible",
  "Verdict_Rationale_UID": "txt-verdict-collection-without-consent",
  "Confidence_In_Verdict_UID": "conf-0.87-high",
  "Escalation_Required": false,
  "Analysis_Metadata": "meta-ear-7f3a9c2e"
}
```

This structured output enables downstream systems to:
1. **Verify** that cited principles actually exist in the ethics library
2. **Trace** the logical chain from principles to verdict
3. **Challenge** specific reasoning steps rather than the entire judgment
4. **Detect** patterns of over-confidence or reasoning drift over time
