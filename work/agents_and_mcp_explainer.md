# Technical Explainer: Workflows vs Agents and Model Context Protocol (FL-05)

## 1. Workflow vs. Agent Distinction

- **Workflows:** Deterministic, hard-coded execution paths where code/prompts follow predefined steps (e.g., Step A ➔ Step B ➔ Step C). The system does not make dynamic control-flow decisions.
- **Agents:** Systems where an LLM dynamically determines its own execution steps, chooses which tools to invoke, and evaluates when a goal is satisfied based on feedback loops.
- **FL-04 Classification:** My FL-04 pipeline is a **Workflow**. It follows a rigid, linear prompt-chaining sequence (Gather ➔ Critique ➔ Format) with no dynamic branching or conditional loop autonomy.

---

## 2. Model Context Protocol (MCP) Core Primitives

Model Context Protocol (MCP) provides a standardized interface connecting LLM interfaces to local and remote data sources:

1. **Tools:** Executable functions called by the LLM (e.g., executing Python code, querying SQL databases, fetching REST APIs).
2. **Resources:** Passive data sources provided to the model as context (e.g., local files, log captures, documentation files).
3. **Prompts:** Pre-designed templates and instructions that guide how the model uses tools and resources effectively.

---

## 3. MCP Tasks Demonstration

To extend chat capabilities beyond plain text generation, three specific tasks were executed via external tool connectors:

1. **Local Filesystem Inspection:** Reading local repository code (`notebooks/capstone.ipynb`) directly to audit function signatures without manual copy-pasting.
2. **Live Data Fetching:** Querying live GitHub API endpoints to check repository commit history and pull request statuses.
3. **Environment Execution:** Invoking terminal execution tools to check Python environment packages and run pytest suites directly.

---

## 4. Upgrading FL-04 Workflow to an Autonomous Agent

To upgrade the static FL-04 paper-summarization workflow into a true **Autonomous Agent**, the following architectural changes are required:

1. **Dynamic Tool Use:** Equip the model with MCP tools to independently search ArXiv, download PDF papers, and parse LaTeX sources based on a query.
2. **Feedback Loop & Self-Correction:** Enable an evaluation loop where the LLM checks its own output against a strict validation rubric. If mathematical gaps are detected, it automatically re-queries tools to fetch missing details.
3. **Goal-Driven Execution Loop:** Replace hard-coded step sequencing with a `while not done:` decision loop where the model autonomously plans, executes, and halts only when full empirical verification is achieved.
