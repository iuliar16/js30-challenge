# PROJECT DESCRIPTION

This project implements the secret key code used sometimes in games that makes something happen. Here the secret code is wesbos and if the user types it he will see some unicorns on the screen.

we listen for each key pressed with window.addEventListener("keyup", (e) => {}} and we push each key in an array (pressed). Then we use splice method to only keep in the array the last 6 keys pressed (secretCode.length = 6). When we press a new key, the first one from the array is removed and we add the new key at the end.
The method splice(index,count) removes count elements starting at index. We use -secretCode.length-1=-7 => start counting the 7th element from the end.

We use pressed.join('') to create a string from the keys and if that string includes the secretCode then we call cornify_add() to show the unicorns.

# WHAT I LEARNED

The formula he used in splice function is interesting and I had to lookup why he used -secrectCode and what happens if we use negative numbers in splice function. Also I did not know about the cornify_add() function.
