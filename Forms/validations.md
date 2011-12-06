# Magento Form Validations

Magento uses Prototype.js to handle form validations. Further, it uses an object called `Validation` to handle form validations on a page.

### Start Magento Validations on a Custom Form

`var customForm = new VarienForm('form-name');`

### Add a Validation

The `add` method of the `Validation` object is used to add custom validations for the form. You can add them using the method below: 

```
Validation.add('target-class', 'Validation error text', function(value) {
    return (v === [your test case]);
});
```

Where after implemented, the validator will find all elements with the `target-class`, and test it using the function passed in as the third argument. If the test fails, it will display the text specifed in the second argument.