# PROJECT DESCRIPTION

The project uses local storage to add persistance to a list of tapas added by user.

First we use document.querySelector to get the form where you type a new tapa and the list where the items will be rendered.

We initialize items array with JSON.parse(localStorage.getItem('items')) || []; to load a previously saved list from localStorage if there is any.

The function addItem(e):
e.preventDefault() - stops the form from reloading the page on submit
Then we read the input value from the form and we build a new object { text, done: false } to represent one tapa and its “checked” state. We add it to the array items and call populateList(items, itemsList) that re-renders the <ul> based on the updated array.

localStorage.setItem('items', JSON.stringify(items)); persists the whole array as JSON.

this.reset() - clears the form field for the next entry.

The function populateList creates one <li> (list item) per item and puts them into one HTML string. Each li includes a checkbox and a label. The checbox has a data-inex used to sotre the array index and checked state that is true if plane.done is also true.

The function toggleDone listens for clicks inside the form but only if the clicked element is an input (a checkbox). Then we can take the index of the clicked element using el.dataset.index (because we used data-index before) and we flip the boolean with

items[index].done = !items[index].done

Then we save in local storage and re render using populateList

Outside of these functions, we call populateList for initial render from whatever is in local storage.

# WHAT I LEARNED

I worked with local storage before and I was already aware of the setItem, getItem methods and the event delegation methods used. I would have implemented this a bit differently, like I would have predefined <li> in HTML and manually update the DOM every time an item is added using appendChild.
