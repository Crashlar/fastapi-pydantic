# 2_field_validator.py

This script demonstrates the use of Pydantic's `field_validator` to perform custom validation and transformation on model fields.

## Pydantic Model: `Patient`

The `Patient` model is defined with the following fields:

- `name`: `str`
- `email`: `EmailStr`
- `age`: `int`
- `weight`: `float`
- `married`: `bool`
- `allergies`: `List[str]`
- `contact_details`: `Dict[str, str]`

### Field Validators

The `Patient` model includes three custom validators:

1.  **`email_validator`**: This validator checks the domain of the email address. It is applied to the `email` field.
    -   It ensures that the email's domain is one of the allowed domains (`'hdfc.com'` or `'icici.com'`).
    -   If the domain is not valid, it raises a `ValueError`.

2.  **`transform_name`**: This validator transforms the `name` field.
    -   It converts the patient's name to uppercase.

3.  **`validate_age`**: This validator checks the validity of the `age` field. It runs `after` the initial type coercion.
    -   It ensures that the age is between 0 and 100 (exclusive).
    -   If the age is outside this range, it raises a `ValueError`.

## Function: `update_patient_data`

This function takes a `Patient` object and prints the patient's name, age, allergies, and marital status. It also prints an "updated" message.

## Example Usage

A dictionary `patient_info` is created with patient data. A `Patient` object `patient1` is then instantiated from this dictionary. During instantiation, Pydantic performs validation and type coercion, including the custom field validators. The `update_patient_data` function is then called with the validated `patient1` object.
