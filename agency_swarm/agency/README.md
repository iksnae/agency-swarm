# Agency 

## Overview

The `Agency` class orchestrates a network of AI agents (`Agent` objects) within an application, facilitating their interaction and collaboration. It is designed to manage agents, their communication, and the overall flow of activities in a complex system.

## Features

- **Agent Management**: Create and manage multiple `Agent` instances, including a CEO agent.
- **Thread Management**: Facilitate communication between agents through `Thread` instances.
- **Shared Instructions**: Apply shared instructions across all agents.
- **Dynamic Tool Creation**: Generates messaging tools dynamically for agent communication.
- **Demo Interfaces**: Implement demonstration interfaces using Gradio or a command-line interface.

## Class Methods

- `__init__`: Initializes the agency with an agency chart and shared instructions.
- `get_completion`: Retrieves message completion from the main thread.
- `demo_gradio`: Launches a Gradio-based chat interface for demonstration purposes.
- `run_demo`: Runs a command-line based demonstration.
- `_parse_agency_chart`: Parses the agency chart to set up agent hierarchies and relationships.
- `_add_agent`: Adds an agent to the agency.
- `get_agent_by_name`, `get_agents_by_names`: Retrieves agents by name.
- `get_agent_ids`, `get_agent_names`: Returns lists of agent IDs and names.
- `_read_instructions`: Reads shared instructions from a file.
- `plot_agency_chart`: (Placeholder method, currently not implemented.)
- `_create_send_message_tools`, `_create_send_message_tool`: Creates tools for sending messages between agents.
- `get_recipient_names`: Retrieves current valid recipient agent names.
- `_init_agents`, `_init_threads`: Initializes agents and threads.
- `get_class_folder_path`: Utility method to get the class folder path.

## Usage

To use the `Agency` class, define an agency chart which outlines the hierarchy and relationships between different agents. Initialize the `Agency` with this chart and any shared instructions. Agents and threads are automatically set up based on the agency chart.

## Example

```python
from agency_swarm.agents import Agent
from agency_swarm.agency import Agency

# Define your agents and agency chart
agent1 = Agent(name=“Agent1”)
agent2 = Agent(name=“Agent2”)
agency_chart = [agent1, [agent2]]

# Initialize the agency
my_agency = Agency(agency_chart=agency_chart)

# Use the agency’s functionalities as needed
```

## Requirements

- Python 3.x
- `pydantic` library
- `agency_swarm` package
- Gradio library for demo interface (optional)

## Note

This README assumes familiarity with the `agency_swarm` package and its dependencies. The actual implementation of methods like `plot_agency_chart` might require further development.
