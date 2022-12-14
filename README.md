# HTML Form handling in JS
Form handling is made clean and elegant.

### Problem Statement
It has been seen that my beginners made a common mistake in handling HTML form using JS. They would prefer to use the `id` attribute and the `getElementById` method to read HTML form fields. This approach forced them to write a new statement to accommodate the newly added form field. Thus end with `n` no of statements against `n` no of form fields. This is not that bad but there are many clean and elegant ways to manage form fields. I have proposed one of them here.

### The Solution

My proposed solution helps the developer completely ignore the JS side and live in the HTML universe. When an HTML form is submitted; it passes the current event state to submit handler. That event object contains all the necessary information along with user input. That tiny object is being used in this solution.


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
