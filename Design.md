# **🎓 Agentic Learning System: Integrated Strategy & Architecture**

This document combines the pedagogical framework with the CrewAI technical implementation details to create a unified roadmap for your CachyOS-based learning solution.

## **🏗️ 1\. Conceptual Framework (The Strategy)**

### **Data Hierarchy & Ontology**

The system follows a recursive "Topic Tree" to ensure a logical flow of information:

* **Root Topic:** The primary subject (e.g., "Quantum Computing").  
* **Sub-Topics:** Core pillars (e.g., "Qubits," "Superposition").  
* **Related Topics:** Prerequisite or lateral concepts (e.g., "Linear Algebra").

### **Information Depth & Metadata Logic**

We employ a **Conditional Depth Model** where every concept fetched must include:

* **Origin Date:** When the concept was first introduced (for the Historical Glossary).  
* **Complexity Weight:** A 1-10 scale based on abstractness and prerequisite requirements.  
* **Provenance:** Direct links to official documentation or high-authority whitepapers.  
* **Depth Trigger:** A "Full Detail" section is generated only if the Complexity Score ![][image1] or it is a "Major Pillar."

## **🤖 2\. CrewAI Technical Architecture**

### **Process Flow: The Hierarchical Manager**

To handle the recursive nature of learning, the Crew uses Process.hierarchical. A **Manager Agent** oversees the lifecycle:

1. **Map:** Agent 1 maps the territory.  
2. **Iterate:** The Manager spawns an instance of Agent 2 for *each* topic found.  
3. **Sort:** Agent 3 organizes the resulting data.  
4. **Publish:** Agent 4 compiles the final artifact.

### **Agent Definitions & Tasks**

| Agent | Role | Responsibility | Strategy Alignment |
| :---- | :---- | :---- | :---- |
| **Agent 1: The Architect** | High-Level Researcher | Identifies the Hierarchy (Topic \> Sub \> Related). Outputs topics.md. | Establishes the **Ontology**. |
| **Agent 2: The Scholar** | Deep-Dive Specialist | Fetches Summary, Full Detail, Date, and Complexity. Outputs .md per topic. | Executes the **Depth Logic**. |
| **Agent 3: The Ranker** | Curriculum Designer | Analyzes prerequisites and complexity to sort the learning path. | Executes **Pedagogical Ranking**. |
| **Agent 4: The Collator** | Technical Editor | Merges content, creates TOC, and the Interactive Progress Tracker. | Delivers the **Success Metrics**. |

## **🛠️ 3\. Execution Logic & Tooling**

### **Toolset Integration**

* **Search:** SerperDevTool (Optimized for structured metadata like dates).  
* **Scraping:** Crawl4AI (Preferred for CachyOS performance/low overhead).  
* **Storage:** Python pathlib for managing the /research/ temporary directory.

### **The "Progress Tracker" Schema**

The Collator is specifically tasked with generating the following Markdown-ready checkboxes for each topic:

* \[ \] **Read** (Initial exposure)  
* \[ \] **Describe (Reminded)** (Passive recognition)  
* \[ \] **Describe (Fluid)** (Active recall)  
* \[ \] **Implemented** (Actionable application)

### **Ranking Algorithm**

The Ranker (Agent 3\) must follow this logic:

Rank Score \= (Prerequisite Count \* 2\) \+ (Complexity Score)

*This ensures that foundational "bottleneck" topics appear first regardless of their individual difficulty.*