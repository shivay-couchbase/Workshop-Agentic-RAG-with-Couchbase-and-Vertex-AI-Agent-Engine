# Agentic RAG with Couchbase and Vertex AI Agent Engine Workshop

Build production-ready AI agents using **Vertex AI Agent Engine** and **Couchbase Capella** for advanced Retrieval-Augmented Generation (RAG) applications.

 [![Open In Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/shivay-couchbase/Workshop-Agentic-RAG-with-Couchbase-and-Vertex-AI-Agent-Engine/blob/main/agentic_rag_with_couchbase_and_vertex_ai_agent_engine.ipynb)


## Workshop Overview

This hands-on workshop demonstrates how to build and deploy intelligent AI agents that can:

* Research Star Wars topics using vector search
* Generate well-structured blog posts from research data
* Chain tools automatically based on user requests

### What You'll Build

An intelligent multi-agent system that:

1. Scrapes and processes content from Wikipedia
2. Stores vector embeddings in Couchbase for semantic search
3. Creates two specialized tools: research and blog writing
4. Chains tools intelligently based on user intent
5. Deploy to Vertex AI Agent Engine

---

## Learning Objectives

By the end of this workshop, you'll be able to:

* Set up Couchbase Capella for vector storage and search
* Create vector embeddings using Vertex AI models
* Build specialized tools for RAG applications
* Implement tool chaining for complex workflows
* Deploy AI agents to production using Vertex AI Agent Engine
* Test and iterate on deployed agents

---

## Prerequisites

### Required Accounts & Services

1. **Google Cloud Project** with:

   * Vertex AI API enabled
   * Cloud Storage bucket created
   * Billing enabled
   * Required IAM permissions

2. **Couchbase Capella Cluster**:

   * Free cluster in your preferred Google Cloud region
   * [Create account here](https://cloud.couchbase.com/sign-up)

### Technical Requirements

* Python 3.8+ with pip
* Jupyter Notebook or Google Colab
* Basic knowledge of:

  * Python programming
  * REST APIs
  * Vector databases (helpful but not required)

### Setup Instructions

1. Clone or download this workshop repository
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```
3. Set up environment variables (see Configuration section below)

---

## Workshop Structure

### Files in This Repository

```
agentic-rag-workshop/
├── agentic_rag_with_couchbase_and_vertex_ai_agent_engine.ipynb  # Main workshop notebook
├── index.json                                                   # Vector search index definition
├── requirements.txt                                             # Python dependencies
├── README.md                                                    # This file
└── .env.example                                                 # Environment variables template
```

## Configuration

### Environment Variables

Create a `.env` file in the project root:

```bash
# Couchbase Configuration
CB_HOST=couchbases://your-cluster-url
CB_USERNAME=your-username
CB_PASSWORD=your-password
CB_BUCKET_NAME=gemini
INDEX_NAME=vector_search_gemini
SCOPE_NAME=_default
COLLECTION_NAME=_default

# Google Cloud Configuration  
PROJECT_ID=your-project-id
LOCATION=us-central1
STAGING_BUCKET=gs://your-bucket-name
```

### Google Cloud Setup

1. Enable required APIs:

   ```bash
   gcloud services enable aiplatform.googleapis.com
   gcloud services enable storage.googleapis.com
   gcloud services enable cloudbuild.googleapis.com
   ```

2. Set up authentication:

   ```bash
   gcloud auth application-default login
   ```

3. Create storage bucket:

   ```bash
   gsutil mb gs://your-bucket-name
   ```

### Couchbase Capella Setup

1. Create a free cluster in Google Cloud region
2. Create a bucket named `gemini` (or update environment variables)
3. Set up database credentials (username/password)
4. Allow network access for your IP address

---

## Key Technologies

### AI & ML

* Vertex AI Agent Engine: Managed agent deployment platform
* Gemini 2.5 Pro: Large language model for text generation
* text-embedding-005: Vector embedding model
* LangChain: Agent framework and tool orchestration

### Data & Storage

* Couchbase Capella: NoSQL database with vector search
* Vector Search: Semantic similarity search capabilities
* Google Cloud Storage: Model artifacts and staging

## Getting Started

### Quick Start (5 minutes)

1. Open the notebook:

   ```bash
   jupyter notebook agentic_rag_with_couchbase_and_vertex_ai_agent_engine.ipynb
   ```

2. Follow the cells sequentially - each section builds on the previous

3. Update configuration in the first few cells with your credentials

4. Run each cell and observe the outputs

---

## What You'll Experience

### Real-World Scenarios

1. Information Research: Query Star Wars universe knowledge

   ```
   "Tell me about the Death Star's construction"
   ```

2. Content Generation: Create blog posts from research

   ```
   "Write a blog post about Darth Vader's transformation"
   ```

3. Tool Chaining: Automatic workflow execution

   ```
   User Request → Research Tool → Blog Writing Tool → Final Output
   ```

### Expected Outputs

* Functional vector search on Star Wars content
* AI agent that researches and writes blogs
* Production deployment on Google Cloud Vertex AI Engine

---

## Troubleshooting

### Common Issues

| Issue                      | Solution                                            |
| -------------------------- | --------------------------------------------------- |
| Couchbase connection fails | Check credentials, network access, cluster status   |
| Vector search not working  | Verify index creation, wait for indexing completion |
| Deployment errors          | Check Google Cloud permissions, API enablement      |
| Tool chaining not working  | Review system instructions, test tools individually |

---

## Next Steps

### After the Workshop

1. Extend the agent with additional tools
2. Add different data sources beyond Wikipedia
3. Implement custom embedding models
4. Monitor and optimize performance

### Advanced Topics to Explore

* Multi-turn conversations with memory persistence
* Multi-modal agents with image and text
* Analytics and monitoring for production agents
* Security best practices for enterprise deployment


