As a part of this Kata, you need to create a function that when provided with a triplet, returns the index of the numerical element that lies between the other two elements.

The input to the function will be an array of three distinct numbers (Haskell: a tuple).

For example:

gimme([2, 3, 1]) => 0
2 is the number that fits between 1 and 3 and the index of 2 in the input array is 0.

Another example (just to make sure it is clear):

gimme([5, 10, 14]) => 1
10 is the number that fits between 5 and 14 and the index of 10 in the input array is 1.

#solution
```js
//pure mine + MDN
var gimme = function (inputArray) {
    const len = Math.floor(inputArray.length / 2);
    const cloneArr = [...inputArray];
    cloneArr.sort((a,b)=>a-b);
    return inputArray.indexOf(cloneArr[len]);
};

//most voted
//.slice and .concat are equal to [...arr], use to duplicate the array. COOL!git
function gimme(a) {
  return a.indexOf(a.concat().sort(function(a, b) { return a - b })[1])
}
var gimme = function (inputArray) {
  return inputArray.indexOf(inputArray.slice(0).sort(function(a,b) { return a-b; })[1]);
};


```