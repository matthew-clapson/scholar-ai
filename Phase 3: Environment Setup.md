# **🐧 Phase 3: CachyOS Environment Setup**

This document provides the optimized setup commands for running a high-performance Python environment on CachyOS (Arch-based).

**Status:** Proven (CachyOS/Arch compatibility).

## **1\. System Dependencies**

CachyOS users should utilize the tuned kernel performance by ensuring base-devel is present for Python wheel compilations.

\# Update and install base dependencies  
sudo pacman \-Syu \--noconfirm  
sudo pacman \-S base-devel python-pip python-virtualenv git \--noconfirm \--needed

## **2\. Virtual Environment Configuration**

We recommend a dedicated workspace to avoid system-level package conflicts.

mkdir \~/agentic-learning && cd \~/agentic-learning  
python \-m venv venv  
source venv/bin/activate

\# Install CrewAI and LLM connectors  
pip install crewai\[tools\] langchain\_google\_genai \--no-cache-dir

## **3\. Hardware Optimization (Optional)**

If you have an NVIDIA GPU on CachyOS, ensure cuda is installed to speed up local embedding models if you choose to use them.

sudo pacman \-S cuda \--noconfirm \--needed

## **4\. API Configuration**

Create a .env file in your root directory:

SERPER\_API\_KEY=your\_key\_here  
GOOGLE\_API\_KEY=your\_gemini\_key\_here  
\# If using Firecrawl  
FIRECRAWL\_API\_KEY=your\_key\_here

## **🐧 5\. Implementation Notes**

* **LLM Choice:** Use gemini-2.5-flash-preview-09-2025 for high-speed research or local Ollama models if privacy is preferred.  
* **Concurrency:** CachyOS's Bore Scheduler handles the multi-threading of Agent 2's "Deep Dives" exceptionally well. Ensure max\_rpm is set in CrewAI to avoid API rate limits during parallel scraping.