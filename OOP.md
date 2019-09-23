// FreeCodeCamp.org

// Inheritance

    // Supertype
    function Animal() { }

    Animal.prototype = {
    constructor: Animal, 
    eat: function() {
        console.log("nom nom nom");
    }
    };

    // Inheritance - New instance variables(duck & beagle) are inheriting Animal's prototype via creating a new object

    let duck = Object.create(Animal.prototype); // Change this line
    let beagle = Object.create(Animal.prototype); // Change this line

    duck.eat(); // Should print "nom nom nom"
    beagle.eat(); // Should print "nom nom nom"

// Inheritance - Setting subtype or "child"(Dog) prototype to instance of the parent(Animal)
    function Animal() { }

    Animal.prototype = {
    constructor: Animal,
    eat: function() {
        console.log("nom nom nom");
    }
    };

    function Dog() { }

    // Set prototype of Subtype/"child"(Dog) to be an instance of the Supertype/"parent"(Animal)
    Dog.prototype = Object.create(Animal.prototype);

    let beagle = new Dog();
    beagle.eat();  // Should print "nom nom nom"

// Reset an inherited constructor property
    function Animal() { }
    function Bird() { }
    function Dog() { }

    Bird.prototype = Object.create(Animal.prototype);
    Dog.prototype = Object.create(Animal.prototype);

    // Manually set Bird's constructor property to the Bird object:
    Bird.prototype.constructor = Bird;
    Dog.prototype.constructor = Dog;

    let duck = new Bird();
    let beagle = new Dog();

// Adding methods after inheritance
    function Animal() { }
    Animal.prototype.eat = function() { 
        console.log("nom nom nom"); 
    };

    function Dog() { }

    // Dog is a constructor and inherits prototype from Animal
    Dog.prototype = Object.create(Animal.prototype);
    Dog.prototype.constructor = Dog;

    // Unique behavior added to Dog
    Dog.prototype.bark = function() {
        console.log("Woof!");
    };


    // Add your code above this line

    let beagle = new Dog();

    beagle.eat(); // Should print "nom nom nom"
    beagle.bark(); // Should print "Woof!"
