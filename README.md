# ELECTRICONIT – Customer Service Chatbot

Welcome to the **ELECTRICONIT** Customer Service Chatbot repository! This project implements a multi-agent AI customer support assistant built with **LangGraph** and **LangChain**.

---

## 🛠️ Architecture Overview

The system routes incoming customer inquiries through a **Router / Supervisor** node powered by an **Intent Classifier**. Based on the classified intent, queries are directed to specialized agents or the off-topic fallback handler. Conversation history is continuously synchronized using **MemorySaver**.
