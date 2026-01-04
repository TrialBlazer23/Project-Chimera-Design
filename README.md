# The Aletheia Framework

### (Formerly Project Chimera)

**A Neuro-Symbolic Standard for Auditable, Self-Healing Agent Ecosystems.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status: Experimental](https://img.shields.io/badge/Status-Experimental-red.svg)]()
[![Architecture: Neuro-Symbolic](https://img.shields.io/badge/Architecture-Neuro--Symbolic-blueviolet.svg)]()

> **The Philosophy:** Current AI models are Black Boxes. Aletheia is a **Glass Box**. It separates *Generation* (The Narrator) from *Judgment* (The Philosopher) to create agents that are safe, auditable, and capable of recursive self-improvement.
> *Read the origin story and architectural thesis in [VISION.md](VISION.md).*

---

## 🏗️ The Architecture

Aletheia is not a single model. It is a **Multi-Agent System (MAS)** composed of specialized "Organs" that communicate via the **Domino Cascade** (Event Bus).

### 1. The Family (Agent Roles)

| Agent | Role | Function |
| --- | --- | --- |
| **Nexus-Mind** | Orchestrator | Strategic planning, task decomposition, and resource allocation. The "System 2" thinker. |
| **Philosopher** | Ethical Kernel | A Neuro-Symbolic auditor that validates outputs against "Prime Directives" *before* execution. |
| **Archivist** | Memory Core | Manages the Knowledge Graph using deterministic dependency parsing (Spacy) to prevent hallucinations. |
| **Diagnostician** | Self-Healing | Monitors the event bus for infinite loops or failures. Triggers the **Resonance Cycle** to patch policy errors. |
| **Narrator** | Interface | Synthesizes complex data into human-readable narrative. |

### 2. Core Mechanics

#### The Domino Cascade (Event-Driven Flow)

Unlike linear chains, Aletheia agents operate asynchronously.

> *Example:* `USER_INPUT` -> **Archivist** (retrieves context) -> `CONTEXT_READY` -> **Narrator** (drafts response) -> `DRAFT_READY` -> **Philosopher** (audits draft) -> `APPROVED` -> **User**.

#### The Resonance Cycle (Recursive Improvement)

The system does not just log errors; it learns from them.

1. **Experience:** The system logs a failure (e.g., a loop or a rejected draft).
2. **Reflection:** The Nexus-Mind analyzes the *Cascade Log*.
3. **Mutation:** The system proposes an update to its `Operational_Policy.json`.
4. **Verification:** The Philosopher validates the new policy.
5. **Integration:** The agent's behavior is permanently updated.

---

## 🚀 Getting Started

### Prerequisites

* Python 3.10+
* Spacy (`en_core_web_sm`)
* Ollama (for local inference) or OpenAI API Key

### Installation

```bash
git clone https://github.com/TrialBlazer23/Aletheia-Framework.git
cd Aletheia-Framework
pip install -r requirements.txt
python -m spacy download en_core_web_sm
```

### Running the Prototype

To launch the `Nexus-Mind` console:
```bash
python main.py
```

---

## 📂 Repository Structure

* `/core`: The Python implementation of the agents (Archivist, Philosopher, etc.).
* `/standards`: JSON Schemas for **SDR** (Structured Data Representation).
* `/policies`: The default "Prime Directives" and Operational Policies.
* `/docs`: Detailed architectural diagrams and RFCs.

---

## 🤝 Contributing

We are looking for architects, ethicists, and engineers to help build the **Glass Box** future.

* **Engineers:** Help us refine the *Domino Cascade* event bus.
* **Philosophers:** Help us expand the ethical rule sets for the *Philosopher* agent.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
