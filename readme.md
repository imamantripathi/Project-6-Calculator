# ***Calculator Using JavaScript***
----
## **Concepts Used**
---
## **eval()**
>eval() is a function property of the global object.

>The argument of the eval() function is a string. If the string represents an expression, eval() evaluates the expression. If the argument represents one or more JavaScript statements, eval() evaluates the statements. Do not call eval() to evaluate an arithmetic expression; JavaScript evaluates arithmetic expressions automatically.

>If you construct an arithmetic expression as a string, you can use eval() to evaluate it at a later time. For example, suppose you have a variable x. You can postpone evaluation of an expression involving x by assigning the string value of the expression, say "3 * x + 2", to a variable, and then calling eval() at a later point in your script.

>If the argument of eval() is not a string, eval() returns the argument unchanged. In the following example, the String constructor is specified and eval() returns a String object rather than evaluating the string.

<br>
<br>

## **Code**
```
eval(new String('2 + 2')); // returns a String object containing "2 + 2"
```
```
eval('2 + 2');             // returns 4
```
>You can work around this limitation in a generic fashion by using toString().
```
var expression = new String('2 + 2');
eval(expression.toString());            // returns 4
```
>If you use the eval function indirectly, by invoking it via a reference other than eval, as of ECMAScript 5 it works in the global scope rather than the local scope. This means, for instance, that function declarations create global functions, and that the code being evaluated doesn't have access to local variables within the scope where it's being called.
```
function test() {
  var x = 2, y = 4;
  // Direct call, uses local scope
  console.log(eval('x + y')); // Result is 6
  // Indirect call using the comma operator to return eval
  console.log((0, eval)('x + y')); // Uses global scope, throws because x is undefined
  // Indirect call using a variable to store and return eval
  var geval = eval;
  console.log(geval('x + y')); // Uses global scope, throws because x is undefined
}
```
---
# [***Code By Aman Triapthi***](https://linktr.ee/imamantripathi)
---