Coderbyte Challenges

// Have the function FirstFactorial(num) take the num parameter being passed and return the factorial of /// it. For example: if num = 4, then your program should return (4 * 3 * 2 * 1) = 24. For the test cases, // the range will be between 1 and 18 and the input will always be an integer. 

    function FirstFactorial(num) { 
    
    if (num === 0 || num === 1) {
        return 1;
    }
    else {
        return num * FirstFactorial(num - 1); 
    }      
    }

// keep this function call here 
// to see how to enter arguments in JavaScript scroll down
FirstFactorial(readline());

// Have the function FirstReverse(str) take the str parameter being passed and return the string in 
// reversed order. For example: if the input string is "Hello World and Coders" then your program should 
// return the string sredoC dna dlroW olleH. 

// Use the Parameter Testing feature in the box below to test your code with different arguments.

    function FirstReverse(str) { 

    return str.split("").reverse().join("");         
    }
   
// keep this function call here 
// to see how to enter arguments in JavaScript scroll down
    FirstReverse(readline());