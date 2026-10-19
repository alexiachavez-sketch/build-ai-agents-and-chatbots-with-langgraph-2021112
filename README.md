# ELECTRONIT - Multi-Agent Customer Service Chatbot

## Project Overview
ELECTRONIT is an AI customer service chatbot built using LangGraph and LangChain. It uses an intentional supervisor/router architecture to classify customer intent and seamlessly direct queries to three specialized agents, backed by persistent thread memory (`MemorySaver`).

## Team Members & Responsibilities
- **Eseta:** Project Coordinator (Timeline, rubric checklist)
- **Tanvi:** Dev 1 (Environment setup & API integration)
- **Andres:** Dev 2 (Agents, Router, Memory implementation)
- **QA / Tester:** Test conversations & output capture
- **Brandon Le & Alexia Chavez:** Presenter / Editor (Slides, README & Video)

## System Architecture
![Architecture Diagram](./Customer%20Support%20Architecture%20Diagram.png)

### The Three Agents
1. **Order Status Agent:** Uses the `lookup_order_status` tool to fetch shipping dates and order status by ID.
2. **Refund/Return Policy Agent:** Provides accurate return window rules, restocking fees, and instructions.
3. **Product Recommendation Agent:** Uses the `get_product_catalog` tool to suggest laptops based on budget and user needs.
## Test Results & Memory Proof

```text
============================================================
TEST 1: MULTI-TURN CONVERSATION WITH MEMORY & AGENT SWITCHING
============================================================

[Thread: customer-001] 👤 USER: Hi, I want to check order ORD-1001.
[Thread: customer-001] 🤖 BOT:  Your order ORD-1001 for the AlphaBook Pro has been shipped. The expected delivery date is October 22, 2026. If you need further assistance, just let me know!

[Thread: customer-001] 👤 USER: When will it arrive?
[Thread: customer-001] 🤖 BOT:  Your order ORD-1001 for the AlphaBook Pro is expected to arrive on October 22, 2026. If you have any more questions, feel free to ask!

[Thread: customer-001] 👤 USER: Can I return it if I don't like it?
[Thread: customer-001] 🤖 BOT:  Yes, you can return the item within 30 days of delivery if you don't like it. Please note that opened items will incur a 15% restocking fee unless the item is defective. If you need assistance with the return process, let me know!

============================================================
TEST 2: INDIVIDUAL AGENTS & EDGE CASES
============================================================

[Thread: customer-002] 👤 USER: I need a laptop for high-end video editing and 3D rendering. What do you recommend?
[Thread: customer-002] 🤖 BOT:  For high-end video editing and 3D rendering, I recommend the **SpectraBook S**. It features an Intel Core i9 processor, 64GB of RAM, and a 2TB SSD, making it a powerful workstation suitable for demanding tasks. 

If you're looking for a slightly lower price point, the **OmegaPro G17** with a Ryzen 9 5900HX, 32GB RAM, and 1TB SSD is also a solid choice, especially for gaming and creative work.

Let me know if you need more information on either option!

[Thread: customer-003] 👤 USER: Can you give me status on order ORD-9999?
[Thread: customer-003] 🤖 BOT:  I couldn't find any information for order ID 'ORD-9999'. Please double-check the order ID and try again. If you need further assistance, feel free to ask!

[Thread: customer-004] 👤 USER: Who won the last Super Bowl?
[Thread: customer-004] 🤖 BOT:  I’m sorry, but I can only assist with questions about orders, returns, refunds, and product recommendations at ELECTRONIT. Is there anything related to our store I can assist with?

[Thread: customer-005] 👤 USER: I need help with something.
[Thread: customer-005] 🤖 BOT:  I’m sorry, but I can only assist with questions about orders, returns, refunds, and product recommendations at ELECTRONIT. Is there anything related to our store I can assist with?

============================================================
TEST 3: MEMORY ISOLATION PROOF
============================================================

[Thread: customer-002-isolated] 👤 USER: When will my order arrive?
[Thread: customer-002-isolated] 🤖 BOT:  Could you please provide me with your order ID so I can check the status and delivery details for you?

## Setup & API Key Instructions
1. Clone the repository:
   ```bash
   git clone [https://github.com/alexiachavez-sketch/build-ai-agents-and-chatbots-with-langgraph-2021112.git](https://github.com/alexiachavez-sketch/build-ai-agents-and-chatbots-with-langgraph-2021112.git)
