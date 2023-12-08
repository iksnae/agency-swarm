# Thread

## Overview

The `Thread` class is designed to handle communication and task execution between agents in an 'agency_swarm' environment. It manages the interaction between agents (or users), executes tools as required by the conversation, and handles message sending and receiving.

## Dependencies

- `inspect`: Used for introspection of Python objects.
- `time`: For handling time-related tasks, such as sleeping between checks for message completion.
- `typing`: Provides the `Literal` type for type hinting.
- `agency_swarm.agents`, `agency_swarm.messages`, `agency_swarm.user`, `agency_swarm.util.oai`: These modules are part of the 'agency_swarm' package and are used to manage agents, messages, users, and OpenAI client interactions.

## Class Definition

### `Thread`

The `Thread` class handles a communication thread between an agent and a recipient agent.

#### Attributes

- `id`: Identifier for the thread.
- `thread`: Holds the thread instance.
- `run`: Stores the current run instance.

#### Methods

1. `__init__(self, agent: Literal[Agent, User], recipient_agent: Agent)`:
   - Initializes a new `Thread` instance.
   - **Parameters**:
     - `agent`: The initiating agent or user.
     - `recipient_agent`: The recipient agent.

2. `get_completion(self, message: str, yield_messages=True)`:
   - Handles message sending, tool execution, and response retrieval within the thread.
   - **Parameters**:
     - `message`: The message to be sent.
     - `yield_messages`: Whether to yield `MessageOutput` objects during execution.
   - **Returns**: The final message from the assistant or an error message.

3. `_execute_tool(self, tool_call)`:
   - Executes a specified tool and returns its output.
   - **Parameters**:
     - `tool_call`: Information about the tool to be executed.
   - **Returns**: The output of the tool or an error message.

## Usage

The `Thread` class is used in scenarios where an agent needs to interact with another agent, send messages, and execute tools based on the conversation's context. It manages the lifecycle of a thread, including message sending, waiting for responses, handling tool execution, and dealing with errors.

## Implementation Notes

- The class heavily relies on the OpenAI client and the structures defined in the `agency_swarm` package.
- It uses generators to yield `MessageOutput` objects, allowing for real-time updates during the thread's execution.
- Error handling includes raising exceptions on run failures and tool execution errors.
- The class assumes certain methods and attributes in the `Agent` class, such as `functions`.
