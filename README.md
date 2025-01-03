# Chatbot with Langchain and ChatGroq Integration

This repository contains code for building an AI chatbot using Langchain and ChatGroq. The bot leverages the `ChatGroq` API and integrates with `TavilySearchResults` for real-time web search functionality. The system is designed to allow the chatbot to query tools and interact with users through a flexible workflow.

### Features:
- **ChatGroq Integration**: Utilizes ChatGroq's `Gemma2-9b-It` model for advanced NLP tasks.
- **Web Search Integration**: Makes use of `TavilySearchResults` to fetch real-time search results from the web.
- **Custom Workflow**: A dynamic workflow based on Langgraph's `StateGraph` to handle the conversation state and routing between model responses and tool calls.
- **Memory Management**: Implements memory-saving functionality to track and save the chatbot's state during interactions.

### Setup:
1. **Install Dependencies**:
   Ensure you have the required libraries by installing dependencies from `requirements.txt`.
   
2. **Environment Variables**:
   - Set the `GROQ_API_KEY` environment variable with your API key for ChatGroq.

   Example:
   ```bash
   export GROQ_API_KEY="your_api_key"
   ```

3. **Run the Application**:
   The chatbot will respond to queries such as "who is the current prime minister of the USA?" by using Langchain's `StateGraph` for structured message passing.

### How it Works:
1. **`chatbot` class**: Manages the entire bot workflow, including tool calls and model invocations.
2. **`call_tool` method**: Initializes `TavilySearchResults` for querying search results.
3. **`call_model` method**: Sends messages to the `ChatGroq` model for processing.
4. **`router_function`**: Decides whether to route to tools or end the conversation based on the state of the messages.
5. **`__call__` method**: Defines the workflow and compiles it for use.

### Example:
Run the bot to ask a question:
```python
mybot = chatbot()
workflow = mybot()
response = workflow.invoke({"messages": ["who is the current prime minister of USA?"]})
print(response['messages'][-1].content)
```

### Dependencies:
- `langgraph`
- `langchain_core`
- `langchain_groq`
- `langchain_community.tools.tavily_search`
- `dotenv`

Make sure to install the necessary packages for the environment setup.

---

Feel free to contribute to this repository or suggest improvements to enhance the chatbot’s functionality!
