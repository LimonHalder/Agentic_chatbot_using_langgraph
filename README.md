# LLM-Powered Chatbot with Tool Integration

## Overview
This project is an AI chatbot built using **LangGraph** and **ChatGroq (Gemma2-9B-It)**. It integrates **TavilySearchResults** to fetch real-time web search results and utilizes a dynamic workflow for intelligent tool routing.

## Features
- **Conversational AI:** Uses ChatGroq for LLM-based responses.
- **Web Search Integration:** Retrieves up-to-date information using TavilySearchResults.
- **Dynamic Workflow:** Implements a state-based workflow with conditional tool routing.
- **Scalable & Modular:** Designed for easy extension with additional tools.

## Installation
### Prerequisites
Ensure you have Python installed (>=3.8). Install dependencies using:
```bash
pip install langgraph langchain_groq langchain_community python-dotenv
```

### Environment Setup
Create a `.env` file and add your API key:
```env
GROQ_API_KEY=your_groq_api_key
```

## Usage
Run the chatbot with:
```bash
python chatbot.py
```
Example query:
```python
response = workflow.invoke({"messages": ["Who is the current Prime Minister of the USA?"]})
print(response['messages'][-1].content)
```

## Project Structure
```
├── chatbot.py  # Main chatbot logic
├── .env        # API keys (ignored in .gitignore)
├── README.md   # Documentation
└── requirements.txt  # Dependencies
```

## Technologies Used
- **LangGraph** (for workflow management)
- **ChatGroq** (LLM-powered responses)
- **TavilySearchResults** (web search integration)
- **Python** (backend development)

## Future Enhancements
- Add more tool integrations (e.g., Wikipedia, financial APIs)
- Implement memory for better conversation flow
- Deploy as an API for external access

## License
This project is licensed under the MIT License.

---
### 🚀 Contributions & Feedback
Feel free to fork, contribute, or suggest improvements!
