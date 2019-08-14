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