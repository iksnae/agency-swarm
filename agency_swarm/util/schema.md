# Docs for `dereference_schema` and `reference_schema` Functions

## Overview

These two functions, `dereference_schema` and `reference_schema`, are designed for manipulating JSON schemas, specifically for handling `$ref` references. They are useful in scenarios where schemas need to be simplified or enhanced for easier processing or understanding.

## Function Definitions

### 1. `dereference_schema(schema: Dict) -> Any`

This function resolves `$ref` references within a JSON schema, replacing them with the actual definitions.

- **Parameters**:
  - `schema`: A dictionary representing the JSON schema.

- **Returns**: The schema with `$ref` references resolved.

- **Functionality**:
  - Iterates through the schema and replaces `$ref` nodes with the actual definitions from the `$defs` part of the schema.

### 2. `reference_schema(schema: Dict) -> Dict`

This function enhances a JSON schema by identifying nested properties and extracting them into `$defs`, updating the schema to use `$ref` references to these definitions.

- **Parameters**:
  - `schema`: A dictionary representing the JSON schema.

- **Returns**: The enhanced schema with nested properties extracted into `$defs` and replaced with `$ref` references.

- **Functionality**:
  - Iterates through the schema, finding nested properties that can be extracted into `$defs`.
  - Replaces these nested properties with `$ref` references to the newly created definitions in `$defs`.

## Use Cases

- **`dereference_schema`**: Ideal for simplifying a schema by resolving `$ref` references, making it more readable or easier to process programmatically.
- **`reference_schema`**: Useful for schema optimization and standardization by extracting reusable definitions, making the schema cleaner and more maintainable.

## Example

Suppose we have a JSON schema with nested properties and `$ref` references. We can use `dereference_schema` to resolve these references for a full, expanded view of the schema, or `reference_schema` to optimize the schema by extracting common nested properties into reusable definitions.

## Implementation Notes

- These functions are particularly useful in environments where JSON schemas are heavily used and need to be dynamically manipulated or optimized, such as in API development or data modeling.
- The functions make recursive calls to process all levels of the schema, ensuring thorough and complete handling of the schema structure.
