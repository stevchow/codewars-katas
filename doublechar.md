## Given a string, you have to return a string in which each character (case-sensitive) is repeated once.

```
doubleChar("String") ==> "SSttrriinngg"

doubleChar("Hello World") ==> "HHeelllloo  WWoorrlldd"

doubleChar("1234!_ ") ==> "11223344!!__  "
```


# solution

```js 
function doubleChar(str) {
  // Your code here
  //convert str into array by using spread. Spread is used for slice every word in str and convert it into index value in new array
  //then we apply Array.map method to loop over every index in the new array and repeat it 2 times
  //finally join them
  return ([...str].map(a=> a.repeat(2)).join(''));
}
```
// function doubleChar(str) {
//   // Your code here
//   return (str.split('').map(a=> a.repeat(2)).join(''));
// }