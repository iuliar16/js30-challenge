# PROJECT DESCRIPTION

This project works with a list of checkboxes and implements the checking of more items at the same time with just one click.

Variable lastChecked will store the last checkbox that the user clicked and it is used to know which two checkboxes define the range when Shift is held.

We use querySelectorAll to select all checkboxes elements.

The function handleCheck runs every time a checkbox is clicked and the parameter e is the click event which gives details like e.shiftKey.

inBetween flag tracks if we are currently looping through checkboxes between the first and second clicked boxes.

We check if the user held down the Shift key (e.shiftKey) and is the current checkbox is checked (this.checked), if these are true then we loop through the checkboxes and for each one we check if its between the current and the previous clicked checkbox. When the loop reaches the current checkbox (this) or the last checked checkbox (lastChecked) it toggles inBetween. This way, once it hits one of them, it starts marking all boxes in between as checked. While inBetween is true, all checkboxes encountered in the loop will be set to checked. At the end of the function we set lastChecked = this so we know this checkbox for the next shift-click selection.

# WHAT I LEARNED

First, I tried to solve the challenge myself and I am used to define all functions as arrow functions so instead of
function handleCheck(e) {},

I typed:

const handleCheck = (e) => {...}

but still used 'this' instead of e.target and I noticed that it did not work because 'this' inside arrow functions will refer to window instead of the current checkbox.

Second, there is really no new js related information in this challenge, but the way of thinking to solve this problem that is interesting. I was thinking we could use the indexes of the current and lastChecked checkboxes but I think this solution is easier to implement.
