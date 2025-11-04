# PROJECT DESCRIPTION

This project creates a search tool for cities and states after their names. We have an endpoint containing the cities and state and information about them (e.g. population) and we use fetch to retrieve the data. The fetch returns an HTTP response and we use method .json() to parse the body as JSON, and then we use cities.push(...data) to put the data into an array. Here we use the spread operator (...) because we need to change the data array into individual components before pushing into cities array. Another way to do that - we can define let array instead of const and use cities = data.

The function findMatches receives as arguments a wordToMatch (the user input and the array of cities) and filters the cities array and uses regex to find cities/states that match the user input. 'gi' in RegExp comes from global (find all matches, not just the first one) and insensitive (ignoe case - matching both uppercase and lowercase letters).

The function displayMatches calls findMatches for the user input (this.value) and creates an html element (a list item with 2 span elements) that has the cityName, stateName and population. This info is populated withing suggestions element (which is an unordered list <ul>) using suggestions.innerHtml = html; Also, here we want to highlight the userInput in the matched cities so the cityName and cityState added in span will be replaced with <span class="hl">${this.value}</span>` where hl has a yellow background in style.css and this.value is the user input.

# WHAT I LEARNED

I learned how to use the spread operator in this case and also how to work with regex, I did not know about the 'gi' element and also I was not very familiar with returning html directly from a js function.
 Also I realized that instead of using this.value in displayMatches, I am more familiar with adding e as argument for the function and using e.target.value which seems to work the same as this.value.