# Agency Swarm

## Overview

The Agency Swarm package is a sophisticated framework designed for orchestrating a network of AI agents and user interactions within an application. This package includes several classes like `Agency`, `Agent`, `Thread`, `User`, and various tools, each playing a unique role in managing AI agents and their interactions.

## Key Components

### 1. [Agency Class](agency/README.md)
- **Purpose**: Manages a network of AI agents.
- **Key Features**:
  - Agent and Thread management.
  - Implementation of shared instructions.
  - Dynamic creation of communication tools.
  - Gradio interface and CLI demo capabilities.
- **Usage**: Initialize with an agency chart and shared instructions.

### 2. [Agent Class](agents/README.md)
- **Purpose**: Represents individual AI agents within the agency.
- **Key Features**:
  - Unique identification and descriptions.
  - Assignment of specific tools and instructions.
  - Integration with OpenAI’s API.
- **Usage**: Extend this class to create specific agents with customized functionalities.

### 3. [Thread Class](thread/README.md)
- **Purpose**: Manages conversations between an agent or user and a recipient agent.
- **Key Features**:
  - Message handling and tool execution within a thread.
  - Lifecycle management of conversation runs.
- **Usage**: Instantiate with an agent or user and a recipient agent to manage conversation flows.

### 4. [User Class](user/README.md)
- **Purpose**: Represents a user in the system.
- **Key Features**:
  - Currently focused on the user’s name.
  - Scalable for future enhancements.
- **Usage**: Instantiate to represent a user, with potential for future attribute expansion.

### 5. [Tools](tools/README.md) and [Utilities](util/README.md)
- **BaseTool Class**: Serves as an abstract base class for creating tools.
- **CodeInterpreter and Retrieval Classes**: Simple models for specific types of operations.
- **MessageOutput Class**: Manages and formats messages in the system.
- **OpenAI Client Management Functions**: Facilitates thread-safe access and dynamic setting of OpenAI API keys.

## Usage

1. **Setting Up Agency**:
   - Define an agency chart outlining agent relationships.
   - Initialize the `Agency` class with this chart and shared instructions.

2. **Creating Agents**:
   - Extend the `Agent` class to create custom agents.
   - Assign tools and specific instructions to each agent.

3. **Managing Conversations**:
   - Use the `Thread` class to handle message exchanges and tool executions between agents or between a user and an agent.

4. **Interacting as a User**:
   - Create instances of the `User` class to represent users in the system.

5. **Utilizing Tools**:
   - Create specific tools by extending the `BaseTool` class.
   - Use `CodeInterpreter` and `Retrieval` classes for specialized operations.

## Requirements

- Python 3.x
- `pydantic` for data validation and schema definition.
- `termcolor`, `enum`, `uuid`, `inspect`, `os` Python modules.
- `gradio` for interactive web demos (optional).
- OpenAI Python package and API key for integration with OpenAI services.

## Note

This package is part of a larger framework and is intended for users familiar with AI agents and OpenAI API integration. The package is designed to be flexible and scalable to accommodate various functionalities within an AI-driven application.

