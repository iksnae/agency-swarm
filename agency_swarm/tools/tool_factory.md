# ToolFactory Class

## Overview

The `ToolFactory` class implements a factory design pattern to create and manage instances of tools within the Agency Swarm framework, enabling a consistent and efficient process for tool generation based on diverse configurations.

## Core Methods

- **from_langchain_tools**: Converts a list of langchain tools into `BaseTool` instances.
- **from_langchain_tool**: Converts a single langchain tool into a `BaseTool` instance, including a callback to handle tool logic.
- **from_openai_schema**: Creates a `BaseTool` from an OpenAI schema, addressing schema standardization and resolution.

## Schema Standardization and Resolution

`ToolFactory` standardizes the schema through `reference_schema()` to ensure all $refs are resolved. It dynamically constructs Pydantic models based on the schema properties, enabling custom tool input configurations.

### Dynamic Model and Class Generation

`ToolFactory` dynamically generates classes based on predefined schemas. These classes, derived from `BaseTool` and the Pydantic model, allow for the specification of complex inputs like objects and arrays.

### Type Mapping

Using a dictionary, `ToolFactory` maps JSON schema types to Python types, aiding in the creation of Pydantic models that reflect these types correctly.

### Integration within the Agency Swarm

The `ToolFactory` serves as a key element in the Agency Swarm tool creation process, facilitating consistent and adaptable tool instantiation that developers can seamlessly integrate into various workflows.

### Usage Example

Creating a tool instance for data retrieval can be as follows:

```python
DataRetrievalTool = ToolFactory.from_openai_schema(data_retrieval_schema, data_retrieval_callback)
# Instantiating the data retrieval tool with a specific dataset
my_data_tool = DataRetrievalTool(dataset='sales')
# Running the tool to retrieve data
results = my_data_tool.run()
```

In this example, `data_retrieval_schema` represents the tool's input schema while `data_retrieval_callback` processes these inputs to produce the desired output.

## Conclusion

The `ToolFactory` class is integral to the Agency Swarm development environment, promoting a scalable and adaptable tooling infrastructure through its efficient mechanisms for tool instantiation.
