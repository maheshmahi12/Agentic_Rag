# Agentic_Rag - Meeting Insights with Vector Search and AI Agents

In this project, I’ve built a system that combines vector search and AI agents to extract insights from meeting recordings. The system integrates **Qdrant** for vector search, **CrewAI** for AI agent coordination, and **Anthropic Claude** for natural language understanding and response generation. The goal is to allow users to search through their meeting data and receive valuable insights.

## What I’ve Built

This system does the following:
1. Uses **Qdrant** to store and retrieve meeting transcripts as vector embeddings.
2. Leverages **CrewAI agents** to analyze and summarize meeting data.
3. Presents insights via a simple **Streamlit interface** for easy interaction.

### Key Features
- **Vector Search**: The system stores meeting transcripts as vector embeddings and uses Qdrant to enable semantic search.
- **AI-Powered Agents**: I’ve implemented CrewAI agents to analyze meeting data and generate insights.
- **Natural Language Responses**: Anthropic Claude is used to provide natural language understanding and generate human-readable insights.
- **Real-Time Interaction**: A Streamlit interface is built to allow users to interact with the system in a chat-like format.

## Architecture

The system consists of three core components:
1. **Qdrant Vector Database**:
   - Stores meeting transcripts and summaries as vector embeddings.
   - Allows semantic search of meeting content.
2. **CrewAI Framework**:
   - Coordinates various AI agents that handle specific tasks like searching the Qdrant database and processing queries.
3. **Anthropic Claude**:
   - Generates human-like responses based on the insights extracted from the vector database.

### Data Processing Pipeline
1. **Meeting Transcripts**: Transcripts are converted into vector embeddings using `SentenceTransformer`.
2. **Qdrant Management**: I manage the Qdrant collection to store and query the embeddings.
3. **AI Agent Logic**: CrewAI agents process user queries, search the database, and synthesize responses.
4. **Synthesis**: The system uses Claude to convert the analysis into a natural language response.

### User Interface
- The interface is a **chat-like web application** where users can query the system and receive responses in real-time.

## Getting Started

### Prerequisites
1. **Qdrant API Credentials**:
   - I created an account at Qdrant and set up a new cluster.
   - I copied the **Cluster URL** and generated an **API key** from the **Data Access Control** section.

2. **AI Services API Credentials**:
   - I obtained an API key from **Anthropic** [here](https://www.anthropic.com/).
   - I also got an API key from **OpenAI** to use their services if needed.

### Setup Instructions

#### 1. **Create and Activate Virtual Environment**:
   - I created a virtual environment using:
     ```bash
     python -m venv venv
     ```
   - Then activated it:
     - For Windows:
       ```bash
       .\venv\Scripts\activate
       ```
     - For macOS/Linux:
       ```bash
       source venv/bin/activate
       ```

#### 2. **Install Required Libraries**:
   - I installed the dependencies by running:
     ```bash
     pip install -r requirements.txt
     ```

#### 3. **Configure API Keys**:
   - I set the API keys for **Qdrant**, **Anthropic**, and **OpenAI** as environment variables:
     - For Windows:
       ```bash
       set QDRANT_API_KEY=your_qdrant_api_key
       set ANTHROPIC_API_KEY=your_anthropic_api_key
       set OPENAI_API_KEY=your_openai_api_key
       ```
     - For macOS/Linux:
       ```bash
       export QDRANT_API_KEY=your_qdrant_api_key
       export ANTHROPIC_API_KEY=your_anthropic_api_key
       export OPENAI_API_KEY=your_openai_api_key
       ```

#### 4. **Run the Streamlit App**:
   - Finally, I ran the Streamlit interface to start interacting with the system:
     ```bash
     streamlit run your_app.py
     ```
