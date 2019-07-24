JavaScript & ES6 Notes

// Create a function sum() to solve for all three:

        sum(1, 3)
        sum(10, 20, 5)
        sum(2, 5, 80, 1, 10, 12)

        function sum(..args) {
            var total;
            total = args.reduce((acc.elem) => acc + elem, 0);

            console.log(total);
        }

// Print numbers before 5 & print var;

        var i = 10;

        for (let i = 0; i < 5; i++) {
            console.log(i);     // prints(0-4)
        }
        console.log(i);         // prints (10)

// Change below function to use ternary operator

        function isNumber(a) {
            if (typeOf a === "number") {
                return "That's a number";
            } else {
                return "That's not a number";
            }
        }

        console.log(isNumber(10));
        console.log(isNumber("Hey there"));
        console.log(isNumber(true));

        * Ternary operator
        function isNumber(a) {
            // condition ? result1 : result2
            return typeOf a === "number" ? "That's a number" : "That's not a number";
        }