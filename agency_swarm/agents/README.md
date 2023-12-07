# Agent

## Overview

The `Agent` class in this code is designed to create and manage an AI assistant using the OpenAI API. It includes functionalities such as initializing and updating the assistant, managing tools, and handling files and instructions.

## Features

- **Assistant Initialization and Management**: Initialize and update an AI assistant with custom settings.
- **Tool Integration**: Add and manage different types of tools (`BaseTool`, `Retrieval`, `CodeInterpreter`).
- **File Handling**: Upload and manage files associated with the assistant.
- **Instructions Management**: Read and update instructions from a file or string.

## Class Methods

- `__init__`: Initialize the agent with id, name, description, tools, etc.
- `init_oai`: Initialize or retrieve the OpenAI assistant.
- `_update_assistant`: Update the assistant’s parameters.
- `_check_parameters`: Check if the current parameters match the assistant’s settings.
- `_save_settings`, `_update_settings`: Manage settings in a local JSON file.
- `_read_instructions`: Read instructions from a file.
- `_upload_files`: Upload files to the assistant.
- `_add_id_to_file`, `_get_id_from_file`: Manage file IDs.
- `get_settings_path`, `get_class_folder_path`: Utility functions for path management.
- `set_params`: Set parameters of the agent dynamically.
- `add_tool`: Add a tool to the agent’s toolset.
- `add_instructions`: Add instructions to the agent.
- `get_oai_tools`: Retrieve tools formatted for OpenAI schema.
- `delete_assistant`: Delete the assistant and its settings.

## Usage

To use the `Agent` class, you need to create an instance with the required parameters (id, name, description, etc.). Then, initialize the OpenAI assistant using `init_oai`. You can add tools, manage files, and set instructions as needed.

## Requirements

- Python 3.x
- `deepdiff` library
- `agency_swarm` package
- OpenAI API key and client setup

## Example

```python
from agency_swarm import Agent

# Create an agent instance
my_agent = Agent(name=“MyAgent”, description=“This is a test agent.”)

# Initialize OpenAI assistant
my_agent.init_oai()

# Add tools and manage settings as required
```

## Note

This README assumes familiarity with the OpenAI API and the custom `agency_swarm` package. It’s important to handle API keys and client information securely.

