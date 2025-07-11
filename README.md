HealthBot: Nutrition QA Agent with Judgeval Evaluation
This repository contains the implementation of HealthBot, a clinical nutrition question-answering agent. The agent integrates retrieval from a Graphiti knowledge graph with a large language model for response generation and is evaluated using Judgeval for faithfulness, correctness, and instruction adherence.

Overview ->
Language: Python 3.11.8

Frameworks: LangGraph, LangChain, Graphiti, Judgeval

Features:
1) Retrieves nutritional facts using Graphiti’s search client
2) Generates professional clinical nutrition responses
3) Evaluates outputs using Judgeval scorers for automated benchmarking and unit testing

Folder structure:
.
├── judegval-graphiti-agent.ipynb   #Main notebook with agent code, evaluation, and tests
├── USDA-Food-Dataset #Folder containing USDA data for generating Knowledge Graph Triplets
├── NutriBench.csv #Benchmark dataset for evalution
└── README.md

Setup Instructions:
Clone the repository:
- git clone https://github.com/vlds18/USDA-Knowledge-Graph-Agent-Graphiti.git
- cd USDA-Knowledge-Graph-Agent-Graphiti

Create a virtual environment and activate it:
- python3 -m venv venv
- source venv/bin/activate

Set up environment variables for Judgeval and Graphiti:
- JUDGMENT_API_KEY="your_judgment_api_key"
- JUDGMENT_ORG_ID="your_judgment_org_id"
- OPENAI_API_KEY="your_openai_api_key"


The notebook implements an async chatbot(state) function that retrieves context from Graphiti and generates nutrition answers using a bound LLM.

Benchmark Evaluation:
It loads a subset of the NutriBench dataset, runs the agent over the inputs, and evaluates outputs using the AnswerCorrectnessScorer from Judgeval.

Unit Testing:
Includes unit tests using InstructionAdherenceScorer to validate instruction following capabilities of the agent.

