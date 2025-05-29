# Project Name

**GraphAugment: Graph-Based Retrieval-Augmented Generation Systems**

---

## Project Description

GraphAugment explores advanced implementations of Retrieval-Augmented Generation (RAG) systems by integrating knowledge graphs to enhance generative AI. This project analyzes and compares two sophisticated RAG approaches: **GraphRAG** (developed by Microsoft Research) and **LightRAG** (developed by the University of Hong Kong).

GraphRAG utilizes detailed knowledge graphs to deeply understand complex entity relationships, providing comprehensive and contextually rich responses. LightRAG, optimized for speed and efficiency, leverages simplified graph structures and hybrid retrieval methods to deliver swift, relevant responses ideal for real-time applications.

The project demonstrates setups, conducts comparative experiments using various datasets, evaluates performance metrics such as indexing time, API efficiency, and output quality, and offers insights into their optimal use cases.

---

## Features

* **GraphRAG**: Deep, detailed retrieval and generation with comprehensive context handling.
* **LightRAG**: Rapid, efficient responses optimized for speed with streamlined knowledge graph updates.
* **API Interaction**: RESTful API endpoints for query operations, data insertion, and health checks.
* **Hybrid Retrieval**: Combines text-based and graph-based retrieval methods.

---

## Project Structure

```
GraphAugment/
├── GraphRAG/
│   ├── prompts/
│   ├── logs/
│   ├── input/
│   └── output/
├── LightRAG/
│   ├── api_server/
│   ├── scripts/
│   └── data/
├── datasets/
├── experiments/
├── README.md
└── requirements.txt
```

---

## Setup Instructions

### GraphRAG

1. Install Python 3.8+
2. Install dependencies:

```bash
pip install graphrag
```

3. Initialize and configure the project:

```bash
graphrag init --root ./ragtet
```

4. Run indexing:

```bash
graphrag index --root ./ragtet
```

### LightRAG

1. Install Python 3.10+
2. Set up environment:

```bash
conda create --name lightrag_env python=3.10 -y
conda activate lightrag_env
pip install fastapi uvicorn pydantic lightrag
```

3. Run API server:

```bash
chmod +x set_env.sh
./set_env.sh
python examples/lightrag_api_openai_compatible_demo.py
```

---

## API Usage

* **Query**:

```bash
curl -X POST "http://127.0.0.1:8020/query" -H "Content-Type: application/json" -d '{"query": "Your question", "mode": "hybrid"}'
```

* **Insert Text**:

```bash
curl -X POST "http://127.0.0.1:8020/insert" -H "Content-Type: application/json" -d '{"text": "Document content"}'
```

* **Health Check**:

```bash
curl -X GET "http://127.0.0.1:8020/health"
```

---

## Comparative Analysis Highlights

| Feature          | GraphRAG                 | LightRAG                          |
| ---------------- | ------------------------ | --------------------------------- |
| Speed            | Moderate                 | High                              |
| Cost Efficiency  | Moderate                 | High                              |
| API Requests     | High                     | Low                               |
| Graph Complexity | High                     | Moderate                          |
| Use Case         | Deep contextual analysis | Real-time and efficient retrieval |

---

## Additional Enhancements

* **Visualizations**: Interactive visualizations of knowledge graphs.
* **Dockerization**: Containerize setups for easier deployment.
* **Benchmarking Tools**: Automated tools for performance testing.
* **Continuous Integration (CI/CD)**: Integration with GitHub Actions for automated tests and deployments.

---

## Contributing

Contributions are welcome! Please submit a pull request or open an issue to suggest improvements or report bugs.

---


---

## Acknowledgments

* Microsoft Research (GraphRAG)
* University of Hong Kong (LightRAG)

---
