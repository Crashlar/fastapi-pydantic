# 4_computed_fields.py

This script demonstrates the use of Pydantic's `computed_field` to add a calculated field to a model.

## Pydantic Model: `Patient`

The `Patient` model is defined with the following fields:

- `name`: `str`
- `email`: `EmailStr`
- `age`: `int`
- `weight`: `float` (in kilograms)
- `height`: `float` (in meters)
- `married`: `bool`
- `allergies`: `List[str]`
- `contact_details`: `Dict[str, str]`

### Computed Field

The `Patient` model includes a `computed_field` named `bmi`.

-   This field is calculated using the `weight` and `height` of the patient.
-   The formula for BMI is `weight / (height^2)`.
-   The result is rounded to two decimal places.
-   The `@property` decorator allows `bmi` to be accessed as an attribute.

## Function: `update_patient_data`

This function takes a `Patient` object and prints the patient's name, age, allergies, and marital status, as well as the computed `bmi`. It also prints an "updated" message.

## Example Usage

A dictionary `patient_info` is created with patient data. A `Patient` object `patient1` is then instantiated from this dictionary. The `update_patient_data` function is called with the `patient1` object, and the computed `bmi` is accessed and printed.
