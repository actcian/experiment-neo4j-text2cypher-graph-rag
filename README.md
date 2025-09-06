# Neo4j GraphRAG & Text2Cypher Experiment

This project demonstrates the use of Neo4j's GraphRAG Python library for knowledge graph-based retrieval augmented generation and natural language to Cypher query conversion.

## Features

- **GraphRAG**: Vector-based similarity search using Neo4j and OpenAI embeddings
- **Text2Cypher**: Natural language to Cypher query conversion using LLMs
- **Schema Introspection**: Automatic database schema exploration and adaptation
- **Docker Integration**: Easy Neo4j setup with Docker Compose

## Prerequisites

- Python 3.9+
- Neo4j 5.18.1+
- OpenAI API key
- Docker & Docker Compose

## Setup

1. **Clone and navigate to the project:**
   ```bash
   cd neo4j-graphRAG
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Create environment file:**
   ```bash
   cp .env.example .env
   ```
   
   Edit `.env` with your credentials:
   ```
   NEO4J_PASSWORD=your_neo4j_password
   OPENAI_API_KEY=your_openai_api_key
   ```

4. **Start Neo4j database:**
   ```bash
   docker-compose up -d
   ```

5. **Access Neo4j Browser:**
   - URL: http://localhost:7474
   - Username: `neo4j`
   - Password: (from your `.env` file)

## Usage

Open `graph-rag.ipynb` in Jupyter and run the cells to:

1. **Initialize connections** to Neo4j and OpenAI
2. **Test database connectivity**
3. **Explore GraphRAG capabilities:**
   ```python
   # Vector-based similarity search
   result = basic_rag_query("What is the main topic discussed?")
   ```

4. **Use Text2Cypher for natural language queries:**
   ```python
   # Convert natural language to Cypher
   result = text_to_cypher_query("Find all people who work at companies")
   ```

5. **Explore database schema:**
   ```python
   # Get current database structure
   get_database_schema()
   ```

## Project Structure

```
neo4j-graphRAG/
├── graph-rag.ipynb          # Main Jupyter notebook
├── requirements.txt         # Python dependencies
├── docker-compose.yml       # Neo4j container setup
├── .env.example            # Environment template
├── .env                    # Your credentials (create this)
└── README.md               # This file
```

## Key Components

### GraphRAG
- Uses OpenAI embeddings for semantic search
- Retrieves relevant information from knowledge graphs
- Combines graph data with LLM generation

### Text2Cypher
- Converts natural language to Cypher queries
- Auto-adapts to your database schema
- Provides example-driven query generation

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `NEO4J_URI` | Neo4j connection URI | `bolt://localhost:7687` |
| `NEO4J_USERNAME` | Neo4j username | `neo4j` |
| `NEO4J_PASSWORD` | Neo4j password | Required |
| `OPENAI_API_KEY` | OpenAI API key | Required |

## Resources

- [Neo4j GraphRAG Python Documentation](https://neo4j.com/docs/neo4j-graphrag-python/current/)
- [Neo4j GraphRAG API Reference](https://neo4j.com/docs/neo4j-graphrag-python/current/api.html)
- [Neo4j Documentation](https://neo4j.com/docs/)
