# 5_nested_models.py

This script demonstrates the use of nested Pydantic models to create a structured data hierarchy.

## Pydantic Models

### `Address`

The `Address` model represents a physical address with the following fields:

- `city`: `str`
- `state`: `str`
- `pin`: `str`

### `Patient`

The `Patient` model represents a patient and includes an `Address` object as a nested model:

- `name`: `str`
- `gender`: `str`
- `age`: `int`
- `address`: `Address`

## Example Usage

1.  An `address_dict` is created to hold the components of an address.
2.  An `Address` object, `address1`, is instantiated from `address_dict`.
3.  A `patient_dict` is created, which includes basic patient information and the `address1` object for the `address` field.
4.  A `Patient` object, `patient1`, is instantiated from `patient_dict`. This demonstrates how Pydantic handles nested models.
5.  `patient1.model_dump()` is called to serialize the `Patient` object back into a dictionary. The output of this is printed to the console.

## Benefits of Nested Models

The comments at the end of the script highlight the advantages of using nested models:

-   **Better organization**: Related data (like an address) is grouped together.
-   **Reusability**: The `Address` model can be reused in other models.
-   **Readability**: The structure is easier for developers and API consumers to understand.
-   **Validation**: Nested models are automatically validated by Pydantic.
