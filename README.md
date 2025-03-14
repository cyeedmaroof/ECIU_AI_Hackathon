# ECIU_AI_Hackathon

This notebook demonstrates the construction and execution of a state graph for an interview and document retrieval process. The graph is built using the `StateGraph` class and involves several nodes and edges to manage the flow of the process.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Graph Nodes](#Define-nodes)
- [Graph Edges](#Define-edges)
- [Graph Compilation](#graph-compilation)
- [Visualization](#visualization)

## Installation

To run this notebook, you need to have the following dependencies installed:

- `IPython`
- `langchain`
- `pydantic`
- `PIL` (optional, for graph visualization)

You can install these dependencies using pip:

```sh
pip install ipython langchain pydantic pillow
```
# State Graph for ECIU AI Hackathon

## Usage
### Build the Graph
The graph is constructed using the `StateGraph` class. Nodes and edges are added to define the flow of the process.

### Define Nodes
Each node represents a specific step in the process:
- **greet**: Handles the initial greeting of the user.
- **judge_node**: (Commented out) Would handle the judging logic.
- **answer_interview**: Handles answering interview questions.
- **create_context**: Creates the context for document retrieval.
- **retrieve_documents**: Retrieves relevant documents based on the context.
- **rerank_documents**: Reranks the retrieved documents.
- **llm_answer**: Generates answers using a language model.
- **interview**: Handles the interview process.

### Define Edges
Edges define transitions between nodes. Conditional edges determine the next step based on the output of the current node.

- `START -> greet`: The process starts with the greeting node.
- `greet -> judge_node`: Conditional edges determine whether to proceed to the interview or document retrieval based on the output of the greeting node.
- `interview -> answer_interview`: Transition from the interview node to the answer interview node.
- `answer_interview -> create_context`: Transition from the answer interview node to the create context node.
- `create_context -> retrieve_documents`: Transition from the create context node to the retrieve documents node.
- `retrieve_documents -> rerank_documents`: Transition from the retrieve documents node to the rerank documents node.
- `rerank_documents -> llm_answer`: Transition from the rerank documents node to the LLM answer node.
- `llm_answer -> END`: The process ends after generating the answer using the LLM.

## Graph Compilation
The graph is compiled using the `compile` method of the `StateGraph` class.

## Visualization
The graph can be visualized using the `draw_mermaid_png` method from the `IPython.display` module.

## Conclusion
This document demonstrates the construction and execution of a state graph for an interview and document retrieval process. The graph is built using the `StateGraph` class and involves several nodes and edges to manage the flow of the process. The graph can be visualized using the `draw_mermaid_png` method from the `IPython.display` module.

