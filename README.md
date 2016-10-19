# Snapkit Validation
Snapkit Validation is a simple jQuery plugin for form validation. You can learn it in less than 5 minutes, by reading this documentation.


##Structure
The form should follow a flexible structure, based on css BEM syntax. In the end, it should result something similiar:

form.form (The form)
|_.form__group (A group, relative to a input/select/textarea and their possible errors)
  |_.form__group__label (The label describing the field, i.e. Username/Password/E-mail/Message etc...)
  
  |_input/select/textarea
  
  |_.form__group__info (The possible errors)
  
  |_.form__group__info
  
So the form has several .form__group, one for each field, and inside every .form__group there is a label, descibing the field, a input/select/textarea which will be filled by the user, and one or more potential errors (you will find more information about the possible error types below), and it might have a structure like this:

```
<div class="form__group">
<label>Username</label>
<input type="text">
<span class="form__group__info" data-validate="required">This field is required</span>
</div>
```

##Errors
To create a possible error, you should add a `<span class="form__group__info" data-validate="required">This field is required</span>` inside the .form__group element, after the input/select/textarea.
The .form__group__info element, as you can see in the example, has a data-validate attribute, which tell the plugin what kind of possible error it should search for.
There are several different kind of errors:

###required
This is one of the most common called. It requires the user to fill the field. To call it, add `<span class="form__group__info" data-validate="required">This field is required</span>` after your input/select/textarea element.

###email
It requires the user to fil the field with a valid email. To call it, add `<span class="form__group__info" data-validate="email">E-mail not valid</span>` after your input/select/textarea element.

###number
It requires the user to fil the field with a number. To call it, add `<span class="form__group__info" data-validate="number">This field must be a number</span>` after your input/select/textarea element.

###website
It requires the user to fil the field with a valid url. To call it, add `<span class="form__group__info" data-validate="website">This field must be a valid website</span>` after your input/select/textarea element.

###minLenght
It requires the user to fill the field with no less then 'x' characters, where 'x' is equal to the paramether you pass inside the data-validate attribute. As you can see in the following example, we added a `data-validate="minLenght | 4"` attribute, meaning that the field can contain no less than 4 chars. To call it, add `<span class="form__group__info" data-validate="minLenght | 4">This field must be at least 4 chars</span>` after your input/select/textarea element.

###maxLenght
It requires the user to fill the field with no more then 'x' characters, where 'x' is equal to the paramether you pass inside the data-validate attribute. As you can see in the following example, we added a `data-validate="maxLenght | 20"` attribute, meaning that the field can contain no more than 20 chars. To call it, add `<span class="form__group__info" data-validate="maxLenght | 20">This field must be no more than 20 chars</span>` after your input/select/textarea element.

###match
It requires the user to fill the field with the same value of another field. You can set the field you want your input/select/textare to match by sending via paramther the id/class of the target element. As you can see in the following example, we added a `data-validate="match | #email"` attribute, meaning that the field must match with the #email field. To call it, add `<span class="form__group__info" data-validate="match | #email">The emails doesn't match</span>` after your input/select/textarea element.

###pattern
Still work in progree

###ajax
Still work in progress

We hope this documentation clarifies most of your doubts. Don't hesitate to ask, in case you have any misunderstanding.

####YET TO DO
-Finish the implementation of pattern and ajax checks
-Write down a better documentation
-Make the script customizable and usable without css dependencies, just by configuring the style as well via js
