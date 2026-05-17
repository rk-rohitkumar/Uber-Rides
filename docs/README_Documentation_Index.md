# 🚀 Project Documentation Index (The Single Source of Truth)

Welcome to the [Project Name] repository documentation hub. This index guides all contributors and new developers through the architecture, business rules, and development standards used in this PBIP project.

## 📚 Quick Start Guide (For New Developers)
1. **Read the Project Architecture:** Understand how pieces fit together before diving into code or formulas. -> [docs/project_architecture.md](#)
2. **Review Business Rules:** Understand *why* we calculate what we calculate. This is the law of the project. -> [docs/business-rules.md]
3. **Understand Naming Conventions:** Ensure consistency across all new inputs and objects. -> [docs/Naming Standards.md]

***

## 🏛️ Architectural Deep Dive (Technical Reference)
This section contains detailed, technical guidance on the project's structure. Use this when investigating model connections, metadata formats, or system behavior.

*   **[Project Architecture Overview]**: A merged guide detailing the physical organization of PBIP artifacts, including report paths and semantic model locations. -> [docs/project_architecture.md](#)
*   **[PBIR & TMDL Format Standards]**: Technical details on the source-control-friendly metadata formats used for reports (PBIR) and data models (TMDL).
*   **[Data Model Schema Reference]**: The canonical list of tables, relationships, and fields. -> [docs/DataModel_Schema.md]

## 📊 Data Layer & Business Logic (The Core)
This section defines the measurable aspects of the business. **Treat these definitions as contract code.**

*   **[KPI Measures Definition]**: A comprehensive catalog of all calculated metrics (DAX formulas, assumptions, and use cases). -> [docs/Measures_Reference.md]
*   **[Data Sources & ETL Guidance]**: Defines external data inputs, refresh logic, and data governance protocols. (If available)

## 🛠️ Operational Guides (Process & Process Control)
This section governs *how* we work on the project.

*   **[Contributor Workflow Guide]**: Step-by-step guidance for interacting with the PBIP/Fabric environment. -> [docs/agent-instructionss.md]
*   **[Handover and Context Tracking]**: For documenting current state, assumptions, and next steps during an agent handover. -> [docs/agent-handover.md]
*   **[Change Log & History]**: All recorded project changes are tracked here. -> [docs/change-log.md]

***

## 💡 Key Principles Reminder
*   **Principle of Least Surprise:** Every change must be minimal, precise, and easy to review in a Git Pull Request.
*   **Analysis First:** Always analyze the problem, propose a plan, then apply edits only after explicit approval.