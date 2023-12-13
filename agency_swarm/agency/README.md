# Agency

## Purpose

The `Agency` class is pivotal to the Agency Swarm framework, representing a collective of `Agent` instances. It defines the behavior and collaborative efforts of the agent swarm, orchestrating their interactions and managing the flow of communication between them, which is critical to the system's functionality and coherence.

## Input and Output Specifications

- **agents** (List[Agent]): A list of `Agent` objects that are part of the Agency. Each agent should have a distinct role within the collective.
- **agency_chart** (List[Tuple[Agent, Agent]]): Defines communication pathways where each tuple indicates the direction of initiation possible between the two agents.
- **shared_instructions** (Optional[str]): Abstracted instructions that apply to all members of the agency collectively.

Outputs are typically the results of coordinated actions between the agents, where each agent contributes to the overall process in their specialized manner.

## Functionality

The `Agency` class allows for flexible and dynamic orchestration of actions between various agents with varying specialties. It holds the structure and logic necessary to define how agents will communicate and collaborate, enabling complex workflows to be managed with ease.

## Usage Example

Crafting a new agency consisting of a CEO, Developer, and Virtual Assistant agents:

```python
from agency_swarm import Agent, Agency

# Define the agent instances
ceo = Agent(...)
developer = Agent(...)
virtual_assistant = Agent(...)

# Define the agency
agency = Agency(
    agents=[ceo, developer, virtual_assistant],
    agency_chart=[
        (ceo, developer),
        (developer, virtual_assistant),
    ],
    shared_instructions='agency_manifesto.md'
)
```

## Best Practices

- Define clear communication pathways and responsibilities for each agent within the agency to streamline processes and avoid confusion.
- Regularly refine the `agency_chart` to reflect the current structure and needs of agent interactions.
- Utilize `shared_instructions` to ensure uniformity of understanding and action across the agency.

## Extending the Agency Class

The `Agency` class can be extended through subclassing to fine-tune its functionality to better suit specific project demands.

```python
# CustomAgency.py
from agency_swarm import Agency

class CustomAgency(Agency):
    """ Custom implementation for a specialized agency structure """
    # additional properties and methods here

# Usage
my_custom_agency = CustomAgency(
    agents=[...],
    agency_chart=[...],
    # ... other parameters as needed
)
```

## Conclusion

The `Agency` class provides a way to effectively manage a group of agents, making it a cornerstone of the Agency Swarm framework. Mastery of this class is essential for orchestrating complex development processes and workflows.
