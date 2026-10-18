# ⚡ ELECTRONIT – Agentic AI Customer Support System

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-Framework-1C3C3C?style=for-the-badge)
![LangGraph](https://img.shields.io/badge/LangGraph-Multi--Agent-FF6F61?style=for-the-badge)

An agentic multi-agent AI customer service assistant built with **LangGraph** and **LangChain** for **ELECTRONIT**, an online electronics retailer.

---

## 📐 Architecture Overview

The system routes incoming customer queries through a **Router / Supervisor** node powered by an **Intent Classifier**. Based on the query, it delegates tasks to specialized agents, maintains session history via **MemorySaver**, and handles out-of-scope inquiries with a polite fallback handler.

![Customer Support Architecture Diagram](Customer%20Support%20Architecture%20Diagram.png)

### 🤖 Specialized Agents & Tools
* **Router / Supervisor:** Classifies customer intent and routes the query to the correct handler.
* **Order Status Agent:** Queries order databases to provide live tracking, shipping, and delivery status.
* **Refund / Return Policy Agent:** Reads store policy documents to evaluate return eligibility, deadlines, and exchange rules.
* **Product Recommendation Agent:** Searches the electronics catalog to compare specs and suggest items based on budget and user needs.
* **Fallback Handler:** Gracefully redirects off-topic questions back to ELECTRONIT support capabilities.
* **MemorySaver:** Synchronizes multi-turn conversation context across all agents.

---

## 🚀 Quickstart

### 1. Prerequisites & Environment
```bash
git clone [https://github.com/your-username/electronit-chatbot.git](https://github.com/your-username/electronit-chatbot.git)
cd electronit-chatbot
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
