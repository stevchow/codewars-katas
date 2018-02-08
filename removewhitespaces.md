Simple, remove the spaces from the string, then return the resultant string.

```js
function noSpace(x){
  return x.replace(/\s/g,""); // \s for looking for whitespace
}
//or
function noSpace(x){return x.split(' ').join('')}
```

