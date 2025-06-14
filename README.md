# PythonAIAgentFromScratch

An AI-powered research assistant that combines web search and Wikipedia to gather, structure, and save information on any topic.

Quick Start ----------------------------------------------------------------------------------------------

1. Prerequisites

   - Python 3.8 or higher
   - An Anthropic API key (for Claude) or OpenAI API key (for GPT-4)
   - You need to register your CC or debit card with Antrhopic or OpenAI before you cna use the AI Agent

2. Setup

   # Create and activate virtual environment

   - python3 -m venv venv
   - source venv/bin/activate # On Windows use: venv\Scripts\activate

   # Install dependencies

   - pip install -r requirements.txt

   # Set up your API key

   # Create a .env file and add your API key:

   # ANTHROPIC_API_KEY="your_key_here"

   # or

   # OPENAI_API_KEY="your_key_here"

3. Run the Agent
   python main.py

How It Works ----------------------------------------------------------------------------------------------
System Architecture:

The system consists of three main components:

1. Large Language Model
   - Claude 3.5 Sonnet (Anthropic)
   - GPT-4 (OpenAI)
2. AI Agents Research Tools
   - Search Tool: Web search using DuckDuckGo
   - Wikipedia Tool: Information retrieval from Wikipedia
   - Save Tool: Persistent storage of research results
3. Output Structure
   ```python
   class ResearchResponse:
       topic: str
       summary: str
       sources: list[str]
       tools_used: list[str]
   ```

Workflow:

1. User inputs a research query
2. Agent receives query and starts the research process
3. Agent uses available tools to gather information:
   - Search Tool: Uses DuckDuckGo for web searches
   - Wikipedia Tool: Fetches information from Wikipedia with controlled output length
   - Save Tool: Saves research results to a text file with timestamps
4. Agent structures the information according to ResearchResponse format
5. Agent saves the results using the save tool
6. Results are displayed to user and saved to file

Key Features:

- Structured Output: Ensures consistent, well-formatted research results
- Multiple Sources: Combines web search and Wikipedia for comprehensive research
- Research Storage: Automatically saves research results with timestamps
- Error Handling: Gracefully handles parsing errors and displays raw response if needed
- Extensible: Easy to add new tools or modify existing ones

Technical Implementation:

- Uses environment variables for API keys (via dotenv)
- Implements async-compatible tools
- Uses Pydantic for data validation
- Follows LangChain's agent architecture for tool usage

System is useful for:

- Automated research tasks
- Structured information gathering
- Persistent storage of research results
- Combining multiple information sources
- Maintaining consistent output format
