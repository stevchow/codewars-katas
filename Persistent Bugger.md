Write a function, persistence, that takes in a positive parameter num and returns its multiplicative persistence, which is the number of times you must multiply the digits in num until you reach a single digit.

For example:

 persistence(39) === 3 // because 3*9 = 27, 2*7 = 14, 1*4=4
                       // and 4 has only one digit

 persistence(999) === 4 // because 9*9*9 = 729, 7*2*9 = 126,
                        // 1*2*6 = 12, and finally 1*2 = 2

 persistence(4) === 0 // because 4 is already a one-digit number

```js

// I think it works like this but not, I false
//too complicated
 function persistence(num) {
 
  function digits(numToConvert){ 
    return numToConvert.toString()
          .split("")
          .map(numz => parseInt(numz))
  }
  //convert to array
  num = digits(num);
  //set new array to push index and later to pop last value
  const lastIndex = [];
  if(num.length === 1) return 0;
  // i-1 because index based on 0
  for( let i = 0; i-1 < num.length ; i++){
    num = num.reduce((a,b)=> digits(a*b));
    //i+1 because it increase everytime it loop
    lastIndex.push(i+1);
  }
  return lastIndex.pop();
}

// Real Solution 

function persistence(num) {
  let times = 0;
  num = num.toString();
  while (num.length > 1) {
    times++;
    num = num.split('').map(Number).reduce((a, b) => a * b).toString();
  }
  return times;
}
```
