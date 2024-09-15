# JQUERY NOTES

This repository contains jQuery topics and their notes to learn as a beginner.

*Refer the below contents, To kick start the learning of jQuery. which gives you __step by step__ approach to the concepts.*
\
&nbsp;

## Prerequisites
Before diving into jQuery, ensure you have a strong foundation in:
1. [HTML](https://github.com/ag-sanjjeev/HTML-Notes): Understand the structure and elements of web pages.
2. [CSS](https://github.com/ag-sanjjeev/CSS-Notes): Grasp styling and layout concepts.
3. [JavaScript](https://github.com/ag-sanjjeev/JavaScript-Notes): Have a good understanding of core JavaScript concepts like variables, functions, objects, and DOM manipulation.

## &#9776; CONTENTS 
1. [Introduction](#-introduction)
	- [What is jQuery](#-what-is-jquery)
	- [Uses](#-uses)
	- [Key features of jQuery](#-key-features-of-jquery)
2. [Basic Syntax and Selectors](#-basic-syntax-and-selectors)
	- [jQuery Object](#-jquery-object)
	- [Selectors](#-selectors)
3. [DOM Manipulation](#-dom-manipulation)
	- [Traversing the DOM](#-traversing-the-dom)
	- [Modifying attributes and content](#-modifying-attributes-and-content)
	- [Creating and removing elements](#-creating-and-removing-elements)
4. [Event Handling](#-event-handling)
	-	[Binding and unbinding events](#-binding-and-unbinding-events)
	-	[Event object](#-event-object)
	-	[Custom events](#-custom-events)
5. [AJAX Requests](#-ajax-requests)
	- [Making Requests](#-making-requests)
	- [Handling Responses](#-handling-responses)
	- [Data Serialization](#-data-serialization)
6. [Effects and Animations](#-effects-and-animations)
	- [Effects](#-effects)
	- [Animations](#-animations)
	- [Callbacks, Piping and Chaining](#-callbacks-piping-and-chaining)
7. [Plugins and Extensions:](#-plugins-and-extensions)
	- [Popular jQuery plugins:](#-popular-jquery-plugins)
		- [UI Widgets](#-ui-widgets)
		- [Validation](#-validation)
		- [DataTables](#-datatables)
	- [Creating custom plugins](#-creating-custom-plugins)

---

## &#10162; Introduction:

### &#10022; What is jQuery:
jQuery is a JavaScript library that simplifies DOM manipulation, event handling, and AJAX requests. It provides a consistent way to write code, making it easier to develop a JavaScript based web applications through it.

The `$` symbol in jQuery is a shorthand for the jQuery function. It is a convenient way to select elements from the DOM tree.

```javascript
// to select element
jQuery('#myElement');
// shorthand of jQuery function
$('#myElement');
```

### &#10022; Uses:
- Improved code readability: jQuery syntax is often more concise and easier to understand than plain JavaScript, It makes the code more readable and maintainable.
- Cross-browser compatibility: jQuery can support most of the browsers, ensuring that the code works consistently across different browsers and devices.
- Built-in functions: jQuery provides the rich set of functions and methods for common web development tasks.

### &#10022; Key features of jQuery:

- DOM manipulation: It can select, create, modify, and remove elements from the DOM.
- Event handling: It can simplifies the event binding and handling mechanism, including custom events.
- AJAX: It can make asynchronous requests to the server.
- CSS manipulation: It can apply styles to elements dynamically.
- Effects: It can create animations and visual effects.
- Utilities: It provides various utility functions such as string manipulation and browser detection.

---

## &#10162; Basic Syntax and Selectors:

### &#10022; jQuery Object:
- jQuery Object can be created using `$()` function, which represent a collection of DOM elements.

*Syntax: $('selector')*

```javascript
// It creates a jQuery object representing the element with the ID of "myElement"
$('#myElement')
```

### &#10022; Selectors:
The selectors requires to select element in the DOM tree. jQuery can work with following selectors.

- ID Selector: `#id` - It selects the element by their id name.
- Class Selector: `.class-name` - It selects the element by their class name.
- Element Selector: `tag-name` - It selects the element by their tag name.

```javascript
  // tag name selector
  let paragraphs = $('p');
  // id name selector
  let elementById = $('#myElement');
  // class name selector
  let elementsByClass = $('.myClass');
  // attribute selector
  let links = $('a[href]');
  // Hierarchical selectors
  let firstChild = $('div > p');
  let nextSibling = $('p + span');
  let allSiblings = $('div ~ p');
  let descendants = $('div p');
```

---

## &#10162; DOM Manipulation:

### &#10022; Traversing the DOM:
It will select and go through the DOM tree based on the element specified in the jQuery selectors.

- `parent()`: Returns the parent element of the selected elements.
- `children()`: Finds direct child elements of the selected elements.
- `closest()`: Finds the first ancestor element that matches the selector.
- `siblings()`: Finds sibling elements of the selected elements.
- `first()`: Finds the first element in the matched set.
- `last()`: Finds the last element in the matched set.
- `next()`: Finds the next sibling element.
- `prev()`: Finds the previous sibling element.
- `find()`: Finds descendant elements of the selected elements.
- `eq()`: Gets an element at a specific index.

```javascript
// getting DOM reference of parent element
$('element').parent();
// getting collections of children DOM reference of an element
$('element').children();
```

### &#10022; Modifying attributes and content:
It will get and set attributes and content and value of the elements. Some methods will accepts only one argument and most will accept two arguments. Typically, the last parameter is specified means that it will assign or set the value. 

- `attr()`: Gets or sets attributes of elements.
- `removeAttr()`: Removes an attribute from an element.
- `val()`: Gets or sets the value of input elements.
- `text()`: Gets or sets the plain text content of elements.
- `html()`: Gets or sets the HTML content of elements.
- `css()`: Gets or sets CSS properties of elements.
- `prop()`: Gets or sets properties of elements.
- `data()`: Gets or sets data attributes.

```javascript
// dynamically setting href attribute of an anchor tag
let href = link.attr('href');
link.attr('href', 'https://example.com');

// Getting value of input element
let value = input.val();
// Setting value of input element
input.val('New value');

```

### &#10022; Creating and removing elements:
It will create, manage and remove HTML elements in the DOM tree by specifying the reference.

- `append()`: Inserts elements at the end of the current elements.
- `prepend()`: Inserts elements at the beginning of the current elements.
- `after()`: Inserts elements after the current elements.
- `before()`: Inserts elements before the current elements.
- `remove()`: Removes the current elements.
- `empty()`: Removes all child elements from the current elements.
- `clone()`: Creates a clone of the selected elements.

```javascript
$(document).ready(function() {
  let container = $('#container');
  let newParagraph = $('<p>New paragraph</p>');

  // Append an element
  container.append(newParagraph);

  // Prepend an element
  container.prepend(newParagraph);

  // Insert after an element
  paragraph.after(newParagraph);

  // Insert before an element
  paragraph.before(newParagraph);

  // Remove an element
  newParagraph.remove();

  // Empty an element
  container.empty();
});
```

---

## &#10162; Event Handling

### &#10022; Binding and unbinding events
- **Binding events to the HTML element in different ways as below:**
	- `click()`: Binds a click event handler.
	- `hover()`: Binds hover events (mouseenter and mouseleave).
	- `focus()`: Binds a focus event handler.
	- `blur()`: Binds a blur event handler.
	- `submit()`: Binds a submit event handler for forms.
	- `change()`: Binds a change event handler for input elements.

- **One method can accept specific type of event to bind:**
	- `on()`: Attaches event handlers to elements.

- **One method can unbind events to the elements:**
	- `off()`: Removes event handlers from elements.

### &#10022; Event object
The event object is passed to the event handler function and contains information about the event, such as DOM reference of the element, the event type, and the event related data.

- `target:` The element that triggered the event.
- `type:` The type of event.
- `preventDefault()`: Prevents the default action of the event (e.g., form submission).
- `stopPropagation()`: Stops the event propagation (It prevents the event from bubbling up the DOM).

```javascript
$('a').click(function(event) {
  event.preventDefault();
  console.log('Link clicked:', event.target.href);
});
```

### &#10022; Custom events
- `trigger()`: Triggers a custom event on an element.
- `triggerHandler()`: Triggers a custom event without bubbling.

```javascript
$(document).ready(function() {
	// defining custom event handler
  $('#myButton').on('customEvent', function(event) {
    console.log('Custom event triggered');
  });

  // triggering custom event based on click event
  $('#triggerButton').click(function() {
    $('#myButton').trigger('customEvent');
  });
});
```

---

## &#10162; AJAX Requests
AJAX stands for Asynchronous JavaScript and XML. It allows web applications to send and receive data with a server in the background. So, It only refreshes the specific part of the web page rather than refresh the whole page. It gives the possibilities of dynamic content to be loaded for enrich user interactions.

### &#10022; Making Requests
jQuery provides several methods for making AJAX requests:

- `$.ajax()`: The most flexible method for making AJAX requests. Which accepts type or method of request to make and also various options along to it.
- `$.get()`: A simplified method for making GET requests.
- `$.post()`: A simplified method for making POST requests.
- `$.getJSON()`: A simplified method for making GET requests and parsing the response as JSON.

```javascript
$.ajax({
  url: 'https://api.example.com/data',
  type: 'GET',
  dataType: 'json',
  success: function(data) {
    console.log(data);
  },
  error: function(xhr, status, error) {
    console.error('Error:', error);
  }
});

// Using simplified methods:
$.get('https://api.example.com/data', function(data) {
  console.log(data);
});

$.post('https://api.example.com/data', { name: 'John' }, function(data) {
  console.log(data);
});

$.getJSON('https://api.example.com/data', function(data) {
  console.log(data);
});
```

### &#10022; Handling Responses
jQuery gives the possibilities to handle the response in two ways.

- `success` callback: The function to be executed if the request is successful.
- `error` callback: The function to be executed if the request fails.

### &#10022; Data Serialization
jQuery can serialize the data before make any request in two ways.

- Query parameters: Data can be sent as query parameters in the URL.
- JSON: Data can be sent as a JSON object in the request body.

```javascript
// It serializes the data in url as typeuserdetail and response=json
// It serializes the data in the data option as JSON
$.ajax({
  url: 'https://api.example.com?type=userdetail&response=json',
  type: 'POST',
  data: { name: 'John', age: 30 },
  dataType: 'json',
  success: function(data) {
    console.log(data);
  },
  error: function(xhr, status, error) {
    console.error('Error:', error);
  }
});
```

---

## &#10162; Effects and Animations

### &#10022; Effects
jQuery has following transition effects to applied on the element.
- `fadeIn()`: Fades elements in.
- `fadeOut()`: Fades elements out.
- `slideDown()`: Slides elements down.
- `slideUp()`: Slides elements up.
- `toggle()`: Toggles between showing and hiding elements.
- `fadeTo()`: Fades elements to a specified opacity.
- `fadeToggle()`: Toggles between fading in and out.
- `slideToggle()`: Toggles between sliding down and up.

```javascript
$('#myElement').fadeIn(1000);
$('#myElement').fadeOut(500);
$('#myElement').slideDown(2000);
$('#myElement').slideUp(1500);
$('#myElement').toggle();
$('#myElement').fadeTo(1000, 0.5);
$('#myElement').fadeToggle(500);
$('#myElement').slideToggle(2000);
```

### &#10022; Animations
jQuery has `animate` method to create custom animation to the element. This `animate()` method creates custom animations with specified properties, durations, and easing functions.

```javascript
$('#myElement').animate({
  left: 200,
  opacity: 0.5
}, 1000);
```

### &#10022; Callbacks, Piping and chaining
Callbacks: Functions that are executed after the completion of another method or function.
Chaining: Combining multiple functionalities into a single sequence.
Piping: Passing the result of a method as an argument to another.

```javascript
$('#myElement')
  .fadeIn(1000)
  .animate({ left: 200 }, 500)
  .fadeOut(1000)
  .promise() // Get a Promise for the animation
  .done(function() {
    console.log('Animation complete');
  });
```

---

## &#10162; Plugins and Extensions:
jQuery can able to work with external plugins that is made for and by jQuery to extend it's possibilities and use cases.

### &#10022; Popular jQuery plugins:
There are commonly used jQuery plugins for creating UI, form validation and for creating and handling large data based tables.

### &#10022; UI Widgets:
- jQuery UI: This plugin used for creating user interface such as widgets, dialogs, tabs, sliders, datepickers, and more.

### &#10022; Validation:
- jQuery Validate: A plugin for validating form data.

### &#10022; DataTables:
- jQuery DataTables: A powerful plugin for creating and handling the large data based interactive tables with features like sorting, filtering, pagination, and more.

### &#10022; Creating custom plugins:
To create custom jQuery plugins to extend jQuery's functionality and encapsulate reusable code. 

*Syntax:*
```javascript
$.fn.myPlugin = function(options) {
  // Plugin logic here
  return this; // Return the jQuery object for chaining
};
```

```javascript
$('#myElement').myPlugin({
  option1: 'value1',
  option2: 'value2'
});
```

---

By following this roadmap and consistently practicing, you can learn a basic fundamentals in JQuery and build web application.

## &#9873; Contribution
Contributions are welcome! If you have any suggestions, bug reports, or feature requests, please open an issue or submit a pull request. Make sure to follow the existing coding style and provide clear documentation for your changes.

## &#9873; License
This reference licensed under the [MIT license](LICENSE). Feel free to use, modify, and distribute it as per the terms of the license.

## &#9873; Contact
If you have any questions or need further assistance, please feel free to reach me at [Email](mailto:sanjjeevag.aug21@gmail.com)


Thanks for reviewing this reference notes!