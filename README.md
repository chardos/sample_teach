## Function declarations vs expressions
```
function speak (words) {
  console.log(words);
}

var speak = function (words) {
  console.log(words);
}
```

## Function declarations vs expressions

``` javascript
//Bad code
var number = 3250550;
number = number.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");  // 3,250,550
number = '$' + number; // $3,250,550
```
``` javascript
//Good code

var number = 3250550;
number = addCommas(number);
number = addDollarSign(number);

function addCommas(num){
  return num.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
}
function addDollarSign(num){
  return '$' + num;
}
```
- Functions are self documenting
- Making functions do one thing only increases reusability
- Pure functions mean we don't need to worry about any other part of the code.

``` javascript
function addDollarSignAndCommas(num){
  num = addCommas(num);
  num = addDollarSign(num);
  return num;
}
```
