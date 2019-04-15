# Fix-Me

This is a class exercise created by our coach [Lambelin Rafael](https://github.com/rafaello104)

I followed this exercises during my training as JuniorWeb Developer at BeCode in maart 2019.
## Objectives

- Learn how to use javascript fully in terms of DOM Manipulation


## Instructions

- Load in [this](https://github.com/becodeorg/GNT-Yu-1.10/blob/master/2.The-Hills/1.Javascript-Intro/1.DOM-Manipulation/files/index.html) html page and [this](https://github.com/becodeorg/GNT-Yu-1.10/blob/master/2.The-Hills/1.Javascript-Intro/1.DOM-Manipulation/files/stylesheet.css) stylesheet
- Read the instructions and solve all the exercises in there


## My approach

### Step 1
  
  + I added a event listener to the input. If the input is not empty, the innerHTML of the box will be the same as the innerHTML of the input. If the input is empty, the innerHtml of the box will be another string.

### Step 2

  + After the user inputs his data and press enter,  `keydown`  event will trigger `function enter()`.
  This function declares 4 variables ( name, pizza, size, remarks) which holds the user's data.Then the program checks if key enter was pressed with `if (event.key == "Enter") ` condition. If the user has filled at least the name, pizza and size inputs,  the program calls `createRow()`. 
  + When function createRow() is called, the program inserts a row under the first one and 4 cells. The program copies the content from the cell with the same index , on the last row ( user's data), and paste it in the new cell.  `row.insertCell(i).innerHTML = input[i].value;` where inptu[i] holds the user's data.
  + A fourth cell is created at the end of the row. An 'i' element is created with classes from font awesome and append it to the last cell. The onclick event is added to perform the deleteRow function. This function delets  the target's row.


### Step 3

  + To fix the list the program creates an ul element. For every li element added, it copies the text of the existing item and removes the item.
  + To add a input element at the end of the list, the program will make an exception for the li element on the last position, and append an input element.
  + To launch the user's data when the button is clicked, the onclick event changes the content of the last list with the value of the  input. To have the same effect when the user clicks outside the input field, I used the blur event for that input.


### Step 4

  + For the filter, starting from the second row, the program will search in every cell the index of the inputted string. Before the search, a variable named "flag" is initialized with the value false. If such index is found, the flag will be true. At the end of the row, if the flag is true, the row will keep it's display property value, if not, this value will be set to "none".
  + To highlight the found text, the innerHTML of the cell will have a span element wrapping the inputted text.
  + For the check box I created an input element, type checkbox, and a label element for that input. The text of the cell is appended to the label. The text of the cell is removed an the input and label are appended. A [change](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event) event is added to the input. In this event, all the cells in the same column are deleted.

### Step 5

  + To move the box to the right in 2 sec an to the left in 5 sec, I used the tranform property. I have 2 functions that calls each other. First function wait 5 seconds and move the box to the right, and the second function waits about 2 seconds and moves the box to the left.  Even though the move to left function starts exactly when the previous animation has ended, I added 20 miliseconds extra, to look more obviously.

### Step 6

  + To make the box follow the mouse horizontally, I added mousemove event to the box parent. This event updates the mouse position. Using requestAnimationFrame I calculate the distance between the mouse and the box and add it to the box.

### Step 7
  + In this step I created a slider where the user can write a name by adding letters and change them, without typing.  
  + I created a function that takes one parameter. This parameter will be the container's id. In this container I added an input element where the name will be displayed. A button will be added when the user clicks inside the input field. When clicking this button, a div element will be created between the button and the input field. 
  + This div has 2 children. A div element (this will be the letter container) and a input element . The user will be able to choose a letter by moving the slider-thumb. As the slider-thumb is moved, the letter from the div element will be change.
  + To change the value of the name input, I initiate an empty array before any events. When the button is clicked, the letter inside the letter container will be pushed in this array. This is just to make the array increasing its size with every click. The letter does't matter. The oninput event of the slider will create  an array of all the existing sliders. Then it will take the index of the current slider and change the element from the initial array at the same index as the slider. The  name input value wil be a string of all elemens in this array. This way the user can go anytime to a previous letter and change it.
  + It was quite challenging to change the style of the sliders without touching the html file or add a css file, because I couldn't find a way to select the slider-thumb pseudo class with Javascript. Instead I injected a style tag inside the html head and  change the innerHtml of that tag. So in my defence I did not touch anithing outside the <script></script> tags.

### Step 8

  + To make the slider again i call the same function from step 7 but for a different id. The slider will be placed in the div with that id.

## Things I learned

  - When you need to handle text input, use the input event instead. Keyboard events may not be fired if the user is using an alternate means of entering text, such as a handwriting system on a tablet or graphics tablet.

   - To create a new [KeyboardEvent](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent), use the [KeyboardEvent()](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/KeyboardEvent) constructor.

   - You can use [insertRow() method](https://www.w3schools.com/jsref/met_table_insertrow.asp) and [TableRow insertCell() method](https://www.w3schools.com/jsref/met_tablerow_insertcell.asp) to create new rows and cell in a table.

   - To check which key triggered the event use [KeyboardEvent Properties](https://www.w3schools.com/jsref/obj_keyboardevent.asp).

   - Use the [blur event](https://developer.mozilla.org/en-US/docs/Web/API/Element/blur_event) to detect when an element has lost focus.

   - Use [input type="checkbox"](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox) to create a checkbox. You can use [label htmlFor Property](https://www.w3schools.com/jsref/prop_label_htmlfor.asp) to specifie which form element a label is bound to.

   - To delete cells the tableRow [deleteCell()](https://www.w3schools.com/jsref/met_tablerow_deletecell.asp) method comes in handy.

   - The [pageX](https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/pageX) read-only property of the MouseEvent interface returns the X (horizontal) coordinate (in pixels) at which the mouse was clicked.

   - With the [call()](https://www.w3schools.com/Js/js_function_call.asp) method, you can write a method that can be used on different objects.

   - Convert a [unicode](https://www.w3schools.com/charsets/ref_html_utf8.asp) number into a character with [string fromCharCode()](https://www.w3schools.com/jsref/jsref_fromcharcode.asp) method;

   - Create a [slider](https://www.w3schools.com/howto/howto_js_rangeslider.asp) with [input range object](https://www.w3schools.com/jsref/dom_obj_range.asp);


 ### Documentation

 [KeyboardEvent](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)

 [oninput Event](https://www.w3schools.com/jsref/event_oninput.asp)

 [keycode.info](https://keycode.info/)

 [Table insertRow() Method](https://www.w3schools.com/jsref/met_table_insertrow.asp)

 [How TO - Filter/Search Table](https://www.w3schools.com/howto/howto_js_filter_table.asp)

 [How to highlight text using javascript](https://stackoverflow.com/questions/8644428/how-to-highlight-text-using-javascript)

 [JavaScript String Reference](https://www.w3schools.com/jsref/jsref_obj_string.asp).

 [Follow Mouse with Easing & Direction](https://codepen.io/redspiderfish/pen/MYmeYz);

 [Get index of e.target child inside eventlistener](https://stackoverflow.com/questions/35384592/get-index-of-e-target-child-inside-eventlistener);
 [Customising Cross-Browser Range Inputs with CSS and JavaScript](https://css-tricks.com/custom-interactive-range-inputs/);

### Results at https://alexandramadalina.github.io/starting-javascript/
 

