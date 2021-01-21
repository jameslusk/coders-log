# Coder's Log
----------------------------------------------------------

# Format

## LOG:

## DATE, 2021 

**Today's Progress**:

**Thoughts**: 

**Link to work**:

**Resources**:

----------------------------------------------------------

## LOG: #001

## Jan 19th, 2021

**Today's Progress**:
4.4hrs

I started my moring off by uploading a JavaScript Tester program I wrote yesterday and then created a README bio in GitHub for my profile. I then created and formatted this log as a way to journal and track my progress. I wish I had started it sooner.

Zero to Mastery (ZTM) Course: Learning about Document Object Model (DOM): When a web page is loaded, the browser creates a Document Object Model of the page.

The DOM is a W3C (World Wide Web Consortium) standard. The DOM defines a standard for accessing documents:
"The W3C Document Object Model (DOM) is a platform and language-neutral interface that allows programs and scripts to dynamically access and update the content, structure, and style of a document."

<h2>Learned about</h2> 

DOM Selectors
--------------
getElementsByTagName
getElementsByClassName
getElementById

querySelector
querySelectorAll

getAttribute
setAttribute

##Changing Styles
style.{property} //ok

className //best
classList //best

classList.add
classList.remove
classList.toggle

##Bonus
innerHTML //DANGEROUS

parentElement
children

##It is important to CACHE selectors in variables

##CODE: How to make parent elements contorl ( > * )
#parent > * {
    display: block;
    margin: 30px 0;
}

##CODE: how to force first letter to uppercase
textBox.value = textBox.value.charAt(0).toUpperCase() + textBox.value.slice(1).toLowerCase();

Made a simple shopping list maker with DOM and JavaSript.
**Thoughts**: 
Using DOM and JavaScript is exacltly what I was looking for in learning how to mimic making a To-Do list program with Flask. There are a lot of possibilites with JavaScript and DOM manipulation. I'm eager to get more involved. I have some ideas for projects using this system.

**Link to work**:

[Shopping List Maker](https://jameslusk.github.io/shopping-list.v1/)

**Resources**:<br>
[w3schoools - JavaScript HTML DOM](https://www.w3schools.com/js/js_htmldom.asp)<br>
[JavaScript Char/key codes](https://www.cambiaresearch.com/articles/15/javascript-char-codes-key-codes)<br>
[Event reference](https://developer.mozilla.org/en-US/docs/Web/Events)

----------------------------------------------------------

## LOG: 002

## Jan 20th, 2021 

**Today's Progress**: 5.2hrs

Made some progress with a Shopping List maker that I'm working on. It could really double as a To Do list. I have to where user can enter a item in the form field, press enter, and then the item gets added to the list with a checkbox and a delete button. I worked on coding the program to line-through the text when the checkbox is clicked. I spent most of my time today searching and trying different methods to no avail.

I was able to add the checkbox element with the following code;

<!-- // Add checkbox element to list -->
    checkBox = cb = document.createElement( "input" );
    cb.type = "checkbox";
    cb.id = "c1";
    cb.value = name;
    cb.checked = false;
<!-- //Append the checkbox to the li -->
    li.appendChild(cb);

As information, I am writing this program with logic in JavaScript.

**Thoughts**: 

Today was a mental struggle for sure. I searched and attempted different combonations of syntax to make the damn thing line-through list text when the checkbox is clicked. It's crazy that when you get so involved with a problem time seems to fly by. It didn't feel like I had been working on this issue for roughly 5 hours. Nonetheless, I do enjoy it. I enjoy the obsticles and the extraordinary feeling you get once you solve a problem.

I ened up reaching out to some people in the Zero to Mastery Discord as a desparate plea for help. Someone answered, looked at my code, and gave some pointers. I now need to get back on tomorrow and (try to )apply what they said.

**Link to work**:

[Shopping List Maker](https://jameslusk.github.io/shopping-list.v1/)

**Resources**:
[checkbox solution #1](https://stackoverflow.com/questions/56837740/how-to-add-remove-class-from-a-parent-list-itemli-when-their-child-checkbox-is)<br>
[checkbox solution #2](https://stackoverflow.com/questions/40245046/js-how-to-select-and-line-through-the-items-in-html-list-by-pressing-on-a-butt)<br>
[checkbox solution #3](https://github.com/drood87/shoppingList/blob/master/script.js)<br>
[checkbox solution #4](https://github.com/NickPax/shopping-list/blob/master/script.js)

----------------------------------------------------------

## LOG: #003

## DATE, 2021 

**Today's Progress**:

Solved the damned checkbox/line-through issue with my shopping list maker. Sort of; with the following code;

function strikeThrough(event) {
    var parent = document.getElementById("c1").parentElement;
    parent.classList.toggle("done");
}

It performs the strike-through of list item, but only first item on the list. Good enough for now. Moving on in lesson. Notes from fellow ZTM student below helped me out.

## Notes From Joao (ZTM Disscord)

Ok well there are a couple of ways. Based on  what you are doing right now, I would modify the li element's CSS style. To do that you can create addEventListener that will trigger when clicked on a checkbox, target it's parent element (given that your input is inside the li) and update the classList. You should of course create that class in your CSS which would simply apply the text-decoration property.
To target the element of a parent you can use parentElement (is not a function)
I think with this is enough to get started, I think you already are familiar with all of these?
A final hint: do not add the event listener for each individual checkbox. Create one for the entire list and check inside the function which element was clicked on.

## Today's lesson

Made a gradient background generator and learned syntax in both css and javascript to do so.

### CSS Linear Gradients
To create a linear gradient you must define at least two color stops. Color stops are the colors you want to render smooth transitions among. You can also set a starting point and a direction (or an angle) along with the gradient effect.

Styntax:

background-image: linear-gradient(direction, color-stop1, color-stop2, ...);

### <input type="color">

<input> elements of type color provide a user interface element that lets a user specify a color, either by using a visual color picker interface or by entering the color into a text field in #rrggbb hexadecimal format. Only simple colors (without alpha channel) are allowed though CSS colors has more formats, e.g. color names, functional notations and a hexadecimal format with an alpha channel.

The element's presentation may vary substantially from one browser and/or platform to another—it might be a simple textual input that automatically validates to ensure that the color information is entered in the proper format, or a platform-standard color picker, or some kind of custom color picker window.

### HTML

<p>Choose your monster's colors:</p>

<div>
    <input type="color" id="head" name="head"
           value="#e66465">
    <label for="head">Head</label>
</div>

<div>
    <input type="color" id="body" name="body"
            value="#f6b73c">
    <label for="body">Body</label>
</div>

### CSS 

p,
label {
    font: 1rem 'Fira Sans', sans-serif;
}

input {
    margin: .4rem;
}

### HTML DOM textContent Property

Definition and Usage
The textContent property sets or returns the text content of the specified node, and all its descendants.

If you set the textContent property, any child nodes are removed and replaced by a single Text node containing the specified string.

Note: This property is similar to the innerText property, however there are some differences:

textContent returns the text content of all elements, while innerText returns the content of all elements, except for <script> and <style> elements.
innerText will not return the text of elements that are hidden with CSS (textContent will). 
Tip: Sometimes this property can be used instead of the nodeValue property, but remember that this property returns the text of all child nodes as well.

Tip: To set or return the HTML content of an element, use the innerHTML property.

### ZTM Lesson #141. Scope:

// Scope

// Root Scope (window)
var fun = 5;

function funFUnction() {
    // Child Scope
    var fun = "hellooo";
    console.log(fun);
}

### JavaScript Function Scope
In JavaScript there are two types of scope:

Local scope
Global scope
JavaScript has function scope: Each function creates a new scope.

Scope determines the accessibility (visibility) of these variables.

Variables defined inside a function are not accessible (visible) from outside the function.

#### Local JavaScript Variables
Variables declared within a JavaScript function, become LOCAL to the function.

Local variables have Function scope: They can only be accessed from within the function.

// code here can NOT use carName

function myFunction() {
  var carName = "Volvo";

  // code here CAN use carName

}

#### Global JavaScript Variables
A variable declared outside a function, becomes GLOBAL.

A global variable has global scope: All scripts and functions on a web page can access it. 

var carName = "Volvo";

// code here can use carName

function myFunction() {

  // code here can also use carName

}

#### Conditional (Ternary) Operator
JavaScript also contains a conditional operator that assigns a value to a variable based on some condition.

Syntax:
variablename = (condition) ? value1:value2 

Example:
var voteable = (age < 18) ? "Too young":"Old enough";

#### The JavaScript Switch Statement
Use the switch statement to select one of many code blocks to be executed.

Syntax:
switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}

This is how it works:

The switch expression is evaluated once.
The value of the expression is compared with the values of each case.
If there is a match, the associated block of code is executed.
If there is no match, the default code block is executed.

Example #2:

//Using this function, answer the questions below:
function moveCommand(direction) {
    var whatHappens;
    switch (direction) {
        case "forward":
            break;
            whatHappens = "you encounter a monster";
        case "back":
            whatHappens = "you arrived home";
            break;
            break;
        case "right":
            return whatHappens = "you found a river";
            break;
        case "left":
            break;
            whatHappens = "you run into a troll";
            break;
        default:
            whatHappens = "please enter a valid direction";
    }
    return whatHappens;
}

**Thoughts**: 

**Link to work**:<br>
https://jameslusk.github.io/background-generator/

**Resources**: <br>
[CSS Linear Gradients](https://www.w3schools.com/css/css3_gradients.asp)<br>
[<input type="color">](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/color)<br>
[HTML DOM textContent Property](https://www.w3schools.com/jsref/prop_node_textcontent.asp)<br>
[JavaScript Scope](https://www.w3schools.com/js/js_scope.asp)<br>
[Conditional (Ternary) Operator](https://www.w3schools.com/js/js_comparisons.asp)<br>
[The JavaScript Switch Statement](https://www.w3schools.com/js/js_switch.asp)<br>

----------------------------------------------------------