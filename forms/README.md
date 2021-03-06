# Forms

Making forms in HTML isn’t too complex but without a backend server language like PHP or Python (or maybe a little Javascript) we can’t actually do anything with the form itself.

### [▶ Video playlist for forms](https://www.youtube.com/playlist?list=PLWjCJDeWfDdce0-oAUUdtYeuvXsGYCHNY)

---

- [Form setup](#form-setup)
	- [Inputs and labels](#inputs-and-labels)
- [Input types](#input-types)
	- [Other attributes](#other-attributes)
		- [Placeholders](#placeholders)
- [Other input types](#other-input-types)
	- [Textareas](#textareas)
	- [Select boxes](#select-boxes)
	- [Checkboxes](#checkboxes)
	- [Radio buttons](#radio-buttons)
	- [Fieldsets](#fieldsets)
- [Buttons](#buttons)
- [Styling forms and inputs](#styling-forms-and-inputs)
- [Videos](#videos)
- [Links](#links)
	- [Accessibility links](#accessibility-links)

---

## Form setup

There are a few important things to remember about form tags.

```html
<form action="thanks.html" method="post">
	⋮
</form>
```

- The `action` attribute is the URL to where the form’s information should be submitted—but we need a programming language to do something with it.
- The `method` attribute is either `get` or `post`—should most often be “post”. (This matters most to backend developers.)

### Inputs and labels

Inside a form we can create a bunch of inputs—the things people interact with and submit their information to.

All input elements must have a label element associated with them, primarily for accessibility reasons but also as a way to denote what content should be entered into the field.

The input element needs an ID on it, then the label points to the ID using it’s for attribute.

```html
<form action="thanks.html" method="post">
	<!-- Labels are associated with inputs using the for and id attributes -->
	<label for="name">Name</label>
	<input id="name">
</form>
```

*Links*

- [Floated Labels Still Suck](http://www.webaxe.org/floated-labels-still-suck/)

---

## Input types

There are lots of different input types to use in forms—the default is text.

```html
<!-- type="text" is the default for all elements and can be left off -->
<input type="text">
```

- `number` — for accepting numbers
- `email` — for accepting valid e-mail addresses
- `url` — for valid website URLs
- `password` — masks the text that’s being entered with bullets
- `tel` — for telephone numbers
- `time` — for accepting time: hours, minutes, seconds
- `date` — for accepting dates; a calendar picker
- `range` — for selecting from a range of numbers
- `color` — for picking a specific colour
- `file` — for allowing the upload of files
- `search` — for specifying the input as a search field

### Other attributes

Some elements can have other attributes to control what content is allowed to be entered into the field.

- `min` — For specifying a minimum value, for ranges and numbers
- `max` — For specifying a maximum value, for ranges and numbers
- `step` — For specifying a jump value for each increment, for ranges and numbers

```html
<!--
	Would allow any number between 0 and 1, in increments of 0.1
	e.g. 0, 0.1, 0.2, 0.3 ... 0.9, 1.0
-->
<input type="number" min="0" max="1" step="0.1">
```

#### Placeholders

The placeholder attribute can be used to put example text into an element—but should never be used as a replacement for the label.

```html
<input type="url" placeholder="http://example.com">
```

**Links**

- [CSS-Tricks: Numeric Inputs – A Comparison of Browser Defaults](https://css-tricks.com/numeric-inputs-a-comparison-of-browser-defaults/)

---

## Other input types

There are some other input types that can be used in forms for more complex interactions.

### Textareas

An alternative to `<input type="text">` that allows multiple lines and longer text.

```html
<label for="message">Message</label>
<textarea id="message"></textarea>
```

### Select boxes

Select boxes, aka dropdown boxes, allow a user to pick one option of many.

```html
<label for="province">Province</label>
<select id="province">
	<option>Manitoba</option>
	<option>Ontario</option>
	<option>Quebec</option>
</select>
```

### Checkboxes

Checkboxes allow a selection of multiple items out of a few possiblities.

```html
<input type="checkbox" id="apato">
<label for="apato">Apatosaurus</label>
```

In checkboxes (and radio buttons) it’s most common to have the label come after the input element.

### Radio buttons

Radio buttons allow users to select a single option out of many, similar to a select box.

```html
<fieldset>
	<legend>What’s your favourite colour?</legend>

	<input type="radio" id="green" name="fav-color">
	<label for="green">Green</label>

	<input type="radio" id="light-green" name="fav-color">
	<label for="light-green">Light Green</label>

	<input type="radio" id="dark-green" name="fav-color">
	<label for="dark-green">Dark Green</label>
</fieldset>
```

The way to group a bunch of radio buttons together, so they work as a single group is to give them all the same name, like `name="fav-color"`.

### Fieldsets

Above, we’re using the `<fieldset>` element to group radio buttons together semantically. The fieldset can be used to group any inputs together in a form that logically belong together.

*Groups of radio buttons and checkboxes should always be surrounded by fieldsets.*

Here’s an example of grouping address inputs together:

```html
<fieldset>
	<legend>Mailing Address</legend>

	<div>
		<label for="street-address">Street Address</label>
		<input id="street-address">
	</div>
	<div>
		<label for="city">City</label>
		<input id="city">
	</div>
	<div>
		<label for="country">Country</label>
		<input id="country">
	</div>
	<div>
		<label for="postal-code">Postal Code</label>
		<input id="postal-code">
	</div>
</fieldset>
```

---

## Buttons

All forms need to have buttons otherwise the form’s information can’t be sent.

```html
<form>
	⋮
	<button type="submit">Send</button>
</form>
```

Most often the button’s type should be set to “submit”. But if you don’t want it to submit the form and control the button with Javascript, leave the `type` attribute off.

---

## Styling forms and inputs

**When it comes to styling inputs and forms, the most important thing to remember that they are just plain old HTML elements. They can have borders, paddings, margins, colors, fonts, display—anything.**

---

## Videos

1. [Forms: introduction](https://www.youtube.com/watch?v=UoSh5xoz6fg&index=1&list=PLWjCJDeWfDdce0-oAUUdtYeuvXsGYCHNY)
2. [Forms: contact form](https://www.youtube.com/watch?v=GCeKgnALJGs&index=2&list=PLWjCJDeWfDdce0-oAUUdtYeuvXsGYCHNY)
3. [Forms: styling](https://www.youtube.com/watch?v=RYRU0NCWLCk&index=3&list=PLWjCJDeWfDdce0-oAUUdtYeuvXsGYCHNY)
4. [Forms: input types](https://www.youtube.com/watch?v=8pITd2_bgso&index=4&list=PLWjCJDeWfDdce0-oAUUdtYeuvXsGYCHNY)
5. [Forms: checkboxes, radio buttons & fieldsets](https://www.youtube.com/watch?v=GtWZUoGZN4U&index=5&list=PLWjCJDeWfDdce0-oAUUdtYeuvXsGYCHNY)

## Links

- [HTML5 forms introduction and new attributes](http://html5doctor.com/html5-forms-introduction-and-new-attributes/)
- [HTML5 forms input types](http://html5doctor.com/html5-forms-input-types/)
- [CSS3 Pseudo-Classes and HTML5 Forms](http://html5doctor.com/css3-pseudo-classes-and-html5-forms/)
- [MDN: Forms](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms)
- [MDN: Data form validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms/Data_form_validation)
- [MDN: Constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
- [Making Forms Fabulous with HTML5](http://www.html5rocks.com/en/tutorials/forms/html5forms/)
- [HTML5 Form Validation Examples](http://www.the-art-of-web.com/html/html5-form-validation/)

### Accessibility links

- [Simply Accessible: Including error messages in labels](http://simplyaccessible.com/bpow/error-messages-in-labels/)
- [Simply Accessible: Displaying multiple errors on a form](http://simplyaccessible.com/bpow/error-summary/)
- [Simply Accessible: One error message does not fit all](http://simplyaccessible.com/bpow/error-message-content/)
