# 6_serialization.py

This script demonstrates Pydantic's serialization capabilities, specifically using `model_dump` with the `exclude_unset` parameter.

## Pydantic Models

### `Address`

The `Address` model represents a physical address with the following fields:

- `city`: `str`
- `state`: `str`
- `pin`: `str`

### `Patient`

The `Patient` model represents a patient and includes an `Address` object as a nested model:

- `name`: `str`
- `gender`: `str` (with a default value of `'Male'`)
- `age`: `int`
- `address`: `Address`

## Example Usage

1.  An `address_dict` is created to hold the components of an address.
2.  An `Address` object, `address1`, is instantiated from `address_dict`.
3.  A `patient_dict` is created with patient information. Note that the `gender` field is not provided in this dictionary.
4.  A `Patient` object, `patient1`, is instantiated from `patient_dict`. Since `gender` was not provided, it will take on its default value of `'Male'`.
5.  `patient1.model_dump(exclude_unset=True)` is called. This serializes the `Patient` object to a dictionary, but it excludes any fields that were not explicitly set when the object was created. In this case, the `gender` field will be excluded from the output.
6.  The resulting dictionary and its type are printed to the console.
