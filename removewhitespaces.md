Simple, remove the spaces from the string, then return the resultant string.

```js
function noSpace(x){
  const clean = x.replace(/ /g,"");
  return clean;
}
```