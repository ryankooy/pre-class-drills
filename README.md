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
var max = function(num1, num2) {

};
```

<details><summary><b>Answer</b></summary>
<p>

```js
var max = function(num1, num2) {
  if (num1 > num2) {
    return num1;
  }
  else {
    return num2;
  }
};
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var totalSum = function (num) {
  var sum = 0;
  for (var i = 0; i <= num; i++) {
    sum += i;
  }
  return sum;
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var findMax = function (numArr) {
  var maxNum = numArr[0];
  for (var i = 1; i < numArr.length; i++) {
    if (numArr[i] > maxNum) {
      maxNum = numArr[i];
    }
  }
  return maxNum;
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var countVowels = function(str) {
  var count = 0;
  var input = str.toLowerCase();
  var vowelArr = ["a", "e", "i", "o", "u"];
  for (var i = 0; i < input.length; i++) {
    if(vowelArr.includes(input[i])) {
      count++;
    }
  }
  return count;
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
// 1. loop through the string.
// 2. compare the first and last letters and return false if not equal.
// 3. compare the second and second from last letters and return false if not equal.
// 4. continue in this manner until all letters are checked. 
// 5. after all letters are checked, return true.
var isPalindrome = function (str) {
  for (var i = 0; i < str.length; i++) {
    if (str[i] !== str[str.length - (i + 1)]) {
      return false;
    }
  }
  return true;
}

// or

var isPalindrome = function (str) {
  return str.split("").reverse().join("") === str;
}
```

</p>
</details>

### 6. Write a function that takes in a string and outputs the *first* occurrence of a character that does not repeat itself in that string.

```
Ex:
Input: “the quick brown fox jumps over the calm kitten quietly”
Output: "b"

Input: “this hat is the greatest!”
Output: "g"

Input: “what a wonderful day it has been!”
Output: "o"
```

<details><summary><b>Answer</b></summary>
<p>

```js
// 1. loop through each character in the string, initializing a count variable at 0.
// 2. assign the variable char to its corresponding character in our string.
// 3. loop through the array, incrementing the count variable every time we see the same character from our first for loop.
// 4. check to see if the count for each character is one and return the character if that is the case.
function firstNonRepeatChar(str) {
  for (var i = 0; i < str.length; i++) {
    var char = str[i];
    var count = 0;
    
    for (var j = 0; j < str.length; j++) {
      if (str[j] === char) {
        count++;
      }
    }

    if (count === 1) {
      return char;
    }
  }
}

// more efficient version:
// 1. create a new object and then create a key corresponding to each different character in our string. The value will be set to be the total number of times that character appears in our string.
// 2. as we iterate through our input string, every time we encounter an additional occurrence of a string, we increment its value in the charCount object by one.
// 3. once the string has been iterated through, we loop through each key in our charCount object, returning the first time we encounter a value of 1.
// 4. it is important to understand that both solutions are correct, but in its worst case, the first solution has a worse time complexity. this is because it takes longer to iterate through a loop inside a loop (O(n^2)) than it does to iterate through that same loop twice (O(2n)).
function firstNonRepeatChar(str) {
  var charCount = {};
  for (var i = 0; i < str.length; i++) {
    var char = str[i];
    if (charCount[char]) {
      charCount[char]++;
    }
    else {
      charCount[char] = 1;
    }
  }
  for (var j in charCount) {
    if (charCount[j] === 1) {
      return j;
    }
  }
}  
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var average = function (numArr) {
  var sum = 0;
  for (var i = 0; i < numArr.length; i++){
    sum += numArr[i];
  }
  return sum / numArr.length;
}

// with reduce:
var average = function (numArr) {
  var sum = numArr.reduce(function(a, b) {
    return a + b;
  }, 0);
  return sum / numArr.length;
}

// with es6:
const average = arr => arr.reduce((a,b) => a + b, 0) / arr.length;
```

</p>
</details>

### 8. Run the following code and explain the output:
```js
var sample = function() {
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

<details><summary><b>Answer</b></summary>
<p>

`var a = b = 3` is equivalent to writing:
```js
b = 3;
var a = b; 
```

* This means that b is created globally (unless you use strict mode) because there is no var keyword in the variable definition.

* After b is created globally, b is assigned the value 3. Then a is created locally inside the function and assigned the value of b, which is 3.

* Because a is created locally, it doesn’t exist outside the function.

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var isInt = function (input) {
  return parseInt(input) === input;
}

// this is preferable since the first one actually won't work for very large numbers 
// because of the way parseInt works under the hood.
var isInt = function (input) {
  return Math.floor(input) === input;
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var findDup = function (arr) {
  for (var i = 0; i < arr.length; i++) {
    for (var j = 0; j < i; j++) {
      if(arr[i] === arr[j]) {
        return arr[i];
      }
    } 
  }
}

// or, more efficient version:
var firstDup = function(arr){
  var dups = {};
  for (var i = 0; i < arr.length; i++) {
    var val = arr[i]
    if (dups[val]) {
      return val;
    }
    else{
      dups[val] = true;
    }
  }
}
// the second one is more efficient because it only loops through the values once.
// nested for loops loop through all the elements one time for each element in the array.
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var isPangram = function (str) {
  str = str.toLowerCase();
  var alphabet = "abcdefghijklmnopqrstuvwxyz";

  for (var i = 0; i < alphabet.length; i++) {
    if (!str.includes(alphabet[i])){
      return false;
    }
  }
  return true;
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

* The output will be `NaN`.

* Inside `inner` we have declared a variable `a` with the `var` keyword, so when we reference `a` inside of `inner`, it will always look to that `a` - not the one declared in outer or globally.

* We are referencing `a` twice before it is declared, but that does not give us a reference error.

* In JavaScript, variable declarations are hoisted, meaning var `a` is essentially moved to the top line of the function, but the assignment = 5 is not. So `a` is declared but has `a` value of `undefined` until the line `var a = 5;` is run.

* `undefined` is not a number so performing a mathematical operation on it, like the post-increment operation `++`, will result in a value of `NaN`.

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var getDay = function (dayNum){
  switch(dayNum){
    case 1: 
      return 'Monday';
    case 2: 
      return 'Tuesday';
    case 3: 
      return 'Wednesday';
    case 4: 
      return 'Thursday';
    case 5: 
      return 'Friday';
    case 6: 
      return 'Saturday';
    case 7: 
      return 'Sunday';
    default: 
      return undefined;
  }
}
```

</p>
</details>

### 14. Write a function that takes in an array of integers and return the array with duplicates removed.
```
Ex:
Input: [1,2,2,3]
Output: [1,2,3]

Input: [4,5,4,4,7,5]
Output: [4,5,7]

Input: [1,2,3,5]
Output: [1,2,3,5]
```

<details><summary><b>Answer</b></summary>
<p>

```js
var deduper = function (numArr){
  var newArr = [];

  for (var i = 0; i < numArr.length; i++) {
    if(!newArr.includes(numArr[i])) {
      newArr.push(numArr[i]);
    }
  }
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var isValidPass = function (password) {
  var hasLower = false;
  var hasUpper = false;

  if (password.length < 8){
    return false;
  }

  for (var i = 0; i < password.length; i++) {
    if (password[i].toLowerCase() === password[i]) {
      hasLower = true;
    }
    if (password[i].toUpperCase() === password[i]) {
      hasUpper = true;
    }
  }

  return hasLower && hasUpper;
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var getNegative = function (numString) {
  var negNum = numString * -1;

  if (isNaN(negNum)) {
    throw 'input must be coercible to a number';
  }

  return negNum;
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var includes = function(arr, elem) {
  for (var i = 0; i < arr.length; i++) {
    if(elem === arr[i]) {
      return true;
    }
  }
  
  return false;
}
```

</p>
</details>

### 18. Write a function that takes an array of numbers and returns an array with each number doubled.
```
Ex:
Input: [1,2,3]
Output: [2,4,6]

Input: [-1,-2,-3]
Output: [-2, -4, -6]
```

<details><summary><b>Answer</b></summary>
<p>

```js
var double = function(arr) {
  var newArr = [];

  for (var i = 0; i < arr.length; i++) {
    const newNum = arr[i] * 2;
    newArr.push(newNum);
  }

  return newArr;
}
```

</p>
</details>

### 19. Write a function that takes an array of numbers and a function as parameters. The function parameter should do something to a numbers (increment, double, decrement, etc) and return the result. Your function should return the array that results from applying the function parameter to each element in the number array. 
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

<details><summary><b>Answer</b></summary>
<p>

```js
var map = function(arr, cb) {
  var newArr = [];

  for (var i = 0; i < arr.length; i++) {
    var newNum = cb(arr[i]);
    newArr.push(newNum);
  }
  
  return newArr;
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var any = function(arr, cb) {
  var isTrue = false;

  for (var i = 0; i < arr.length; i++) {
    var cbOutput = cb(arr[i]);
    if(cbOutput) {
      isTrue = cbOutput;
    }
  }
  
  return isTrue;
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var filter = function(arr, cb) {
  var newArr = [];

  for (var i = 0; i < arr.length; i++) {
    var cbOutput = cb(arr[i]);
    if(cbOutput) {
      newArr.push(arr[i]);
    }
  }
  
  return newArr;
}
```

</p>
</details>

### 22. What is a JavaScript Prototype?
* There are multiple kinds of interview questions. We've largely practiced coding problems, but you should expect to encounter discussion problems as well.

* Don't copy a definition from a Google Search, but instead read several articles and come up with your own definition.

<details><summary><b>Answer</b></summary>
<p>

* Prototypes hold properties and methods that all objects of that type can access.

* For example, the Array prototype has the push, map, any, filter, and includes methods. That's why every array can use those methods.

* The prototype can be thought of as a centralized storage place for functionality that all objects of a type share access to.

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var reverseDigit = function (num) {
  var newNum = '';
  var numStr = num.toString();
  
  for (var i = numStr.length - 1 ; i >= 0; i--) {
    newNum += numStr[i];
  }

  return parseInt(newNum);
}

// alternative way
var reverseDigit = function (num) {
  var newNum = 0;
  var lastDigit;

  while (num > 0) {
    lastDigit = num % 10;
    newNum = (newNum * 10) + lastDigit;
    num = parseInt(num / 10);
  }

  return newNum;
}
```

</p>
</details>

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

<details><summary><b>Answer</b></summary>
<p>

```js
var singleWord = function (str) {
  var newStr = '';

  for (var i = 0; i < str.length; i++) {
    if (str[i] !== ' ') {
      newStr += str[i];
    }
  }

  return newStr.toLowerCase();
}

// using regular expressions
var singleWord = function (str){
  return str.toLowerCase().replace(/\s/g,'');
}
```

</p>
</details>

### 25. Write a function that takes in an input array and returns the unique items in an array.
```
Ex:
Input: [1, 3, 3, 4, 5, 1, 6, 1]
Output: [4, 5, 6]
```

<details><summary><b>Answer</b></summary>
<p>

```js
var unique = function(arr) {
  return arr.filter(function (value, index, self) { 
    return self.indexOf(value) === index;
  });
}
```

</p>
</details>

### 26. Make the following function work:
```js
flipSentence('I love JS');  // should return 'JS love I'
```

<details><summary><b>Answer</b></summary>
<p>

```js
var flipSentence = function(str) {
  return str.split(" ").reverse().join(" ");
}
```

</p>
</details>

### 27. Solve the issue in the following example:
```js
let profile = {
  name: 'Alex',
  getName: function() {
    let innerGetName = function() {
      return this.name;
    }
    return innerGetName();
  }
};

console.log(profile.getName());
```

<details><summary><b>Answer</b></summary>
<p>

```js
let profile = {
  name: 'Alex',
  getName: function() {
    let innerGetName = () => {
      return this.name;
    }
    return innerGetName();
  }
};
```

</p>
</details>

### 28. Make the following statement work:
```js
[1,2,3,4,5].duplicator(); // should return [1,2,3,4,5,1,2,3,4,5]
```

<details><summary><b>Answer</b></summary>
<p>

```js
Array.prototype.duplicator = function() {
  return [...this, ...this];
};
```

</p>
</details>

### 29. Write a function that takes in a sentence as a string and outputs the number of words.
```
Ex:
Input: “let’s go!”
Output: 2

Input: “I can’t wait to start coding”
Output: 6

Input: “huh?”
Output: 1
```

<details><summary><b>Answer</b></summary>
<p>

```js
var wordCount = function(str) {
  return str.trim().split(" ").length;
};
```

</p>
</details>

### 30. For a given symmetric matrix of M by N, where all elements are numbers, calculate the sum of all the boundary elements.
```
Ex:
Input:
[
  [1, 1, 1],
  [1, 2, 1],
  [1, 1, 1]
]
Output: 8

Input:
[
  [1, 1, 1, 1],
  [1, 2, 2, 1],
  [1, 1, 1, 1]
]
Output: 10

Input:
[
  [ 1, 2, 3, 4 ],
  [ 5, 6, 7, 8 ],
  [ 1, 2, 3, 4 ],
  [ 5, 6, 7, 8 ],
  [ 1, 2, 3, 4 ]
]
Output: 51

Input:
[
  [1]
]
Output: 1

```

<details><summary><b>Answer</b></summary>
<p>

```js
const getBoundarySum = function(arr) {
  let m = arr.length;
  let n = arr[0].length;
  let sum = 0;
  
  for (let i = 0; i < m; i++) {
    for (let j = 0; j < n; j++) {
      if (i === 0 || j === 0 || i === m - 1 || j === n - 1) {
        sum += arr[i][j];
      }
    }
  }
  return sum;
}
```

</p>
</details>

### 31. For a given symmetric matrix of M by N, where all elements are numbers, print only the boundary elements.
```
Ex:
Input:
[
  [1, 2, 4],
  [3, 2, 6],
  [2, 1, 9]
]
Output:
1 2 4
3   6
2 1 9

```

<details><summary><b>Answer</b></summary>
<p>

```js
const getBoundaryElems = function(arr) {
  let m = arr.length;
  let n = arr[0].length;
  let str = "";
  
  for (let i = 0; i < m; i++) {
    for (let j = 0; j < n; j++) {
      if (i === 0 || j === 0 || i === m - 1 || j === n - 1) {
        str += arr[i][j] + " ";
      } else {
        str += "  ";
      }
    }
    str += "\n";
  }
  return str;
}
```

</p>
</details>
