# PROJECT DESCRIPTION

This project creates a follow-along highlight navigation effect. Whenever the user hover over any link <a>, a <span> styles ad a highlight box moves under that link, matching the size and position.

We use document.querySelectorAll to select all <a> elements on the page, then we create a new <span> element that will be the highlight box and add the class highlight so it can be styles in CSS.

the function highlightLink uses this.getBoundingClientRect() - this refers to the link currently being hovered and the method returns the link's width, height, top and left.

getBoundingClientRect() is called whenever the mouse enters a link and gives coordinates relative to what we currently see on the screen, we need to add scrollY and scrollX (how much the page is scrolled vertically/horizontally). This gives the correct position in the full page.

Then, we set the highlight box's width and height to match the link and use transform: translate() to move it smoothly to the right place.

# WHAT I LEARNED

I am not sure if I used getBoundingClientRect but it seems familiar. It was interesting how he needed to add window.scrollX and scrollY to convert the viewport coordinated to page coordinates.
