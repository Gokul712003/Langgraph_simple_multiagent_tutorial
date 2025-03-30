# Multi-Agent Langgraph Tutorial

## Overview
This repository contains a beginner-friendly tutorial demonstrating how to build a multi-agent system using LangGraph and LangChain. The notebook `multi_agent_test.ipynb` shows how to create a hierarchical structure of agents that collaborate to solve arithmetic problems.

## Architecture
The system consists of:

1. **Specialized Agent Tools**: Three agents dedicated to specific arithmetic operations:
   - `add_agent`: performs addition
   - `subtract_agent`: performs subtraction
   - `multiply_agent`: performs in multiplication

2. **Supervisor Agent**: A high-level agent that:
   - Interprets user queries
   - Decides which specialized agent to use
   - Orchestrates the workflow between agents
   - Assembles the final answer

3. **LangGraph Implementation**: The agents are integrated into a simple graph structure for execution flow.

## How It Works
1. User inputs a mathematical expression (e.g., "add 2 and 3 and multiply the result by 4")
2. The supervisor agent parses this request
3. The supervisor delegates tasks to the appropriate specialized agents
4. Each specialized agent performs its calculation
5. Results are combined to produce the final answer

## Key Components
- **Agent Creation**: Using `create_react_agent` with specific tools and prompts
- **Tool Integration**: Converting agents into tools for the supervisor
- **Graph Structure**: Simple implementation with `StateGraph`
- **Message Passing**: Communication between agents via LangChain message objects

## Sample Queries
The notebook demonstrates several examples:
- Basic arithmetic: "add 2 and 3 and multiply the result by 4"
- Multi-step calculations: "add 2 and 3 and multiply the result by 10 and multiply it by -10"
- Mixed operations: "add 2 and 3 and subtract the result by 10 and multiply it by -10"

## Requirements
- Python 3.x
- LangChain
- LangGraph
- Google Generative AI API access (for Gemini-2.0-flash model)
- Python dotenv for environment variables

## Getting Started
1. Clone this repository
2. Set up your environment variables in a `.env` file (including API key for Google Generative AI)
3. Open and run `multi_agent_test.ipynb` to see the multi-agent system in action


## NOTE
This notebook serves as an educational resource for understanding how to build hierarchical multi-agent systems with specialized capabilities and task delegation.
