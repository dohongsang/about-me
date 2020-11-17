### Poeta's Test Exam

`1. What is the correct HTML for referring to an external style sheet?`

[ ] A. <stylesheet>mystyle.css</stylesheet>
[x] B. <link rel="stylesheet" type="text/css" href="mystyle.css">
[ ] C. <style src="mystyle.css">

`2. What is the correct JavaScript syntax for opening a new window called "w2" ?`

[x] A. w2 = window.open("http://www.w3schools.com");
[ ] B. w2 = window.new("http://www.w3schools.com");

`3. How can you detect the client's browser name?`

[x] A. navigator.appName
[ ] B. browser.name
[ ] C. client.navName

`4. The HTML <canvas> element is used to:`

[x] A. draw graphics
[ ] B. create draggable elements
[ ] C. manipulate data in MySQL
[ ] D. display database records

`5. What is the difference between == and === ?`

[ ] A. == is the strict equality operator and === is the abstract equality operator
[ ] B. The === operator will compare for equality after doing any necessary type conversions
[ ] C. Both a and b are correct
[x] D. Both a and b are incorrect

`6. What is the result of the below code?`

```javascript
function Person(name) {
  this.name = name;
}
var person = Person("Your Name");
console.log(person.name);
```

[ ] A. undefined
[ ] B. Person { name: "Your Name" }
[ ] C. "Your Name"
[x] D. Uncaught TypeError: Cannot read property 'name' of undefined

`7. What are the cons of using Promise instead of callbacks?`
[ ] A. Avoid callback hell which can be unreadable
[x] B. Slightly more complex code (debatable)
[ ] C. Makes it easy to write sequential asynchronous code that is readable with .then()
[ ] D. Makes it easy to write parallel asynchronous code with Promise.all()

`8. What is the result of the below code? Sequence is:`

```javascript
function fn() {
  console.log(this);
}
var obj = {
  value: 5,
};
var boundFn = fn.bind(obj);
boundFn();
fn.call(obj);
fn.apply(obj);
```

[ ] A. undefined, { value: 5 }, { value: 5 }
[ ] B. undefined, { value: 5 }, undefined
[ ] C. undefined, undefined, { value: 5 }
[x] D. { value: 5 }, { value: 5 }, { value: 5 }

`9. What is the design pattern in JavaScript using in the below code?`

```javascript
var Tesla = function (model) {
  var version, autodrive;
  version = model;
  gofast = function () {
    return `${model} going maximum plaid speed`;
  };
  autodrive = function () {
    return "Engaging autodrive.";
  };
  return {
    gofast: gofast,
    autodrive: autodrive,
  };
};
var roadster = new Tesla("Roadster");
roadster.gofast();
roadster.autodrive();
```

[ ] A. The Module Pattern
[ ] B. The Revealing Module Pattern
[ ] C. The Singleton Pattern
[x] D. The Prototype Pattern

#### SECTION

```
There is a positive integer n. Please find four numbers a, b, c, d (they can be the same number),
let:
 a2 + b2 + c2 + d2 = n and a >= b >= c >= d > 0
The result should be an array [a, b, c, d]; Perhaps there are a lot of valid results, please choose
the one which has largest a or largest b (if the value of a is the same) or largest c (if the value of
a, b are the same).
Some examples:
findNumbers(16) === [2, 2, 2, 2]
findNumbers(110) === [9, 4, 3, 2]
findNumbers(211) === [13, 5, 4, 1]
findNumbers(99) === [9, 4, 1, 1]
```

```javascript Result
function findNumbers (n) {
  let round = Math.floor(Math.sqrt(n));
  for (let i = round; i > 0; i--) {
    for (let j = i; j > 0; j--){
      for (let k = j; k > 0; k--){
        for (let l = k; l > 0; l--){
          if (i*i + j*j + k*k + l*l === n && (i >= j && j >= k && k >= l)) {
            return [i, j, k, l];
          }
        }
      }
    }
  }
}

console.log(findNumbers(16)); => [2, 2, 2, 2]
console.log(findNumbers(110)); => [9, 4, 3, 2]
console.log(findNumbers(211)); => [13, 5, 4, 1]
console.log(findNumbers(99)); => [9, 4, 1, 1]
```
