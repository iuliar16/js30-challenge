# PROJECT DESCRIPTION

The project uses css to update the color, size and blur of an image. The program uses css variables (--base, --spacing, --blur) for consistency. This variables can be then accesed anywhere in the program using var(--variable_name), this way if we want the backgournd color to be yellow, we just define that once when we define that variable.

 The labels spacing, blur and base have an attribute called data-sizing with value 'px'. We use this attribute to access the inputs and change their values. We have an handleUpdate function which uses this.dataset.sizing which is contains all attributes for this (e.g. data-sizing). Then we change the style for inputs accordingly using style.setProperty and adding that sizing suffix which in our case is 'px'. 
    
The handleUpdate function is called on change and on mousemove over the 3 inputs.

# WHAT I LEARNED

I did not know about this.dataset.attribute_name, where attribute_name is an attribute that I can give any name, like data-sizing, data-something etc. But for this particular example I would not use that. We could have just used this 'px' like:

   document.documentElement.style.setProperty(`--${this.name}`, this.value + 'px');

but I guess this is useful for when that suffix is different for every element.
    