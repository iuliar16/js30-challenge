# PROJECT DESCRIPTION

This project sorts an array of bands without taking into account the words a, the, an.

We use the strip function to take out these words from the full names and we use replace with a regex expression to do that.

bandName.replace(/^(a |the |an )/i, "").trim();

^ - we look for bandnames that start with
a |the |an - the words we are looking for to strip
/i - insensitive (we also look for The, THE, AN etc)
trim - in case there is a space after the word that we strip, we also take care of that

sortedBands is the sorted array that uses sort method on bands array, using the strip function as a condition.

We take the bands div with querySelector and update the innerHTML by mapping each element in the sorted array with a list item. We use join("") because when we map the elements in a list, we have a comma (,) after each one and we join the words into a string to get rid of the comma.

# WHAT I LEARNED

I learned how tu use the regex better and apparentley if you add an extra space before /i:

name = bandName.replace(/^(a |the |an ) /i, "").trim();

it no longer works :D
