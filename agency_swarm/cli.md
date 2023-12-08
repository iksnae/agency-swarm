# Create Agent Template CLI

## Overview

The provided Python script defines a command-line interface (CLI) for creating an agent template in the `agency_swarm` framework. This CLI uses the `argparse` library to parse command-line arguments and invoke the `create_agent_template` function with the specified options.

## Script Components

### 1. Argument Parser Setup

- **Parser**: An `argparse.ArgumentParser` is initialized with a description indicating its purpose for creating agent templates.

- **Subparsers**: The script uses subparsers to manage different commands. Currently, it supports the 'create-agent-template' command.

### 2. 'create-agent-template' Command

- **Subparser**: A subparser is created for the 'create-agent-template' command.
- **Arguments**:
  - `--path`: The path where the agent folder will be created. Default is the current directory (`"./"`).
  - `--use_txt`: A flag to indicate using `.txt` files instead of `.md` for instructions and manifesto.
  - `--name`: The name of the agent.
  - `--description`: A description of the agent.

### 3. Main Function

- **Functionality**: Parses command-line arguments and, if the 'create-agent-template' command is specified, invokes the `create_agent_template` function with the provided arguments.

## Usage

To use the CLI, navigate to the directory containing this script and run it with the appropriate arguments. For example:

```bash
python script_name.py create-agent-template --name "Example Agent" --description "An agent for data processing" --path "./agents"
```

This command will create a new agent template named "Example Agent" with the provided description in the `./agents` directory.

## Implementation Notes

- The script is designed to be user-friendly, providing help messages and default values for some arguments.
- It is extensible, allowing for the addition of more subcommands in the future.
- The use of subparsers enables organized and structured handling of different commands and their respective options.
