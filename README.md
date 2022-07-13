# Palindrome checker application
<span><img src="https://img.shields.io/badge/Adobe%20XD-470137?style=for-the-badge&logo=Adobe%20XD&logoColor=#FF61F6" /> </span> 
<span><img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" /> </span> 
<span><img src="https://img.shields.io/badge/Sass-CC6699?style=for-the-badge&logo=sass&logoColor=white" /> </span> 
<span><img src="https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E" /> </span>

A palindrome is a word, number, phrase, or another sequence of characters that reads the same backward as forward, such as mom, noon, level or 121. 
Live app ➡️ https://maciejkuran.com/palindrome-checker

## UI Design
<p align="center">
<img src="https://user-images.githubusercontent.com/103118542/171482363-166c79dc-28a0-42df-8ed1-2d208760a919.png">
</p>


## JavaScript concepts
There are a lot of JavaScript concepts that could be used to solve this problem. However, I picked the ones that seemed to match the best – at least from my point of view.

In the examples shown below, I do not access any DOM elements. These are just pure functions and the results will be logged to the console.

If you're interested in checking my application source code in which I do DOM manipulation, feel free to check the uploaded files.


## 1st concept – split(), reverse() and join() methods
I developed this application using this concept. 

This function takes one parameter – 'text'. I am converting the 'text' toLowerCase() and to the String() – just in case someone decides to check if certain numbers are the palindrome or types a string with lowercase and uppercase. In the result any input value (including numbers) will be converted to lowercase and to a string.

As the reverse() method doesn't work on strings, I am converting a string to an array. Then I reverse the array and join() values. I use the ternary operator to log the result to the console.

```
const checkPalindrome = (text) => {
const inputToLowerCase = String(text.toLowerCase());
const newString = inputToLowerCase.split('').reverse().join('');

inputToLowerCase === newString
? console.log(`Input: ${inputToLowerCase}\nOutput: ${newString}\n${inputToLowerCase} is a palindrome !`)
: console.log(`Input: ${inputToLowerCase}\nOutput: ${newString}\n${inputToLowerCase} is NOT a palindrome !`);
};

checkPalindrome('Mom');
//OUTPUT
// Input: mom
// Output: mom
// mom is a palindrome !
```

## 2nd concept – for loop (optional)
This concept may look a bit cleaner to you. I am looping through a string. The iteration starts from the end to the beginning of the string and will keep looping until the condition is true. In this case if i(index) >= 0.

Each iteration's value (single letter) is saved to the 'newString' variable.

With the help of the ternary operator, the result will be logged to the console.


```
const checkPalindrome = (text) => {
const inputToLowerCase = String(text.toLowerCase());
let newString = '';

for (let i = inputToLowerCase.length - 1; i >= 0; i--) {
newString = newString + inputToLowerCase.at(i);
}

inputToLowerCase === newString
? console.log(`Input: ${inputToLowerCase}\nOutput: ${newString}\n${inputToLowerCase} is a palindrome !`)
: console.log(`Input: ${inputToLowerCase}\nOutput: ${newString}\n${inputToLowerCase} is NOT a palindrome !`);
};

checkPalindrome('MOM');
//OUTPUT
// Input: mom
// Output: mom
// mom is a palindrome !
```

