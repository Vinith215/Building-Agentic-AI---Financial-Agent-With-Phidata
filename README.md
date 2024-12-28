# Building-Agentic-AI---Financial-Agent-With-Phidata

1. Imports and Environment Setup
•	phi.agent: Provides the base class Agent for creating intelligent agents.
•	phi.model.groq: Introduces a specific AI model (e.g., Groq) that powers the agents.
•	phi.tools.*: Includes various tools for agents, such as:
•	YFinanceTools for financial data.
•	DuckDuckGo for web search capabilities.
.env Management: The .env file is used to securely load sensitive data (e.g., OpenAI API key)

2. Web Search Agent:

•	Purpose: Fetches data from the web using the DuckDuckGo search tool.
Key Features:
•	Utilizes the Groq model for processing and reasoning.
•	Tool: DuckDuckGo to search for information.
•	Instructions:
•	Always include sources in responses.
•	Display results in Markdown format.
•	Debugging: Shows tool calls (show_tool_calls=True).

3. Finance Agent
Purpose: Analyzes and presents financial data related to stocks.
Key Features:
•	Tool: YFinanceTools is configured for:
o	Stock price data.
o	Analyst recommendations.
o	Stock fundamentals.
o	Company news.
•	Instructions:
o	Use tables for displaying financial data.
o	Display output in Markdown.
•	Debugging: show_tool_calls=True enables insights into tool usage.

4. Multi-Agent Configuration
•	Purpose: Combines the capabilities of the Web Search Agent and Finance AI Agent into a unified multi-agent system.
•	Key Features:
o	Teams up the individual agents (web_search_agent and finance_agent).
o	Model: A more versatile version of Groq (llama-3.3-70b-versatile).
o	Unified instructions for all tasks:
	Always include sources.
	Use tables to display data.
o	Debugging: show_tool_calls=True ensures visibility into tool interactions.

5. Query Execution

Task: The multi-agent system is queried to:
•	Summarize analyst recommendations for NVIDIA (NVDA).
•	Provide the latest news about NVIDIA.
Process:
•	The Finance AI Agent fetches analyst recommendations and other stock-related data.
•	The Web Search Agent gathers the latest news for NVIDIA.
•	The results are synthesized into a cohesive response by the multi-agent system.
Streaming Output: stream=True ensures that the response is generated and displayed incrementally.


Explanation of Agent Collaboration
1.	Task Delegation:
o	The Finance Agent handles financial data tasks, leveraging YFinanceTools.
o	The Web Search Agent addresses general web-based information requests using DuckDuckGo.
2.	Response Aggregation:
o	The multi-agent model aggregates insights from the two sub-agents.
o	It adheres to unified instructions (e.g., providing sources and formatting data in tables).
3.	Advantages:
o	Modular and specialized agents enable efficient task handling.
o	Unified processing ensures consistency and clarity in responses
