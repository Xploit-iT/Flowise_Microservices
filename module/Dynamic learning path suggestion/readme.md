
# 🧠 Dynamic Learning Path Suggestion (Flowise AgentFlow + LLM)

This project is part of my internship assignment focused on building AI microservices with Flowise and LangChain. It dynamically generates personalised learning paths through an interactive, step-by-step conversational flow.

---

## 🚀 Features
- Built with Flowise AgentFlow (Start Node + LLM Node)  
- Asks one question at a time and waits for user input before proceeding  
- Uses state management (`$flow.state`) to store and recall conversation context  
- Dynamically suggests learning paths based on user responses  
- Fully compatible with REST API calls or Flowise UI  
- Can be tested via Postman, curl, or browser  

---

## 📦 Tech Stack
- Flowise AgentFlow V2  
- LangChain for LLM integration  
- LLM (OpenAI, local model, or OpenRouter)  
- Postman for API testing  
- Node.js for Flowise environment  

---

## 🛠️ Development Journey & Challenges

### 1. First Attempt — Single Chat Prompt Template
I initially used a single chat prompt template to collect user input.  

**Problem:**  
- There was a one-step delay due to memory variables being updated only after the next user message.  
- This caused the chatbot to respond using outdated values.  

---

### 2. Second Attempt — Prompt Chaining (5 Chains)
I tried prompt chaining with 5 sequential chains:  
- Each chain was meant to collect one piece of information from the user (e.g., skill level, learning goals, available time, etc.).  
- Goal: Use all collected inputs to generate a personalised learning path.  

**Problem:**  
- Flowise executed all chains at once after the first user input instead of pausing for each required response.  
- This broke the step-by-step interaction and skipped questions.  

---

### 3. Final Solution — AgentFlow with Human Input Control
I switched to AgentFlow, which solved all timing and sequencing issues:  
- **Start Node** → Initialises the flow  
- **LLM Node** → Processes each user input  
- **State Management** → Saves progress in `$flow.state`  
- **Pausing Mechanism** → Waits for user input before moving to the next step  

✅ **Result:** Smooth, interactive conversation that collects inputs in real-time and only proceeds when the user is ready.  

---

## 📂 Project Structure    
dynamic-learning-path/    
├── README.md    
├── chatflow/    
│ └── dynamic_learning_path.chatflow.json    
├── postman/    
│ └── dynamic_learning_path.postman_collection.json    
└── screenshots/    
└── demo_flow.png    

---

## ⚙️ Setup Instructions

**1️⃣ Clone the repository**
```
git clone https://github.com/Xploit-iT/dynamic-learning-path.git
cd dynamic-learning-path
```
**2️⃣ Install Flowise**
```

npm install -g flowise
npx flowise start
```
> ✅ Pre-requisite: Node.js (v18.15.0 or v20+) must be installed

**3️⃣ Import the Chatflow**

 - Open Flowise at: http://localhost:3000
 - Navigate to AgentFlows → Import
 - Upload dynamic_learning_path.chatflow.json

**4️⃣ Run the Flow**

 - Interact through Flowise UI or via API

## 📫 API Usage
Endpoint
```

POST http://localhost:3000/api/v1/prediction/<flow-id>
```
Headers
```

Content-Type: application/json
```
Sample Request
```

{
  "question": "I want to learn Data Science and I have 5 hours per week."
}
```
Sample Response
```

{
  "text": "Based on your schedule, here’s a 6-month learning path focusing on Python, statistics, and ML models..."
}
```
## 🧪 Testing with Postman
 - Import dynamic_learning_path.postman_collection.json    
 - Enter your Flow ID    
 - Click Send    
 - View personalised learning path output    

## 🌐 Credits
Flowise AI    
LangChain    
OpenAI / Local LLM    
Groq

## ✨ Author
Mohammad Muzammil Abbasi    
B.Tech – CSE (AI & ML)    
LinkedIn | GitHub    
