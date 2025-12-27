# MagenticUI

<div align="center">
  <img src="docs/img/magui-readme-logo.svg" alt="MagenticUI Logo" width="200">

  _Automate your web tasks while you stay in control_

  [![PyPI Version](https://img.shields.io/pypi/v/magentic_ui.svg)](https://pypi.python.org/pypi/magentic_ui)
  [![License](https://img.shields.io/pypi/l/magentic_ui.svg)](https://pypi.python.org/pypi/magentic_ui)
  ![Python Versions](https://img.shields.io/badge/python-3.10%20%7C%203.11%20%7C%203.12%20%7C%203.13-blue)
</div>

---

## 🚀 Overview

MagenticUI is a **research prototype** of a human-centered interface powered by a multi-agent system. It can browse the web, perform actions, generate and execute code, and analyze files. It is designed to keep you in the loop, ensuring you maintain full control over automated workflows.

![MagenticUI Demo](https://github.com/user-attachments/assets/7975fc26-1a18-4acb-8bf9-321171eeade7)

## ⚡ Quick Start

### 🔰 Prerequisites

Before installing, please read the prerequisites carefully. MagenticUI requires **Docker** to run. If you are on **Windows**, you will need **WSL2**. We recommend using [uv](https://docs.astral.sh/uv/getting-started/installation/) for a faster setup. If you are using **Mac** or **Linux**, you can skip the WSL2 step.

### 💻 Installation & Execution

bash
# 1. Create and activate a virtual environment
python3 -m venv .venv
source .venv/bin/activate

# 2. Install MagenticUI
pip install magentic-ui --upgrade

# 3. Set your API key (example for OpenAI)
export OPENAI_API_KEY=<YOUR_API_KEY>

# 4. Run the application
magentic-ui --port 8081


Once running, access the interface at **[http://localhost:8081](http://localhost:8081)**.

### 🐳 Docker-Free Mode

If you cannot set up Docker, you can run a limited version of MagenticUI that does not support code execution, file navigation, or browser display:

bash
magentic-ui --run-without-docker --port 8081


### 🖥️ Command Line Interface

For headless operation, use the CLI:

bash
magentic-cli --work-dir PATH/TO/STORE/DATA


### 🔌 Optional Providers

To use **Azure** models or **Ollama**, install the optional dependencies:

bash
# For Azure
pip install magentic-ui[azure]

# For Ollama
pip install magentic-ui[ollama]


---

## 🧩 Architecture

MagenticUI orchestrates a multi-agent system to solve complex tasks. Here is how it works:

<p align="center">
  <img src="./docs/img/magenticui_running.png" alt="Magentic-UI Architecture" height="400">
</p>

1.  **User Intent**: You provide a high-level task (e.g., "Find the best flight to Tokyo").
2.  **Orchestrator**: The central agent breaks down the task and delegates subtasks to specialized agents.
3.  **Specialized Agents**:
    *   **Web Agent**: Browses the web, clicks links, and fills out forms using a controlled browser.
    *   **Code Agent**: Writes and executes Python code to process data or generate visualizations.
    *   **File Agent**: Reads, writes, and manages files within the secure workspace.
4.  **Human-in-the-Loop**: At critical junctures, MagenticUI pauses and asks for your approval or input before proceeding. This ensures safety and accuracy.

### Use Cases

*   **Complex Web Navigation**: Filtering flight results or finding links on personal sites not indexed by search engines.
*   **Form Filling & Customization**: Automating repetitive data entry on web forms.
*   **Web Data + Code**: Fetching data from the web and immediately generating charts or reports.

---

## 🛠️ Troubleshooting

For common installation issues and their solutions, please refer to the [troubleshooting document](TROUBLESHOOTING.md).

If you encounter Docker issues, ensure:
1.  Docker Desktop is running.
2.  Your user has permission to run Docker commands.
3.  (Windows) WSL2 backend is enabled in Docker settings.

---

## 🤝 Contributing

We welcome contributions! Please check our [Contributing Guide](CONTRIBUTING.md) for details on how to get started.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
