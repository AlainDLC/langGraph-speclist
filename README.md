# 🧠 LangGraph – Advanced Conversational AI Workflows

This repository contains code and examples for building **advanced conversational AI systems** using **LangGraph**, a graph-based Python framework for managing dialogue workflows.

---

## 📦 Repository Contents

- **examples/** – End-to-end examples of LangGraph workflows  
- **notebooks/** – Jupyter notebooks for experimentation and learning  
- **nodes/** – Reusable components like agent nodes, tool wrappers, and memory handlers  
- **utils/** – Helper functions and utilities  
- **requirements.txt** – List of Python dependencies  
- **README.md** – Project overview and instructions

---

## 📚 What This Project Covers

- Graph-based design of dialogue flows  
- Creating and linking nodes (functions, tools, LLMs)  
- Managing multi-turn conversations with state  
- Integrating memory and external APIs  
- Building reusable, modular, and testable components

---

## ⚙️ Example: Minimal Graph

```python
from langgraph.graph import StateGraph

def reply_node(state):
    user_input = state["input"]
    return {"output": f"You said: {user_input}"}

graph = StateGraph()
graph.add_node("reply", reply_node)
graph.set_entry_point("reply")

app = graph.compile()
response = app.invoke({"input": "Hello LangGraph!"})
print(response["output"])
