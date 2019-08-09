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