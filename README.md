# Fix-Me

This is a class exercise created by our coach [Lambelin Rafael](https://github.com/rafaello104)

I followed this exercises during my training as JuniorWeb Developer at BeCode in maart 2019.
## Objectives

- Learn how to use javascript fully in terms of DOM Manipulation


## Instructions

- Load in [this](https://github.com/becodeorg/GNT-Yu-1.10/blob/master/2.The-Hills/1.Javascript-Intro/1.DOM-Manipulation/files/index.html) html page and [this](https://github.com/becodeorg/GNT-Yu-1.10/blob/master/2.The-Hills/1.Javascript-Intro/1.DOM-Manipulation/files/stylesheet.css) stylesheet
- Read the instructions and solve all the exercises in there
- Save & publish it in a repository called `starting-javascript`
- Show us the end result (send us a pm with the link to the github published page)

## My approach

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

## Thinks I learned

  - When you need to handle text input, use the input event instead. Keyboard events may not be fired if the user is using an alternate means of entering text, such as a handwriting system on a tablet or graphics tablet.

   - To create a new [KeyboardEvent](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent), use the [KeyboardEvent()](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/KeyboardEvent) constructor.

   - You can use [insertRow() method](https://www.w3schools.com/jsref/met_table_insertrow.asp) and [TableRow insertCell() method](https://www.w3schools.com/jsref/met_tablerow_insertcell.asp) to create new rows and cell in a table.

   - To check which key triggered the event use [KeyboardEvent Properties](https://www.w3schools.com/jsref/obj_keyboardevent.asp).

   - Use the [blur event](https://developer.mozilla.org/en-US/docs/Web/API/Element/blur_event) to detect when an element has lost focus.

 ### Documentation

 [KeyboardEvent](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)

 [oninput Event](https://www.w3schools.com/jsref/event_oninput.asp)

 [keycode.info](https://keycode.info/)

 [Table insertRow() Method](https://www.w3schools.com/jsref/met_table_insertrow.asp)

 [How TO - Filter/Search Table](https://www.w3schools.com/howto/howto_js_filter_table.asp)

 [How to highlight text using javascript](https://stackoverflow.com/questions/8644428/how-to-highlight-text-using-javascript)

 [JavaScript String Reference](https://www.w3schools.com/jsref/jsref_obj_string.asp).

