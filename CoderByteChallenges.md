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


// Have the function LetterChanges(str) take the str parameter being passed and modify it using the following algorithm. Replace every letter in the string with the letter following it in the alphabet (ie. c becomes d, z becomes a). 
//Then capitalize every vowel in this new string (a, e, i, o, u) and finally return this modified string. 

// Use the Parameter Testing feature in the box below to test your code with different arguments.

        function LetterChanges(str) { 

        // we will replace every letter in the string with the letter following it
        // by first getting the charCode number of the letter, adding 1 to it, then 
        // converting this new charCode number to a letter using the fromCharCode function
        // we also check to see if the character is z and if so we simply convert the z to an a
        var converted = str.replace(/[a-z]/gi, function(char) { 
            return (char === 'z' || char === 'Z') ? 'a' : String.fromCharCode(char.charCodeAt() + 1);
        });

        // we have now successfully converted each letter to the letter following it
        // in the alphabet, and all we need to do now is capitalize the vowels
        var capitalized = converted.replace(/a|e|i|o|u/gi, function(vowel) { 
            return vowel.toUpperCase();
        });

        // return the final string
        return capitalized;
                
        }
        
        LetterChanges("fun times!");     