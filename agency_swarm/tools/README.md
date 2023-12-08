# BaseTool 

## Overview

The `BaseTool` class serves as an abstract base class for developing tools that conform to the `OpenAISchema`. This class is designed to integrate seamlessly with OpenAI's framework, providing a structured approach to creating tools that leverage OpenAI's capabilities.

## Dependencies

- `abc`: This module provides the infrastructure for defining abstract base classes (ABCs) in Python.
- `OpenAISchema`: This is an assumed external module, likely related to OpenAI's schema or API. It should be implemented or imported from another source.

## Class Definition

### `BaseTool`

The `BaseTool` class inherits from `OpenAISchema` and Python's built-in `ABC` class, making it an abstract class that cannot be instantiated directly. It is intended to be a parent class for more specific tool implementations.

#### Methods

- `__init__(self, **kwargs)`: 
  - Initializes the `BaseTool` instance. 
  - Accepts any number of keyword arguments (`**kwargs`) which are passed to the initializer of `OpenAISchema`.

- `run(self, **kwargs)`: 
  - An abstract method that needs to be implemented in child classes. 
  - This method is designed to execute the primary functionality of the tool. 
  - The use of `**kwargs` allows for flexible argument passing, accommodating various implementation needs in child classes.

## Implementation Notes

- As an abstract class, `BaseTool` cannot be instantiated directly. It requires child classes to implement the `run` method.
- Child classes inheriting from `BaseTool` should adhere to the structure and interface defined in the `OpenAISchema`.
- The flexibility of `**kwargs` in both the constructor and the `run` method allows for versatile implementations in subclasses, catering to different tool requirements.

## Example Usage

Below is a hypothetical example of a subclass implementing `BaseTool`:

```python
class SpecificTool(BaseTool):
    def run(self, **kwargs):
        # Implementation of the specific tool's functionality
        pass
```

In this example, `SpecificTool` would be a concrete implementation of the `BaseTool`, providing specific functionality in the `run` method.


# ToolFactory

## Overview

The `ToolFactory` class provides methods to convert various tool types into `BaseTool` instances compatible with the OpenAI schema. This class includes methods to handle langchain tools, OpenAI schema, and implements functionality to dynamically create tools with specific requirements.

## Dependencies

- `inspect`: Utilized for introspection of the objects and functions.
- `typing`: Provides type hints for better code readability and validation.
- `pydantic`: Used for creating data models based on Python type annotations.
- `base_tool`: Module containing the `BaseTool` class.
- `util.schema`: Assumed to be an external module, containing the `reference_schema` function.

## Class Definition

### `ToolFactory`

`ToolFactory` is a utility class providing static methods to create `BaseTool` instances from different sources.

#### Static Methods

1. `from_langchain_tools(tools: List) -> List[BaseTool]`:
   - Converts a list of langchain tools into a list of `BaseTool` instances.
   - **Parameters:**
     - `tools`: A list of langchain tools.
   - **Returns:**
     - A list of `BaseTool` instances.

2. `from_langchain_tool(tool) -> BaseTool`:
   - Converts a single langchain tool into a `BaseTool` instance.
   - **Parameters:**
     - `tool`: A langchain tool.
   - **Returns:**
     - A `BaseTool` instance.

3. `from_openai_schema(schema: Dict[str, Any], callback: Any) -> BaseTool`:
   - Converts an OpenAI schema into a `BaseTool`.
   - **Parameters:**
     - `schema`: A dictionary representing the OpenAI schema.
     - `callback`: A callback function to be used in the tool.
   - **Returns:**
     - A `BaseTool` instance.

#### Helper Functions Within `from_openai_schema`

- `resolve_ref(ref: str, defs: Dict[str, Any]) -> Any`: Resolves `$ref` references in the schema.
- `create_fields(schema: Dict[str, Any], type_mapping: Dict[str, Type[Any]], required_fields: List[str], defs: Dict[str, Any]) -> Dict[str, Any]`: Creates fields for the Pydantic model based on the schema.

## Implementation Notes

- The class primarily deals with converting tools to a format compatible with the OpenAI schema.
- Dynamic model creation using Pydantic is a key feature, enabling flexibility in tool generation.
- Error handling is included to manage import issues and type parsing errors.

## Usage Example

To use `ToolFactory`, you need to have a list of langchain tools or a specific langchain tool, and the corresponding OpenAI schema for conversion. The usage involves calling the appropriate static method with the required parameters.
