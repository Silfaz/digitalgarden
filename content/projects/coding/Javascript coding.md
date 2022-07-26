---
title: "Javascript coding"
---

## min and max value of an array
https://medium.com/coding-at-dawn/the-fastest-way-to-find-minimum-and-maximum-values-in-an-array-in-javascript-2511115f8621#

*Using Math functions*
`Math.min(1,3,5) //1`
`Math.min([1,3,5]) //NaN`
But `Math.min()` and `Math.max()` expect numbers as arugments, not an array. Use spread syntax `(...)` instead, since it causes the values of the array to be expanded or spread into the function's arguments. 
`Math.min(...[1,3,5]) //1
Math.max(...[1,3,5]) //5`
The spread operator is not good for speed though, slowing down more the higher the number of elements in the array is. But for a few elements it's fine. 

Or alternatively, `.apply()` can be used:
`Math.min.apply(null, [1,3,5]) //1`
This method works fine also for large arrays. 

*Sorting the list numberically*
`array.sort() //In lexographical order`
`array.sort((a,b) => a-b) //Sort numberically, ascending`
`const min = array[0] //Lowest value`
`const max = array[array.length-1] //Highest value`

*Using `.reduce()`*
`const min = () => array.reduce((min, currentValue) => Math.min(min, currentValue), array[0])`

