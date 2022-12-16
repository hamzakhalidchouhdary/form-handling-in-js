# HTML Form handling in JS
Form handling is made clean and elegant.

### Problem Statement
It has been seen that my beginners made a common mistake in handling HTML form using JS. They would prefer to use the `id` attribute and the `getElementById` method to read HTML form fields. This approach forced them to write a new statement to accommodate the newly added form field. Thus end with `n` no of statements against `n` no of form fields. This is not that bad but there are many clean and elegant ways to manage form fields. I have proposed one of them here.

### The Solution

My proposed solution helps the developer completely ignore the JS side and live in the HTML universe. When an HTML form is submitted, submit handler receive all form data. Read user input and validate it. Then response with values and error messages.

### For Developers

As developer you will be able to config HTML; rest will be done in black box. Integration is pretty simple. You has to trigger the form handler method `on submit` event of form and will be responded with user values and validations.

#### Input

| Field | Type | Description 
| --- | --- | ---
| `name` | `string` | will be used as key in response objects
| `data-is-required` | `string` | error message if field is empty
| `data-is-name` | `string` | error message if field value is not validate as name string
| `date-is-email` | `string` | error message if field value is not validate as email
| `data-is-pattren` | `RegEx` | custom `RegEx` for field validation
| `data-pattren-error` | `string` | error message if custom validation doesn’t validated

#### Output

| Data | Type | Description 
| --- | --- | ---
| `values` | `key/value` pair | each user input against input name as `key`
| `validations` | list of `key/value` pair | associative array with keys `isValid`, `message`
| `error flag` | `boolean` | a flag as indication of errors

### Error Handling
To apply validation on any field you need to specify the validation attributes defined above. You will receive `errors` a list and `isError` flag. Error list contains a set of the appropriate `error message` and `isVaild` flag; `field name` as key. `isError` will indicate that weather all fields are valid or not. `true` if all valid `false` otherwise. `showErrors` this method can help in displaying errors. This method receives an error list and gets an HTML element by id matching the field name with error postfix e.g: `email-error`. You can define your own methods if you do like.
