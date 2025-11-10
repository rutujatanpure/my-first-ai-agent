# 🤖 My First AI Agent

This project showcases my **first AI agent**, built using **Google’s Agent Development Kit (ADK)** and **Gemini**, capable of reasoning, taking actions, and using real-world tools (like Google Search) to provide **live, up-to-date answers** — not just static text.

🧠 This agent doesn’t just respond — it **thinks, acts, and observes** before answering.

---

## 🚀 Features

✅ Built with **Google’s Agent Development Kit (ADK)**  
🔍 Uses **Gemini API** for intelligent reasoning  
🌐 Integrates **Google Search tool** for real-time information  
🧩 Modular agent architecture — easily expandable into multi-agent systems  
💡 Runs seamlessly in **Kaggle Notebooks** or any Python environment  

---

## 🧠 How It Works

An AI agent can reason, take actions, and use tools to improve its responses.

**Flow:**



Prompt → Agent → Thought → Action → Observation → Final Answer


**Example Query:**

> “What’s the weather in London?”

The agent:
1. Thinks about what’s needed (current weather info).  
2. Takes an action (uses Google Search).  
3. Observes the result.  
4. Responds with a real-time, accurate answer.

---

## ⚙️ Technologies Used

| Category | Tools / Libraries |
|-----------|------------------|
| 🧠 AI Model | Gemini 2.5 Flash Lite |
| 🧰 SDK | Google Agent Development Kit (ADK) |
| 🧩 Runner | InMemoryRunner |
| 🔧 Tool | google_search |
| 💬 Language | Python 3.11 |
| ☁️ Platform | Kaggle Notebooks |
| 🔒 Secrets | GOOGLE_API_KEY (securely stored in Kaggle Secrets) |

---

## 🧾 Setup Guide

### 1️⃣ Get Your Gemini API Key
- Go to [**Google AI Studio**](https://aistudio.google.com/app/apikey)  
- Create a new key and copy it safely

### 2️⃣ Add It to Kaggle Notebook
In your Kaggle Notebook:

```python
import os
from kaggle_secrets import UserSecretsClient

GOOGLE_API_KEY = UserSecretsClient().get_secret("GOOGLE_API_KEY")
os.environ["GOOGLE_API_KEY"] = GOOGLE_API_KEY
os.environ["GOOGLE_GENAI_USE_VERTEXAI"] = "FALSE"

print("✅ Gemini API key setup complete.")

3️⃣ Import ADK Components
from google.adk.agents import Agent
from google.adk.runners import InMemoryRunner
from google.adk.tools import google_search

4️⃣ Define Your Agent
root_agent = Agent(
    name="helpful_assistant",
    model="gemini-2.5-flash-lite",
    description="An AI agent that provides current, intelligent answers.",
    instruction="Be a helpful AI. Use Google Search for live data.",
    tools=[google_search],
)

5️⃣ Run the Agent
runner = InMemoryRunner(agent=root_agent)
response = await runner.run_debug("What is the current AI trend in 2025?")
print(response)

🌍 Example Queries

Try these prompts:

“Who is the current CEO of OpenAI?”

“What’s the latest AI breakthrough this month?”

“Show top AI conferences in 2025.”

“Compare Gemini vs GPT models in real-time.”

🧰 Project Structure
my-first-ai-agent/
│
├── my_first_ai_agent.ipynb     # Notebook where the agent is built
├── sample-agent/
│   ├── agent.py                # Agent logic
│   ├── __init__.py
│
├── README.md                   # This file
└── .gitignore                  # To hide secrets and cache files


Example .gitignore:

.env
*.json
__pycache__/
.ipynb_checkpoints/
.vscode/
.idea/
*.log

🧭 Future Scope

🧩 Build a multi-agent system with collaborative agents
⚙️ Integrate custom tools (API calls, data analysis, web scraping)
🧠 Deploy the agent as a web service using adk web
📊 Add logging and observability for tracking reasoning steps

🧠 Key Highlights

Real-time reasoning and live data fetching

Runs 100% securely — API key stored in Kaggle Secrets

Easily portable to any Python environment



Built with Google’s ADK and Gemini 2.5 Flash Lite, fully implemented in Python and executed on Kaggle.

💬 “From prompt to action — this AI agent truly thinks before it answers.”
