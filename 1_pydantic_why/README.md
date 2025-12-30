# 1_pydantic_why.py

This script demonstrates the basic usage of Pydantic for data validation and settings management.

## Pydantic Model: `Patient`

The `Patient` model is defined to represent a patient's data with the following fields:

- `name`: The patient's name. It is a string with a maximum length of 50 characters. The `Annotated` type hint is used to provide additional metadata for this field, including a title, description, and example values.
- `email`: The patient's email address, validated as an `EmailStr`.
- `linkedin_url`: The patient's LinkedIn profile URL, validated as an `AnyUrl`.
- `age`: The patient's age, which must be an integer greater than 0 and less than 120.
- `weight`: The patient's weight, which must be a float greater than 0. The `strict=True` parameter ensures that the value is strictly a float and not, for example, an integer that could be coerced into a float.
- `married`: A boolean indicating whether the patient is married. This field is optional and has a default value of `None`.
- `allergies`: An optional list of strings representing the patient's allergies. The list can have a maximum of 5 items.
- `contact_details`: A dictionary of strings for the patient's contact details.

## Function: `update_patient_data`

This function takes a `Patient` object as input and prints the patient's name, age, allergies, and marital status. It also prints a confirmation message "updated".

## Example Usage

A dictionary `patient_info` is created to hold the data for a new patient. A `Patient` object `patient1` is then instantiated using this dictionary. The `update_patient_data` function is called with `patient1` as the argument to demonstrate the use of the Pydantic model.
