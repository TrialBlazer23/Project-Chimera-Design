## SDR_Signal_Instance

**SDR Type Name:** [[SDR_Signal_Instance]]

**Description:** Represents a discrete signal event within the Chimera system—a meaningful unit of information flow between components, sensors, or agents. Signals are the atomic building blocks of the Domino Cascade architecture, representing state changes, triggers, observations, or notifications that propagate through the agent family.

**Anti-Hallucination Design Rationale:**

> Unstructured AI communication allows models to emit vague, unverifiable claims ("something seems wrong," "the system detected an issue"). SDR_Signal_Instance forces precision by requiring:
>
> 1. **Typed signals from controlled vocabulary** - The `Signal_Type_UID` must reference a pre-defined signal type, preventing invented or ambiguous signals.
> 2. **Quantified values with units** - Numeric signals must specify measurement units and ranges, preventing unit confusion or meaningless numbers.
> 3. **Explicit source attribution** - Every signal must declare its origin, enabling verification that the source is authorized to emit that signal type.
> 4. **Temporal precision** - Timestamps are mandatory, preventing temporal hallucinations ("earlier" vs. specific times).
> 5. **Causal chain links** - Signals can reference their triggering events, enabling reconstruction of causality.
> 6. **Validity bounds** - Signals can declare their expiration, preventing stale data from influencing decisions.

**Fields:**

| Field Name                    | Data Type                         | Multiplicity | Description                                                                                                                                                    |
| :---------------------------- | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Signal_Instance_UID`         | `Synapse_UID`                     | `1`          | Unique identifier for this specific signal instance.                                                                                                           |
| `Signal_Type_UID`             | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` from a controlled signal type vocabulary (e.g., `HEALTH_CHECK`, `THRESHOLD_BREACH`, `TASK_COMPLETE`, `ANOMALY_DETECTED`). |
| `Signal_Category_UID`         | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` classifying the signal category: `OBSERVATION`, `EVENT`, `COMMAND`, `STATE_CHANGE`, `HEARTBEAT`, `ALERT`.                 |
| `Timestamp_Emitted`           | `Synapse_Timestamp`               | `1`          | The exact date and time when this signal was emitted.                                                                                                          |
| `Timestamp_Observed`          | `Synapse_Timestamp`               | `0..1`       | The time the underlying phenomenon was observed (may differ from emission time due to processing delays).                                                      |
| `Emitting_Component_UID`      | `Synapse_UID`                     | `1`          | UID of the AI family member, sensor, module, or external system that emitted this signal.                                                                      |
| `Target_Components_UIDs`      | `List<Synapse_UID>`               | `0..*`       | List of UIDs for intended recipient components. Empty list implies broadcast to all listeners.                                                                 |
| `Signal_Payload`              | `[[SDR_Signal_Payload]]`          | `1`          | UID of an `[[SDR_Signal_Payload]]` containing the signal's data content (see below for structure).                                                             |
| `Signal_Strength_UID`         | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Confidence_Score_Item]]` indicating signal reliability or intensity (0.0-1.0).                                                                |
| `Priority_Level_UID`          | `Synapse_UID`                     | `1`          | UID of an `[[SDR_Vocabulary_Term]]` from priority vocabulary: `CRITICAL`, `HIGH`, `NORMAL`, `LOW`, `BACKGROUND`.                                               |
| `Triggering_Event_UID`        | `Synapse_UID`                     | `0..1`       | UID of the event, signal, or cascade that caused this signal to be emitted. **Enables causal tracing.**                                                        |
| `Correlation_ID`              | `Synapse_UID`                     | `0..1`       | UID for correlating related signals across a cascade or workflow.                                                                                              |
| `Validity_Window_Start`       | `Synapse_Timestamp`               | `0..1`       | Timestamp after which this signal becomes valid (for scheduled signals).                                                                                       |
| `Validity_Window_End`         | `Synapse_Timestamp`               | `0..1`       | Timestamp after which this signal expires and should be ignored. **Prevents stale data influence.**                                                            |
| `Acknowledgment_Required`     | `Synapse_Boolean`                 | `1`          | Whether recipient(s) must acknowledge receipt of this signal.                                                                                                  |
| `Acknowledgment_Status_UID`   | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]`: `PENDING`, `ACKNOWLEDGED`, `REJECTED`, `TIMEOUT`.                                                                         |
| `Signal_Metadata`             | `[[SDR_Metadata_Block]]`          | `1`          | UID of an `[[SDR_Metadata_Block]]` containing provenance information.                                                                                          |

---

## SDR_Signal_Payload (Embedded Type)

**Description:** The structured content of a signal, enforcing type-safe data representation.

| Field Name                | Data Type                         | Multiplicity | Description                                                                                                    |
| :------------------------ | :-------------------------------- | :----------- | :------------------------------------------------------------------------------------------------------------- |
| `Payload_UID`             | `Synapse_UID`                     | `1`          | Unique identifier for this payload instance.                                                                   |
| `Payload_Schema_UID`      | `Synapse_UID`                     | `1`          | UID referencing the schema this payload conforms to. **Enables validation.**                                   |
| `Numeric_Value`           | `Synapse_Float`                   | `0..1`       | Numeric data if the signal carries a measurement.                                                              |
| `Numeric_Unit_UID`        | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Vocabulary_Term]]` specifying the unit of measurement. **Required if Numeric_Value present.** |
| `Numeric_Range_UID`       | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Numeric_Range]]` specifying valid/expected range for the value.                               |
| `Boolean_Value`           | `Synapse_Boolean`                 | `0..1`       | Boolean data if the signal is a binary state.                                                                  |
| `Text_Value_UID`          | `Synapse_UID`                     | `0..1`       | UID of an `[[SDR_Text_Block]]` for textual signal content.                                                     |
| `Structured_Data_UID`     | `Synapse_UID`                     | `0..1`       | UID of any other SDR type for complex structured payloads.                                                     |
| `Reference_UIDs`          | `List<Synapse_UID>`               | `0..*`       | List of UIDs this signal references (entities, prior signals, etc.).                                           |

---

## JSON Schema Definition

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://project-chimera.org/schemas/sdr/signal-instance.json",
  "title": "SDR_Signal_Instance",
  "description": "Represents a discrete signal event within the Chimera system—a meaningful unit of information flow between components. Signals are the atomic building blocks of cascade architectures.",
  
  "$comment": "ANTI-HALLUCINATION DESIGN: This schema prevents AI confabulation by (1) requiring signals to have types from a controlled vocabulary—no invented signal types, (2) mandating explicit source attribution for verification, (3) requiring units for numeric values—no ambiguous numbers, (4) enforcing temporal precision with mandatory timestamps, (5) enabling causal chain reconstruction via triggering event links, and (6) preventing stale data influence via validity windows.",

  "type": "object",
  "required": [
    "Signal_Instance_UID",
    "Signal_Type_UID",
    "Signal_Category_UID",
    "Timestamp_Emitted",
    "Emitting_Component_UID",
    "Signal_Payload",
    "Priority_Level_UID",
    "Acknowledgment_Required",
    "Signal_Metadata"
  ],
  
  "properties": {
    "Signal_Instance_UID": {
      "type": "string",
      "format": "uuid",
      "description": "Unique identifier for this specific signal instance.",
      "$comment": "TRACEABILITY: Every signal is uniquely addressable for audit trails and debugging."
    },
    
    "Signal_Type_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID of an SDR_Vocabulary_Term from a controlled signal type vocabulary.",
      "$comment": "ANTI-HALLUCINATION: The signal type must be from a pre-defined vocabulary. Examples: HEALTH_CHECK, THRESHOLD_BREACH, TASK_COMPLETE, ANOMALY_DETECTED, CASCADE_INITIATED, STATE_SYNC, RESOURCE_EXHAUSTED. The AI cannot invent new signal types without formal vocabulary extension.",
      "examples": [
        "vocab-signal-type-health-check",
        "vocab-signal-type-threshold-breach",
        "vocab-signal-type-task-complete"
      ]
    },
    
    "Signal_Category_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID classifying the signal category.",
      "$comment": "ANTI-HALLUCINATION: Strict categorization from controlled vocabulary: OBSERVATION (passive sensing), EVENT (something happened), COMMAND (instruction to act), STATE_CHANGE (transition occurred), HEARTBEAT (liveness check), ALERT (requires attention).",
      "enum_reference": ["OBSERVATION", "EVENT", "COMMAND", "STATE_CHANGE", "HEARTBEAT", "ALERT"]
    },
    
    "Timestamp_Emitted": {
      "type": "string",
      "format": "date-time",
      "description": "ISO 8601 timestamp when this signal was emitted.",
      "$comment": "TEMPORAL GROUNDING: Mandatory precise timestamp prevents vague temporal claims like 'recently' or 'a while ago'. Essential for cascade ordering and replay."
    },
    
    "Timestamp_Observed": {
      "type": "string",
      "format": "date-time",
      "description": "The time the underlying phenomenon was observed (may differ from emission due to processing delays).",
      "$comment": "LATENCY AWARENESS: Distinguishes between when something happened and when it was reported, critical for time-sensitive systems."
    },
    
    "Emitting_Component_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID of the component that emitted this signal.",
      "$comment": "ANTI-HALLUCINATION: Source attribution is mandatory. Enables verification that the emitting component is authorized to produce this signal type. A temperature reading from The Narrator would be suspicious; from a sensor, expected."
    },
    
    "Target_Components_UIDs": {
      "type": "array",
      "items": { "type": "string", "format": "uuid" },
      "description": "List of UIDs for intended recipient components. Empty = broadcast.",
      "$comment": "ROUTING: Explicit addressing prevents signals from being processed by inappropriate components."
    },
    
    "Signal_Payload": {
      "$ref": "#/$defs/SDR_Signal_Payload",
      "description": "The structured content of the signal.",
      "$comment": "TYPE-SAFE DATA: All signal content must conform to the payload schema, preventing unstructured or ambiguous data."
    },
    
    "Signal_Strength_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID of an SDR_Confidence_Score_Item indicating signal reliability (0.0-1.0).",
      "$comment": "UNCERTAINTY QUANTIFICATION: Weak signals can be handled differently than strong signals. A 0.3 strength anomaly detection warrants investigation; a 0.95 strength warrants immediate action."
    },
    
    "Priority_Level_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID from priority vocabulary.",
      "$comment": "ANTI-HALLUCINATION: Priority must be from controlled vocabulary: CRITICAL (immediate action), HIGH (soon), NORMAL (standard processing), LOW (when convenient), BACKGROUND (idle processing only).",
      "enum_reference": ["CRITICAL", "HIGH", "NORMAL", "LOW", "BACKGROUND"]
    },
    
    "Triggering_Event_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID of the event or signal that caused this signal to be emitted.",
      "$comment": "CAUSAL TRACING: Links signals into causal chains. If Signal B was triggered by Signal A, this is recorded. Enables root cause analysis and cascade visualization. 'Why did the system shut down?' can be answered by following the trigger chain."
    },
    
    "Correlation_ID": {
      "type": "string",
      "format": "uuid",
      "description": "UID for correlating related signals across a cascade.",
      "$comment": "WORKFLOW TRACKING: All signals in the same cascade share a correlation ID, enabling grouped analysis."
    },
    
    "Validity_Window_Start": {
      "type": "string",
      "format": "date-time",
      "description": "Timestamp after which this signal becomes valid."
    },
    
    "Validity_Window_End": {
      "type": "string",
      "format": "date-time",
      "description": "Timestamp after which this signal expires and should be ignored.",
      "$comment": "ANTI-HALLUCINATION: Prevents stale signals from influencing current decisions. A temperature reading from an hour ago should not trigger current cooling actions. Systems MUST check validity before acting on signals."
    },
    
    "Acknowledgment_Required": {
      "type": "boolean",
      "description": "Whether recipient(s) must acknowledge receipt of this signal.",
      "$comment": "RELIABILITY: Critical signals require acknowledgment to ensure they were processed."
    },
    
    "Acknowledgment_Status_UID": {
      "type": "string",
      "format": "uuid",
      "description": "UID from acknowledgment vocabulary: PENDING, ACKNOWLEDGED, REJECTED, TIMEOUT."
    },
    
    "Signal_Metadata": {
      "type": "string",
      "format": "uuid",
      "description": "UID of an SDR_Metadata_Block containing provenance information.",
      "$comment": "PROVENANCE: Full audit trail including version, confidence, and processing history."
    }
  },
  
  "$defs": {
    "SDR_Signal_Payload": {
      "type": "object",
      "description": "Structured content of a signal, enforcing type-safe data representation.",
      "$comment": "ANTI-HALLUCINATION: The payload schema prevents ambiguous data. Numeric values MUST have units. Text values MUST be structured SDR_Text_Blocks. Complex data MUST reference defined SDR types.",
      "required": ["Payload_UID", "Payload_Schema_UID"],
      "properties": {
        "Payload_UID": {
          "type": "string",
          "format": "uuid",
          "description": "Unique identifier for this payload instance."
        },
        "Payload_Schema_UID": {
          "type": "string",
          "format": "uuid",
          "description": "UID referencing the schema this payload conforms to.",
          "$comment": "VALIDATION: Payloads can be validated against their declared schema, catching malformed data."
        },
        "Numeric_Value": {
          "type": "number",
          "description": "Numeric data if the signal carries a measurement."
        },
        "Numeric_Unit_UID": {
          "type": "string",
          "format": "uuid",
          "description": "UID specifying the unit of measurement.",
          "$comment": "ANTI-HALLUCINATION: A number without a unit is meaningless. Is 98.6 a temperature in Fahrenheit? Celsius? A percentage? A count? This field eliminates ambiguity. If Numeric_Value is present, this SHOULD be present."
        },
        "Numeric_Range_UID": {
          "type": "string",
          "format": "uuid",
          "description": "UID of an SDR_Numeric_Range specifying valid range for the value.",
          "$comment": "SANITY CHECK: If a temperature sensor reports 5000°C, the range constraint flags it as anomalous."
        },
        "Boolean_Value": {
          "type": "boolean",
          "description": "Boolean data if the signal is a binary state."
        },
        "Text_Value_UID": {
          "type": "string",
          "format": "uuid",
          "description": "UID of an SDR_Text_Block for textual signal content.",
          "$comment": "STRUCTURED TEXT: Even text must be a structured SDR_Text_Block with language, encoding, and provenance—not raw strings."
        },
        "Structured_Data_UID": {
          "type": "string",
          "format": "uuid",
          "description": "UID of any other SDR type for complex structured payloads."
        },
        "Reference_UIDs": {
          "type": "array",
          "items": { "type": "string", "format": "uuid" },
          "description": "List of UIDs this signal references."
        }
      },
      "additionalProperties": false
    }
  },
  
  "additionalProperties": false
}
```

---

## Usage Examples

### Example 1: Threshold Breach Signal

When The Diagnostician detects memory usage exceeding safe thresholds:

```json
{
  "Signal_Instance_UID": "sig-a1b2c3d4-memory-breach-001",
  "Signal_Type_UID": "vocab-signal-threshold-breach",
  "Signal_Category_UID": "vocab-category-alert",
  "Timestamp_Emitted": "2025-06-15T09:45:33.127Z",
  "Timestamp_Observed": "2025-06-15T09:45:33.001Z",
  "Emitting_Component_UID": "model-diagnostician-001",
  "Target_Components_UIDs": ["model-nexus-mind-001"],
  "Signal_Payload": {
    "Payload_UID": "payload-mem-001",
    "Payload_Schema_UID": "schema-resource-measurement",
    "Numeric_Value": 94.7,
    "Numeric_Unit_UID": "vocab-unit-percent",
    "Numeric_Range_UID": "range-memory-safe-0-85"
  },
  "Signal_Strength_UID": "conf-0.98-high",
  "Priority_Level_UID": "vocab-priority-high",
  "Triggering_Event_UID": "event-cascade-batch-processing-47",
  "Correlation_ID": "cascade-batch-47-correlation",
  "Validity_Window_End": "2025-06-15T09:46:33.127Z",
  "Acknowledgment_Required": true,
  "Acknowledgment_Status_UID": "vocab-ack-pending",
  "Signal_Metadata": "meta-sig-a1b2c3d4"
}
```

**What this structure prevents:**
- ❌ "Memory seems high" → ✅ "Memory is 94.7% (exceeds 85% threshold)"
- ❌ "Something might be wrong" → ✅ "Threshold breach detected by Diagnostician"
- ❌ "This happened recently" → ✅ "Observed at 09:45:33.001Z, emitted 126ms later"
- ❌ Stale data influence → ✅ "Signal expires in 60 seconds"

### Example 2: Cascade Completion Signal

```json
{
  "Signal_Instance_UID": "sig-cascade-complete-789",
  "Signal_Type_UID": "vocab-signal-task-complete",
  "Signal_Category_UID": "vocab-category-event",
  "Timestamp_Emitted": "2025-06-15T14:22:01.445Z",
  "Emitting_Component_UID": "model-narrator-001",
  "Signal_Payload": {
    "Payload_UID": "payload-cascade-result",
    "Payload_Schema_UID": "schema-cascade-outcome",
    "Boolean_Value": true,
    "Structured_Data_UID": "cascade-log-789-summary"
  },
  "Priority_Level_UID": "vocab-priority-normal",
  "Triggering_Event_UID": "cascade-789-final-step",
  "Correlation_ID": "cascade-789-correlation",
  "Acknowledgment_Required": false,
  "Signal_Metadata": "meta-cascade-complete-789"
}
```

---

## How SDR_Signal_Instance Prevents Hallucinations

| Hallucination Risk | SDR Mitigation |
|--------------------|----------------|
| **Invented signal types** | `Signal_Type_UID` must reference controlled vocabulary |
| **Vague measurements** | `Numeric_Value` requires `Numeric_Unit_UID`; ranges enable validation |
| **Unattributed claims** | `Emitting_Component_UID` is mandatory—no anonymous signals |
| **Temporal ambiguity** | Mandatory `Timestamp_Emitted`, optional `Timestamp_Observed` for latency |
| **Broken causality** | `Triggering_Event_UID` links signals into verifiable chains |
| **Stale data influence** | `Validity_Window_End` forces expiration checks |
| **Unstructured payloads** | `Signal_Payload` enforces schema conformance |
| **Priority inflation** | `Priority_Level_UID` from finite controlled vocabulary |

The signal format transforms opaque AI communication into transparent, verifiable, auditable data flow.
