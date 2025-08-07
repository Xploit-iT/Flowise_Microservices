# 🧠 Text Summarizer Microservice (Flowise + LLM)

This is a modular microservice built using [Flowise](https://flowiseai.com/) that summarizes long blocks of text into concise summaries using an LLM backend (OpenAI, local model, or custom provider).

This project is part of my internship assignment focused on building AI microservices using Flowise.

---

## 🚀 Features

- Built with Flowise (no-code/low-code platform)
- Summarizes long paragraphs or articles into brief summaries
- Can be accessed via REST API or directly through Flowise UI
- Compatible with Postman, curl, or any HTTP client

---

## 📦 Tech Stack

- 🧩 **Flowise**
- 🔗 **LangChain**
- 🤖 **LLM (OpenAI / Local)**
- 🧪 **Postman** for API testing

---

## 📂 Project Structure

text-summarizer/    
├── README.md    
├── flowise-chatflow/    
│ └── summarizer.chatflow.json    
├── postman/    
│ └── text-summarizer.postman_collection.json    
├── screenshots/    
│ └── demo.png    



---

## 🛠️ Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/Xploit-iT/text-summarizer.git
cd text-summarizer
```
### 2. Setup Flowise (if not already)
```bash
npm install -g flowise
npx flowise start
```
> ✅ Pre-requisite: Ensure Node.js is installed on the machine. Node v18.15.0 or v20 and above is supported.

### 3. Import Flow
Open Flowise at: http://localhost:3000    
Go to Chatflows → Import    
Upload summarizer.chatflow.json    

## 📫 API Usage
🔹 Endpoint
```bash
POST http://localhost:3000/api/v1/prediction/<flow-id>
```
🔹 Headers
```pgsql
Content-Type: application/json
```
🔹 Sample Request Body
```json
{
  "question": "Barnaby the troll lived under the bridge by the Whispering Woods. He was a grumpy old troll..."
}
```
🔹 Sample Response
```json
{
  "text": "Barnaby, a grumpy troll, softens after helping Lily retrieve her ribbon, beginning a gentle friendship."
}
```
## 🧪 Testing with Postman
Open Postman    
Import text-summarizer.postman_collection.json    
Click "Send" on the pre-configured request    
View summarized result

## 🌐 Credits
Flowise AI    
LangChain    
Groq API    
OpenAI or any LLM used

## ✨ Author
Mohammad Muzammil Abbasi    
B.Tech, CSE (AI & ML)    
LinkedIn | GitHub    

## 💡 License
This project is part of an internship assignment and open for educational use.


