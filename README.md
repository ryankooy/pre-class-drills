# Pre-Class Drills - JavaScript


### 1. Write a function that takes in two numbers and outputs the max (the greater of the two numbers).
```
Ex: 
Input: 1, 2
Output: 2

Input: 6, -4
Output: 6

Input: 3.4, 2
Output: 3.4
``` 

* Start with the function expression, write the function and test it out with the sample inputs and outputs provided: 

```js
  var max = function(num1, num2){

  };
```


### 2. Write a function that takes in an integer and outputs the sum of all the numbers from 1 to that integer.
```
Ex: 
Input: 2
Output: 3 (because 1 + 2 = 3)

Input: 4
Output: 10  (because 1 + 2 + 3 + 4 = 10)

Input: 10
Output: 55
```


### 3. Write a function that takes in an array of numbers and outputs the maximum number.
```
Ex: 
Input: [ 1, 2, 3 ]
Output: 3

Input: [ 3, 6, 4, 5, 2, 1 ]
Output: 6

Input: [ 3, 3, 3 ]
Output: 3
```


### 4. Write a function that takes in a string and outputs the number of vowels (not counting y).
```
Ex:
Input: "hello"
Output: 2

Input: "you are great!"
Output: 6

Input: "why?"
Output: 0
```


### 5. Write a function that takes in a single word as a string and returns true if it’s a palindrome and false otherwise.
```
Palindrome: a word that is spelled the same way forwards and backwards.

Ex:
Input: "noon"
Output: true

Input: "horse"
Output: false

Input: "racecar"
Output: true
```

### 6. Write a function that takes in a sentence as a string and outputs the number of words.
```
Ex:
Input: “let’s go!”
Output: 2

Input: “I can’t wait to start coding”
Output: 6

Input: “huh?”
Output: 1
```


### 7. Write a function that takes in an array of numbers and outputs the average of all the numbers.
```
Ex:
Input: [ 1 , 4 , 7 ]
Output: 4

Input: [ 10, 5 ]
Output: 7.5

Input: [ 1.5, 3, 2.5, 1 ]
Output: 2
```


### 8. Run the following code and explain the output:
```js
var sample = function(){
    var a = b = 3;
}
sample();
console.log("Is a defined?", typeof a !== "undefined");
console.log("Is b defined?", typeof b !== "undefined");
```
* This is a bit different from the problems above.
  * There are a few different types of interview problems that you'll see as a developer. 
  * Some focus on logic, like the ones we've seen so far, and some focus on measuring understanding of the language.
  * JavaScript has a lot of quirks that make it unique from other languages. Understanding those quirks will make you a stronger JavaScript developer. 


### 9. Write a function that takes in an input and returns true if it’s an integer and false otherwise.
```
Ex:
Input: "7"
Output: false

Input: 7
Output: true

Input: 4.3
Output: false
```


### 10. Write a function that takes an array of integers as an input and outputs the first duplicate.
```
Ex:
Input: [ 2, 5, 6, 3, 5 ]
Output: 5

Input: [ 1, 3, 4, 1, 3, 4 ]
Output: 1

Input: [ 2, 4, 5 ]
Output: undefined
```


### 11. Write a function that takes in a string and returns true if it’s a pangram or false otherwise.
```
Pangram: a sentence that contains every letter in the alphabet.

Ex:
Input: “Watch Jeopardy, Alex Trebek’s fun TV quiz game”
Output: true

Input: “Five hexing wizard bots jump quickly”
Output: true

Input: “JavaScript is the best”
Output: false
```


### 12. Without running the code, determine what the following code will output and why:
```js
var a = 1;
function outer(){
	var a = 2;
	function inner(){
		a++;
    console.log(a);
		var a = 5;
	}
	inner();
}
outer();
```


### 13. Write a function that takes in a number and returns the corresponding day of the week.
```
Ex:
Input: 1
Output: 'Monday'

Input: 5
Output: 'Friday'

Input: 8
Output: undefined
```


### 14. Write a function that takes in an array of integers and the array with duplicates removed.
```
Ex:
Input: [1,2,2,3]
Output: [1,2,3]

Input: [4,5,4,4,7,5]
Output: [4,5,7]

Input: [1,2,3,5]
Output: [1,2,3,5]
```


### 15. Write a function that takes a string as a parameter and determines if it is a valid password with the following constraints:
```
1. It must be at least 8 characters long
2. It must contain at least 1 capital letter
3. It must contain at least 1 lower case letter

Output true if the string is a valid password or false otherwise. 

Ex:
Input: RexTheDog
Output: true

Input: rexthedog
Output: false

Input: REXTHEDOG
Output: false

Input: Dog
Output: false
```


### 16. Write a function that takes in a string and if the string is a string representation of a number, return the negative version of that number otherwise throw an Error.
```
Ex:
Input: '1'
Output: -1

Input: '4'
Output: -4

Input: 'cow'
Error
 ```


### 17. Write a function that takes 2 parameters - the first is an array, the second is an element that may or may not be in the array. Without using any built in array methods, return true if the element is in the array or false otherwise.
```
Ex:
Input: [1,2,3]  1
Output: true

Input: [1,2,3]  4
Output: false

Input: ['code', 'dev', 'nerd']  'nerd'
Output: false

Input: ['code', 'dev', 'nerd']  'genius'
Output: false
```
 

### 18. Write a function that takes an array of numbers and returns an array with each number doubled.
```
Ex:
Input: [1,2,3]
Output: [2,4,6]

Input: [-1,-2,-3]
Output: [-2, -4, -6]
```


### 19. Write a function that takes an array of numbers and a function as parameters. The function paremeter should do something to a numbers (increment, double, decrement, etc) and return the result. Your function should return the array that results from applying the function parameter to each element in the number array. 
```
Ex:
Input: [1,2,3]  function(num) { return num * 2 }
Output: [2,4,6]

Input: [1,2,3]  function(num) { return num + 1 }
Output: [2,3,4]

Input: [1,2,3]  function(num) { return num / 2 }
Output: [.5, 1. 1.5]

Input: [1,2,3]  function(num) { return num - 2 }
Output: [-1, 0, 1]
```


### 20. Write a function that takes an array of numbers and a function as parameters. The function parameter should return true if the input meets a certain condition or false otherwise. Your function should return true if the function parameter returns true for _any_ of the array elements in the array parameter or false otherwise. 
```
Ex:

Input: [1,2,3]  function(num) { return num === 2 }
Output: true

Input: [1,5,3]  function(num) { return num === 2 }
Output: false

Input: [1,2,3]  function(num) { return num % 2 === 0 }
Output: true

Input: [1,5,3]  function(num) { return num % 2 === 0 }
Output: false
```


### 21. Write a function that takes an array of numbers and a function as parameters. The function parameter should return true if the input meets a certain condition or false otherwise. Your function should run the function parameter on every element in the array parameter and, if it returns true, add the element to a new array. Return the new array.
```js
Ex:
Input: [1,2,3]  function(num){return num === 2}
Output: [2]

Input: [1,2,3,4,5,6]  function(num){return num % 2 === 0}
Output: [2,4,6]

Input: [1,2,3,4,5,6]  function(num){return num > 3}
Output: [4,5,6]
```


### 22. What is a JavaScript Prototype?
* There are multiple kinds of interview questions. We've largely practiced coding problems, but you should expect to encounter discussion problems as well.

* Don't copy a definition from a Google Search, but instead read several articles and come up with your own definition.


### 23. Write a function that takes in a number and reverses the order of the digits.
```
Ex:
Input: 1234
Output:4321

Input: 1201
Output:1021

Input: 4
Output: 4
```


### 24. Write a function that takes in a string and and returns the string with white space removed and all letters changed to lowercase. This is a common task when a variable, routeName, etc needs to be created from user input.
```
Ex:
Input: Alper Gokcehan
Output: alpergokcehan

Input:    favorite tree    ever
Output: favoritetreeever

Input: one word
Output: oneword
```
