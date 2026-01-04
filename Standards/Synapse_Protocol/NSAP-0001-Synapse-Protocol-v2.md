# Project Chimera: Protocol Specification
## Document: SYNAPSE_PROTOCOL_V2.md
**Version:** 1.0
**Date:** June 7, 2025
**Status:** DRAFT
**Extends:** Core Principles of Synapse

---

### 1.0 Overview

This document specifies Version 2.0 of the Synapse protocol. It is an extension of the original Core Principles and is designed to facilitate the event-driven "Domino Cascade" model. [cite_start]It introduces three new formal message types: `EVENT`, `TRIGGER`, and `STATE_CHANGE`, while maintaining the core principles of conciseness, referential purity, and structured logic.

---

### 2.0 Universal Message Header

All Synapse 2.0 messages MUST begin with a universal header to ensure proper routing, identification, and diagnostics.

**Attributes:**
* [[Message-ID]]: A unique UID generated for the specific message.
* [[Source-UID]]: The UID of the model broadcasting the message.
* [[Timestamp]]: The precise UTC timestamp of the broadcast.
* [[Message-Type]]: [[EVENT]], [[TRIGGER]], or [[STATE_CHANGE]].
* [[Protocol-Ver]]: [[2.0]]

---

### 3.0 Message Type Specifications

#### 3.1 [[EVENT]]

* **Purpose:** To announce a completed action and broadcast its results as a new data asset. This is the primary mechanism for continuing a cascade.
* **Formal Syntax:**
    ```synapse
    {
      "Header": {
        "Message-ID": "MSG:...",
        "Source-UID": "MODEL:TYPE:UID",
        "Timestamp": "...",
        "Message-Type": "EVENT",
        "Protocol-Ver": "2.0"
      },
      "Body": {
        "Event-Name": "...",
        "Payload": {
          "Data-Asset-UID": "ASSET:TYPE:UID",
          "Description": "...",
          "Confidence-Score": "0.0-1.0"
        }
      }
    }
    ```
* **Example:** The Archivist completes a data analysis.
    ```json
    {
      "Header": {
        "Message-ID": "MSG:0x4F5A",
        "Source-UID": "Archivist:0x00A1",
        "Timestamp": "2025-06-07T07:15:12Z",
        "Message-Type": "EVENT",
        "Protocol-Ver": "2.0"
      },
      "Body": {
        "Event-Name": "DATA_VALIDATED",
        "Payload": {
          "Data-Asset-UID": "KNOWLEDGE_GRAPH:Creature_XYZ_KG:0xK1L2",
          "Description": "Knowledge graph constructed from raw data.",
          "Confidence-Score": "0.98"
        }
      }
    }
    ```

#### 3.2 [[TRIGGER]]

* **Purpose:** To explicitly and directly command a specific model (or models) to perform an action, often conditionally based on a future event.
* **Formal Syntax:**
    ```synapse
    {
      "Header": { ... },
      "Body": {
        "Target-UID": "MODEL:TYPE:UID",
        "Condition": {
          "On-Event": "...",
          "Source-UID": "..."
        },
        "Action-To-Trigger": "...",
        "Parameters": { ... }
      }
    }
    ```
* **Example:** The Nexus-Mind initiates a full workflow.
    ```json
    {
      "Header": {
        "Message-ID": "MSG:0x4F5B",
        "Source-UID": "Nexus-Mind:0x0001",
        "Timestamp": "2025-06-07T07:15:10Z",
        "Message-Type": "TRIGGER",
        "Protocol-Ver": "2.0"
      },
      "Body": {
        "Target-UID": "Archivist:0x00A1",
        "Condition": {
          "On-Event": "IMMEDIATE"
        },
        "Action-To-Trigger": "ACQUIRE_DATA",
        "Parameters": { "source_url": "..." }
      }
    }
    ```

#### 3.3 [[STATE_CHANGE]]

* **Purpose:** To report on the operational status of a model or cascade. [cite_start]It serves as the primary tool for the Diagnostician to monitor family health  and for models to acknowledge tasks.
* **Formal Syntax:**
    ```synapse
    {
      "Header": { ... },
      "Body": {
        "Target-UID": "MODEL:TYPE:UID",
        "Status-Code": "...",
        "Reason": "..."
      }
    }
    ```
* **Example:** The Narrator acknowledges a task.
    ```json
    {
      "Header": {
        "Message-ID": "MSG:0x4F5C",
        "Source-UID": "Narrator:0x00B2",
        "Timestamp": "2025-06-07T07:15:13Z",
        "Message-Type": "STATE_CHANGE",
        "Protocol-Ver": "2.0"
      },
      "Body": {
        "Target-UID": "Archivist:0x00A1",
        "Status-Code": "TASK_ACCEPTED",
        "Reason": "Listener received EVENT DATA_VALIDATED."
      }
    }
    ```