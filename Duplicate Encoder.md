The goal of this exercise is to convert a string to a new string where each character in the new string is '(' if that character appears only once in the original string, or ')' if that character appears more than once in the original string. Ignore capitalization when determining if a character is a duplicate.

Examples:

"din" => "((("

"recede" => "()()()"

"Success" => ")())())"

"(( @" => "))(("


```js
function duplicateEncode(word){
  return word
    //make it lowercase
    .toLowerCase()
    //convert into array
    .split('')
    //use array method which is .map() that takes 3 params 
    //( currentValue, indexOfCurrentValue, currentArray)
    //check with loop if the first index equal with last index means does it the only word there?
    //if yes return '(' else ')'
    .map((a, i, w) => w.indexOf(a) === w.lastIndexOf(a) ? '(' : ')')
    .join('');
}
```