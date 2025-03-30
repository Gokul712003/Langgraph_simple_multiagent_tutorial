# Multi-Agent Calculator Tutorial

## Overview
This repository contains beginner-friendly tutorials demonstrating how to build multi-agent systems using LangGraph and LangChain. The notebooks showcase how to create different architectures of agents that collaborate to solve arithmetic problems.

## Notebooks

### 1. `multi_agent_test.ipynb`

A tutorial showing how to build a hierarchical multi-agent system with a supervisor agent and specialized worker agents.

#### Architecture
- **Specialized Agent Tools**: Three agents dedicated to specific arithmetic operations:
  - `add_agent`: Specialized in addition
  - `subtract_agent`: Specialized in subtraction
  - `multiply_agent`: Specialized in multiplication

- **Supervisor Agent**: A high-level agent that:
  - Interprets user queries
  - Decides which specialized agent to use
  - Orchestrates the workflow between agents
  - Assembles the final answer

#### How It Works
1. User inputs a mathematical expression
2. The supervisor agent parses this request
3. The supervisor delegates tasks to the appropriate specialized agents
4. Each specialized agent performs its calculation
5. Results are combined to produce the final answer

### 2. `multi_tool_node.ipynb`

A more advanced tutorial implementing an **asynchronous** workflow using ToolNodes for arithmetic operations.

#### Architecture
- **ToolNode Integration**: Uses the `ToolNode` class to wrap calculator functions
- **Asynchronous Processing**: Implements `async`/`await` pattern for non-blocking operations
- **Conditional Workflow**: Uses conditional edges to determine whether to continue processing or end

#### Key Components
- **StateGraph with TypedDict**: Uses a more structured state management approach
- **Conditional Branching**: Dynamic decision making with `should_continue` function
- **Tool Binding**: Direct binding of tools to the LLM for streamlined processing

#### How It Works
1. User inputs multiple arithmetic expressions
2. The model processes the input and identifies tool calls needed
3. The ToolNode handles the arithmetic operations asynchronously
4. Processing continues until no more tool calls are detected
5. The final response contains all calculated answers

## Common Features

- **Agent Creation**: Using `create_react_agent` and `ToolNode` with specific tools and prompts
- **Tool Integration**: Converting agents into tools for delegation
- **Graph Structure**: Implementation with `StateGraph`
- **Message Passing**: Communication between components via LangChain message objects

## Sample Queries
The notebooks demonstrate several examples:
- Basic arithmetic expressions
- Multi-step calculations 
- Multiple operations in a single query

## Requirements
- Python 3.x
- LangChain
- LangGraph
- Google Generative AI API access (for Gemini-2.0-flash model)
- Python dotenv for environment variables

## Getting Started
1. Clone this repository
2. Set up your environment variables in a `.env` file (including API key for Google Generative AI)
3. Open and run the notebooks to see the multi-agent systems in action

These notebooks serve as educational resources for understanding how to build different types of agent-based systems for computational tasks.
