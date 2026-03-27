# **🧠 Phase 1: Strategy**

This document defines the pedagogical framework and data hierarchy for the learning system. It focuses on *how* information is structured and validated.

**Status:** Based on theory/Best practices for instructional design.

## **1\. Data Hierarchy & Ontology**

To ensure a structured learning path, the system follows a recursive "Topic Tree":

* **Root Topic:** The primary subject (e.g., "Quantum Computing").  
* **Sub-Topics:** Core pillars of the subject (e.g., "Qubits," "Superposition").  
* **Related Topics:** Lateral concepts or prerequisite technologies (e.g., "Linear Algebra").

## **2\. Information Depth Logic**

The strategy employs a **Conditional Depth Model**:

* **The Summary/Refresher:** 100-200 words. Used for foundational concepts or topics the user likely knows.  
* **The Full Detail:** Deep technical breakdown. Triggered if the "Complexity Score" is ![][image1] or if the concept is a "Major Pillar."

## **3\. Metadata & Provenance**

Every piece of information must be "Stamped" with:

* **Origin Date:** When was the concept first introduced? (Essential for the Historical Glossary).  
* **Complexity Weight:** 1-10 scale.  
* **Source Integrity:** Links to official documentation, whitepapers, or trusted industry blogs.

## **4\. Learning Progression (The Pedagogical Rank)**

Ranking is determined by **Prerequisite Mapping** rather than just difficulty.

* *Rule:* If Topic B mentions Topic A in its definition, Topic A must be ranked lower (earlier) in the learning list.

## **5\. Success Metrics (The "Implemented" Goal)**

The learning list includes a checkbox for "Implemented." This requires the Agent to identify a specific, actionable project or coding exercise for the topic where applicable.