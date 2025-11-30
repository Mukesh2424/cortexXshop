# 🛍️ CortexXShop – ACP-Inspired Voice Shopping Agent  
### Day 9 – Murf AI Voice Agent Challenge

CortexXShop is a **voice-driven shopping assistant** inspired by the Agentic Commerce Protocol (ACP).  
It interprets natural shopping intent, browses a product catalog using backend Python functions, and creates structured orders — all through conversation.

This project is built as part of **Day 9** of the **Murf AI Voice Agent Challenge**.

---

## 🚀 Features

### 🗣 Voice + Text Interaction
- Works with microphone or typed input  
- Natural, conversational shopping experience  

### 🛍 ACP-Inspired Commerce Flow
- User expresses shopping intent  
- Agent interprets goal  
- Backend merchant layer handles catalog and ordering  
- Clean separation between LLM and commerce logic  

### 📦 Catalog Browsing
Supports:
- Category filters  
- Color filters  
- Price range queries  
- Attribute-based search (size, type, material)  
- “Show me items under ___”  
- “Do you have black hoodies?”  
- “What mugs do you have?”  

### 🧩 Structured Order Creation
Orders include:
- Order ID  
- Product ID(s)  
- Quantity  
- Total price  
- Currency  
- Timestamp  

### 📁 JSON Persistence
Orders are saved into:
- `orders.json` or in-memory list

### 🔍 Order History
User can ask:
> “What did I just buy?”  
> “Show my last order.”

The agent retrieves and summarizes the most recent order.

---

## 🏗 Architecture Overview

### **1. Conversation Layer (LLM / Agent)**  
- Understands user queries  
- Extracts filters (color, price, category…)  
- Calls Python merchant functions  
- Summarizes results  
- Confirms orders  

### **2. Merchant Layer (Python)**  
Your Python backend includes:

```python
list_products(filters)
create_order(line_items)
get_last_order()
