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

**Video 5 - Router:**  
    Learnt about the concept of router agent, where the chat model routes between a direct response or a tool call based upon the user input, specifically how the LLM is directing the control flow either by calling a tool or just responding directly.  
    Changes madee: Used Groq's "openai/gpt-oss-120b" model, implemented my own router example at the end and pasted the screenshots of the LangGraph Studio visualization  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%201/router.ipynb  

**Video 6 - Agent:**  
    Learnt about agentic architecture, where it can pass the ToolMessage back to the LLM, which can either call another tool or respond directly. Also saw how we can see the traces of the whole conversation on Langsmith  
    Changes made: Used Groq's "openai/gpt-oss-120b" model, implemented my own agent example at the end and pasted the screenshots of the LangSmith traces  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%201/agent.ipynb  

**Video 7 - Agent With Memory:**  
    Learnt about how agents can store previous data in memory through persistence, where a checkpointer is used to automatically save the graph state after each step  
    Changes made: Used Groq's "openai/gpt-oss-120b" model, implemented my own agent with memory example at the end and pasted the screenshots of the LangGraph Studio visualization  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%201/agent_memory.ipynb  

**Video 8 - Deployment:**  
    Learnt on how to deploy our implemented Graph models locally to studio and to LangGraph Cloud  
    Implemented code to deploy model locally: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%201/deployment.ipynb  
    (Cannot deploy on Cloud since it is a paid feature)  

# Module 2

**Video 1 - State Schema:**  
    Learnt how to define state schemas in LangGraph using three approaches - TypedDict, dataclass, and Pydantic. Also observed that Pydantic is unique because it includes built-in runtime validation, unlike the other two methods.  
    Changes made: Implemented my own example at the end  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%202/state_schema.ipynb  

**Video 2 - State Reducers:**  
    Learnt how to manage state updates in LangGraph using reducers, particularly focusing on how they resolve ambiguity in concurrent updates during branching. Learnt about the default overwriting behavior, the need for reducers when branching, how to use built-in reducers like "operator.add" and "add_messages" and how to create custom reducers for specific needs like handling None values or modifying messages.  
    Changes made: Implemented my own example at the end  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%202/state_reducers.ipynb  

**Video 3 - Multiple Schemas:**  
    Learnt how to use multiple schemas in LangGraph to manage data flow, allowing for private state within nodes and explicit input/output schemas to control the graph's interface. Using these methods, we can precisely control what data enters, is processed within, and exits the graph.  
    Changes made: Implemented my own example at the end  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%202/multiple_schemas.ipynb  
    
**Video 4 - Trim and Filter Messages**  
    Learnt how to manage message history in LangGraph using different techniques: reducing the number of messages, filtering messages to select a subset, and trimming messages based on token limits. These methods are crucial for building efficient chatbots by controlling the input provided to the language model.  
    Changes made: Implemented my own example at the end and added screenshots of Langsmith traces of my implementation  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%202/trim_filter_messages.ipynb  
    
**Video 5 - Chatbot w/ Summarizing Messages and Memory**  
    Learnt building a chatbot with LangGraph that uses message summarization to manage conversation length. It also shows how to add memory to the chatbot using LangGraph's built-in persistence mechanism with thread IDs.  
    Changes made: Implemented my own example at the end and added screenshots of Langsmith traces to show the working of persistence and summarization  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%202/chatbot_summarization.ipynb  

**Video 6 - Chatbot w/ Summarizing Messages and External Memory**  
    Learnt building a LangGraph chatbot with persistent memory using an external DB (Sqlite) checkpointer. It shows how to define the conversation state, create nodes for interaction and summarization, and compile a graph that saves and loads the conversation history from a database.  
    Changes made: Tried my own set of prompts on the graph and verified the summarization and remembering past chats through external DB (PostGres) memory  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%202/chatbot_external_memory.ipynb  

# Module 3

**Video 1 - Streaming:**  
    Learnt how to set up a LangGraph chatbot with memory and how to stream outputs from the graph during execution using different streaming modes (values, updates, and astream_events) to observe the graph's state and chat model tokens.  
    Changes made: Used Groq's "openai/gpt-oss-120b" model, implemented my own example at the end  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%203/streaming-interruption.ipynb  

**Video 2 - Breakpoints:**  
    Learnt how to use breakpoints in LangGraph to pause the execution of your agent's graph at specific nodes, enabling human-in-loop workflows like user approval of actions before they are executed.  
    Changes made: Used Groq's "openai/gpt-oss-120b" model, implemented my own example at the end  
    Tweaked code: https://github.com/RISSHIKK/RISSHIKK-langgraph-mat496/blob/main/Module%203/breakpoints.ipynb  
