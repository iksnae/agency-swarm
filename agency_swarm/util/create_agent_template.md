# `create_agent_template`

## Overview

The `create_agent_template` function is a utility designed to automate the setup process for a new agent within the `agency_swarm` framework. This function creates a structured directory with necessary files for an agent, ensuring consistency and standardization in the development process.

## Function Definition

### `create_agent_template`

- **Purpose**: To create a new agent template with predefined structure and files.
- **Parameters**:
  - `agent_name` (optional): The name of the agent.
  - `agent_description` (optional): A description of the agent.
  - `path` (optional): The directory path where the agent folder will be created.
  - `use_txt` (optional): Boolean flag to use `.txt` files instead of `.md` for documentation.

- **Functionality**:
  1. **Agent Name and Description Input**: Prompts for the agent's name and description if not provided.
  2. **Agency Manifesto Creation**: Checks for an existing agency manifesto file and creates one if it doesn't exist.
  3. **Agent Folder Creation**: Generates a folder named after the agent.
  4. **File Generation**:
     - Creates Python files for the agent and associated tools.
     - Generates initialization and instruction files.
     - Sets up a directory for additional files.

- **File Structure**:
  - `agent_name.py`: Main agent class file.
  - `__init__.py`: Initialization file for the agent module.
  - `instructions.md` or `instructions.txt`: Instructions specific to the agent.
  - `tools.py`: File for defining tools associated with the agent.
  - `files/`: A folder for additional files related to the agent.

- **Templates Used**:
  1. `agent_template`: Template for the agent class.
  2. `tools_template`: Template for defining tools associated with the agent.

## Example Usage

```python
create_agent_template("MyAgent", "This agent handles data processing.", "./agents", use_txt=False)
```

This will create a new agent named "MyAgent" with the provided description, in the `./agents` directory, using Markdown files for documentation.

## Implementation Notes

- The function handles directory and file creation, ensuring that necessary files are in place for the agent to function within the `agency_swarm` framework.
- It uses string formatting to inject specific agent details into the templates.
- The function raises an exception if the agent folder already exists to prevent overwriting.

