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

- **Step 2**
    + After the user inputs his data and press enter,  `keydown`  event will trigger `function enter()`.
    This function declares 4 variables ( name, pizza, size, remarks) which holds the user's data.Then the program checks if key enter was pressed with `if (event.key == "Enter") ` condition. If the user has filled at least the name, pizza and size inputs,  the program calls `createRow()`. 


    + When function createRow() is called, the program inserts a row under the first one and 4 cells. The program copies the content from the cell with the same index , on the last row ( user's data), and paste it in the new cell.  `row.insertCell(i).innerHTML = input[i].value;` where inptu[i] holds the user's data.
    + A fourth cell is created at the end of the row. An 'i' element is created with classes from font awesome and append it to the last cell. The onclick event is added to perform the deleteRow function. This function delets the row of the target.

## Thinks I learned

  - When you need to handle text input, use the input event instead. Keyboard events may not be fired if the user is using an alternate means of entering text, such as a handwriting system on a tablet or graphics tablet.

   - To create a new [KeyboardEvent](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent), use the [KeyboardEvent()](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/KeyboardEvent) constructor.

   - You can use [insertRow() method](https://www.w3schools.com/jsref/met_table_insertrow.asp) and [TableRow insertCell() method](https://www.w3schools.com/jsref/met_tablerow_insertcell.asp) to create new rows and cell in a table.

   - To check which key triggered the event use [KeyboardEvent Properties](https://www.w3schools.com/jsref/obj_keyboardevent.asp).

 ### Documentation

 [KeyboardEvent](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent)

 [oninput Event](https://www.w3schools.com/jsref/event_oninput.asp)

 [keycode.info/](https://keycode.info/)
 [Table insertRow() Method](https://www.w3schools.com/jsref/met_table_insertrow.asp)
