# RISSHIKK-langgraph-mat496
All that I have learnt from the course "Foundation: Introduction to LangGraph" by academy.langchain.com

# Module 1

**Video 1 - Motivation:**  
    The video explains that while traditional language model workflows (called chains) are reliable, they’re often too rigid. LangGraph was created to bring more flexibility, allowing developers to define reliable parts of the process while letting the LLM make dynamic decisions when needed, therefore it helps build smarter, more adaptable AI agents.  

**Video 2 - Simple Graph:**  
    Learnt how to make simple graphs in LangGraph, which includes defining states, nodes, conditional edges, graph construction & visualization and graph invocation  
    Changes made: Added my own graph implementation at the end of the source code titled "My Examples"  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%201/simple_graph_final.ipynb  

**Video 3 - LangGraph Studio Setup:**  
    Learnt how to setup and run LangGraph Studio on local device and in the studio, learnt how to use the UI to input a graph state, see the thread for the dataflow of the graph  
    Changes made: Since I'm using Groq as the client, I had to download the necessary dependencies as part of the setup after setting up the environment, made a .env file with the Groq and Langsmith API keys, changed the client in **router.py** and **agent.py** (located in the /studio directory) from ChatOpenAI() to ChatGroq() for tool binding.  

**Video 4 - Chains:**  
    Learnt how to use chat messages as our graph state, chat models as graph nodes, binding tools to the model and executing tool calls in graph nodes  
    Changes made: Used Groq's "openai/gpt-oss-120b" model, implemented my own tool calling example at the end  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%201/chain.ipynb  

