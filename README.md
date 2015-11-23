# html5CustomValidations

Example:

``` <input type="text" name="name" id="name" required data-validation-message="Custom Validation Message"> ```

```
var elements = document.querySelectorAll("[data-validation-message]");
for (var i = 0; i < elements.length; i++) {
    elements[i].oninvalid = function(e) {
        console.log(e)
        e.target.setCustomValidity("");
        if (!e.target.validity.valid) {
            e.target.setCustomValidity(e.target.dataset.validationMessage);
        }
    };
    elements[i].oninput = function(e) {
        e.target.setCustomValidity("");
    };
}
```
