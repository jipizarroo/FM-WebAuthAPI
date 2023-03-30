# Enhancing Login Forms

Login form flow

Registration => Login => Recover Password

{% hint style="info" %}
This will not be production-ready stuff, this will just be to learn stuff.
{% endhint %}

### Enhancing Login forms.

* Connect labels for each element.
* Don't use placeholders as labels.
* Using HTML semantics.
* on SPA, form names are different for registration and login forms.
* Let the user make the password visible.
* Help Password managers with autocomplete HTML attributes.
* Help Accessibility with aria-described by attribute for instructions.
* On SPAs, use submit form event and submission will be triggered by a pushState.

For the password manager, we must use the following:

```javascript
FOR REGISTRATION
<input type="password" autocomplete="new-password">

FOR LOGIN
<input type="password" autocomplete="current-password">

FOR THIS THERE ARE MANY MORE ( LASTNAME, FAMILY NAME, PHONE, ETC)
<input type="text" autocomplete="name">

IF YOUR USER IS THE SAME AS THE EMAIL
<input type="email" autocomplete="username">
```

UX & Accessibility example:

```javascript
<label for="register_name" autocomplete="name">Your Name</label> 
<input id="register_name" required>
```

An input should always have a label, a placeholder is never enough, if we have a lot of inputs and we double-check what we are doing, and we do not have a label, we forget what the input was asking us for, you need to delete and check the placeholder once again.\
The form is not only important for screen-readers but is also important for mobile, if we focus the label with our finder, it will focus the input too.

Also, a good thing is to have the label as display: block, so it "grabs" the whole block and not just what it's using on the width of the string (Mobile usage).

