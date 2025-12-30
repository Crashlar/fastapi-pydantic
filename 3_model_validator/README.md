# 3_model_validator.py

This script demonstrates the use of Pydantic's `model_validator` to perform validation that depends on multiple fields.

## Pydantic Model: `Patient`

The `Patient` model is defined with the following fields:

- `name`: `str`
- `email`: `EmailStr`
- `age`: `int`
- `weight`: `float`
- `married`: `bool`
- `allergies`: `List[str]`
- `contact_details`: `Dict[str, str]`

### Model Validator

The `Patient` model includes a `model_validator` named `validate_emergency_contact`.

-   This validator runs `after` the individual fields have been validated.
-   It checks if a patient is older than 60.
-   If the patient is older than 60, it ensures that an `'emergency'` contact is present in the `contact_details`.
-   If the condition is not met, it raises a `ValueError`.

## Function: `update_patient_data`

This function takes a `Patient` object and prints the patient's name, age, allergies, and marital status. It also prints an "updated" message.

## Example Usage

A dictionary `patient_info` is created with patient data. A `Patient` object `patient1` is then instantiated from this dictionary. The `model_validator` is triggered during this process. If the validation is successful, the `update_patient_data` function is called with the `patient1` object.
