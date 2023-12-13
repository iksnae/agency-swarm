# MessageOutput Class

## Overview

The `MessageOutput` class in the Agency Swarm framework is responsible for the formatting and display of messages within the system, representing the communication between agents and users.

## Initialization Parameters

The class is initialized with the following parameters:

- `msg_type`: Indicates the message type (e.g., "function", "function_output", "text", "system").
- `sender_name`: Name of the message sender.
- `receiver_name`: Name of the message receiver.
- `content`: Content of the message.

## Attributes

- Manages message type, sender and receiver identity, and content for presentation and logging purposes.

## Methods

- `hash_names_to_color`: Determines the color used for printing based on a hash of the sender and receiver names or message type.
- `cprint`: Prints the formatted message content to the console in the assigned color.
- `get_formatted_content`: Provides the formatted message content, including sender and receiver information.
- `get_sender_emoji`: Assigns an emoji to the sender based on the hash of the name or message type.

## Integration with Agency Swarm

- `MessageOutput` complements the `Thread` class by improving message readability during interactions.
- It is used to format and visually distinguish messages of different types and origins, enhancing user understanding of system interactions.

## Usage Example

```python
from agency_swarm.messages import MessageOutput

# Creating a message output for a function executed by an agent
function_message = MessageOutput(
    msg_type='function',
    sender_name='Agent',
    receiver_name='API',
    content='Running data analysis...'
)

# Using cprint to display the message
function_message.cprint()
```

In this example, `MessageOutput` is used to format and display a message that indicates the execution of a function within the framework. Its methods support visualization of interactions, aiding developers and users in monitoring the flow of communication.

## Conclusion

With its focus on message formatting and ease of display, the `MessageOutput` class significantly contributes to the operability and user-friendliness of the Agency Swarm framework, allowing for clear and structured presentation of interaction logs.
