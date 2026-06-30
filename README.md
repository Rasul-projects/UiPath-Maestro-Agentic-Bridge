# UiPath-Maestro-Agentic-Bridge

**An advanced orchestration solution built for UiPath AgentHack 2026.**

##  Project Description
In modern enterprise environments, AI agents offer immense flexibility but often lack runtime boundaries, error recovery, and human-in-the-loop governance. This project bridges the gap between high-level autonomous agent frameworks and deterministic enterprise execution. 

We utilize the **UiPath Platform** as a centralized orchestration and governance plane. The solution processes complex, exception-heavy business workflows by dynamically assigning tasks to AI agents and gracefully handing off edge cases to human operators when confidence thresholds drop. This ensures enterprise-grade reliability while maximizing AI autonomy.

##  UiPath Components Used
To orchestrate this workflow end-to-end, the following native capabilities are utilized:
*   **UiPath Automation Cloud:** The core execution layer.
*   **UiPath Maestro:** Orchestrates the flow, manages process state, and coordinates handoffs between systems, agents, and humans.
*   **UiPath Agent Builder:** Used to construct and govern the low-code agents executing structured sub-tasks.
*   **UiPath API Workflows:** Facilitates rapid data exchange between external LLM environments (GitHub Codespaces) and the UiPath control plane.

##  Agent Type Declaration
**This solution utilizes BOTH Coded Agents and Low-Code Agents.**
*   **Coded Agents:** Developed using Python and executed in GitHub Codespaces. We heavily utilized **UiPath for Coding Agents** (specifically leveraging Gemini CLI and Cursor) to rapidly prototype and test our orchestration scripts.
*   **Low-Code Agents:** Built natively via UiPath Agent Builder for deterministic data validation steps.

## ⚙️ Setup Instructions & Prerequisites

### Prerequisites
1.  Access to UiPath Automation Cloud / UiPath Labs.
2.  GitHub Codespaces enabled for this repository.
3.  Valid LLM API Keys (e.g., OpenAI, Anthropic, or Gemini).

### Run Instructions
1.  **Clone & Launch:** Open this repository directly in **GitHub Codespaces**.
2.  **Environment Setup:** Create a `.env` file in the root directory and add your keys:
    ```env
    UIPATH_ORCHESTRATOR_URL=[https://cloud.uipath.com/](https://cloud.uipath.com/)[YOUR_ORG]
    LLM_API_KEY=[YOUR_KEY]
    ```
3.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Import UiPath Assets:** Navigate to the `/uipath_workflow` folder in this repo, zip the contents, and import them as a new project into your UiPath Studio Web / Automation Cloud instance.
5.  **Execute:** Trigger the main sequence from UiPath Maestro. The process will reach out to the Codespace agent listener to execute the cognitive tasks.

## 📜 License
This project is licensed under the Apache-2.0 License - see the [LICENSE](LICENSE) file for details.
