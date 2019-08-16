// http://thatjsdude.com/interview/js1.html


// Check Prime
    function isPrime(n){
        var divisor = 2;

        while (n > divisor){
            if(n % divisor == 0){
            return false; 
            }
            else
            divisor++;
        }
        return true;
    }

    > isPrime(137);
    = true
    > isPrime(237);
    = false


// Better Prime
    function isPrime(n) {
        var divisor = 3, 
            limit = Math.sqrt(n);
        
        //check simple cases
        if (n == 2 || n == 3)
            return true;
        if (n % 2 == 0)
            return false;

    while (divisor <= limit) {
            if (n % divisor == 0)
            return false;
            else
            divisor += 2;
        }
        return true;
    }
    
    > isPrime(137);
    = true
    > isPrime(237);
    = false


// Prime Factors

    function primeFactors(n) {
        var factors = [], 
            divisor = 2;
        
        while(n>2) {
            if(n % divisor == 0) {
                factors.push(divisor); 
                n= n/ divisor;
            }
            else {
            divisor++;
            }     
        }
        return factors;
    }

    > primeFactors(69);
    = [3, 23]

// Fibonacci

    function fibonacci(n) {
        var fibo = [0, 1];
  
        if (n <= 2) return 1;

        for (var i = 2; i <=n; i++ ) {
            fibo[i] = fibo[i-1]+fibo[i-2];
        }

        return fibo[n];
    } 

    > fibonacci(12);
    = 144

    // recursive

        function fibonacci(n) {
            if(n<=1)
                return n;
            else
                return fibonacci(n-1) + fibonacci (n-2);  
        }

        > fibonacci(12);
        = 144


// Remove Duplicate

    function removeDuplicate(arr) {
        var exists ={},
            outArr = [], 
            elm;

        for(var i =0; i<arr.length; i++) {
            elm = arr[i];
            if(!exists[elm]) {
                outArr.push(elm);
                exists[elm] = true;
            }
        }
        return outArr;
    }

    > removeDuplicate([1,3,3,3,1,5,6,7,8,1]);
    = [1, 3, 5, 6, 7, 8]


// Merged two sorted away

function mergeSortedArray(a, b){
  var merged = [], 
      aElm = a[0],
      bElm = b[0],
      i = 1,
      j = 1;
  
  if(a.length ==0)
    return b;
  if(b.length ==0)
    return a;
  /* 
  if aElm or bElm exists we will insert to merged array
  (will go inside while loop)
   to insert: aElm exists and bElm doesn't exists
             or both exists and aElm < bElm
    this is the critical part of the example            
  */
  while(aElm || bElm){
   if((aElm && !bElm) || aElm < bElm){
     merged.push(aElm);
     aElm = a[i++];
   }   
   else {
     merged.push(bElm);
     bElm = b[j++];
   }
  }
  return merged;
}

> mergeSortedArray([2,5,6,9], [1,2,3,29]);
 = [1, 2, 2, 3, 5, 6, 9, 29]


 // Check for palindrome

    function isPalindrome(str) {
        var i, len = str.length;
        for(i =0; i<len/2; i++) {
            if (str[i]!== str[len -1 -i])
            return false;
        }
        return true;
    }

    <!-- function checkPalindrom(str) {
        return str == str.split('').reverse().join('');
    } -->

    > isPalindrome('madam')
    = true
    > isPalindrome('toyota')
    = false