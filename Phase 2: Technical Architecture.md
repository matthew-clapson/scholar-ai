# **🤖 Phase 2: CrewAI Technical Architecture**

This document outlines the technical implementation, agent definitions, and the specific "Manager" logic required for the CrewAI workflow.

**Status:** Proven (standard CrewAI implementation patterns).

## **1\. Agent Definitions**

### **Agent 1: The High-Level Architect**

* **Backstory:** An expert librarian and taxonomist specializing in knowledge mapping.  
* **Task:** Perform a high-level search and generate a JSON-ready structure of topics and sub-topics.  
* **Expected Output:** topics.md and a Python Dictionary for the Manager.

### **Agent 2: The Deep-Dive Scholar**

* **Backstory:** A senior technical researcher with a PhD in information retrieval.  
* **Task:** Accept a specific topic, determine depth requirements, and fetch all metadata (Date, Links, Detail).  
* **Expected Output:** Single .md file per topic with standardized front-matter.

### **Agent 3: The Pedagogical Ranker**

* **Backstory:** A curriculum designer who understands learning curves.  
* **Task:** Review all .md files in the /research/ folder. Build a dependency graph to sort them.  
* **Expected Output:** A sorted index list.

### **Agent 4: The Master Collator**

* **Backstory:** A professional technical editor and publisher.  
* **Task:** Merge files, create the TOC with anchor links, and generate the checkbox-based progress tracker.  
* **Expected Output:** FINAL\_GUIDE.md.

## **2\. Process Flow: The Hierarchical Manager**

To solve the "Loop" requirement (running Agent 2 for every topic), we implement a **Manager Agent**:

* The Manager uses the Process.hierarchical setting.  
* The Manager receives the output from Agent 1 and spawns individual tasks for Agent 2\.  
* **Logic:** for topic in topics: delegate\_task(Scholar, topic).

## **3\. Toolset Integration**

* **Search:** SerperDevTool (requires API key).  
* **Scraping:** Firecrawl or Crawl4AI (preferred for CachyOS performance).  
* **Storage:** Python os and pathlib for managing the /research/ directory.