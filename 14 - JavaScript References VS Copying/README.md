# PROJECT DESCRIPTION

This project is about JS reference vs copying.

We work with the array players:
const players = ["Wes", "Sarah", "Ryan", "Poppy"];

if we make a copy:
const team = players;
and then try to change the team array, we will also change the original array players because team is just a reference to players, so changing anything at team array, we will also make that change in players. There are a few solutions for this:

- we can use players.slice() - when we give 0 arguments to slice method ...
- use the spread operator [...players]
- use Array.from(players)

The same goes for objects. We used the object person and if we create a copy like this:
const captain = person;
then changing anything about the captain will change also in person.
For objects, to solve this we can use

- the spread operator
- const captain = Object.assign({}, person);
  These 2 methods work well but only for first level of the object, if we have more levels in an object we can use lodash clone deep method or JSON.parse(JSON.stringify(wes)) - which means that first we create a string from the original object then we parse it to obtain a new object.

# WHAT I LEARNED

I knew about the reference vs copying issue in JS, but I did not know that you can use splice, concat, Array.from to solve it. I always used the spread operator instead. I also used lodash clone deep method before and it was the only thing I actually used for objects, I don't think I used Object.assign(..) before.
