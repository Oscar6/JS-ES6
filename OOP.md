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

// Overriding inherited methods
    function Bird() { }

    Bird.prototype.fly = function() { 
        return "I am flying!"; 
    };

    function Penguin() { }
    Penguin.prototype = Object.create(Bird.prototype);
    Penguin.prototype.constructor = Penguin;

    // fly method is overriding Animal's method
    Penguin.prototype.fly = function() {
        return "Alas, this is a flightless bird."
    }

    let penguin = new Penguin();
    console.log(penguin.fly());

// Use a Mixin to add common behavior between unrelated objects
    let bird = {
    name: "Donald",
    numLegs: 2
    };

    let boat = {
    name: "Warrior",
    type: "race-boat"
    };

    // glideMixin variable = Mixin defines glide method and gives objects(bird & boat) access to  // method
    let glideMixin = function(obj) {
        obj.glide = function() {
            console.log("")
        }
    }

    glideMixin(bird);
    glideMixin(boat);

// Using Closures to protect Properties within an Object from being modified externally
    function Bird() {
        
        //let creates a private variable
        let weight = 15;

        //getWeight method has access to weight since it is created within the same function
        this.getWeight = function() {
            return weight;
        };
    }

    let fowl = new Bird();
    fowl.getWeight();

// Immediately Invoked Function Expression
    function makeNest() {
    console.log("A cozy nest is ready");
    }

    makeNest();

    // Below is an anonymous version
    (function () {
    console.log("A cozy nest is ready");
    }) ();

// Grouping mixins into a module
    let funModule = (function () {
        return {
            isCuteMixin: function(obj) {
                obj.isCute = function() {
                    return true;
                };
            },
            singMixin: function(obj) {
                obj.sing = function() {
                    console.log("Singing to an awesome tune");
                };
            }
        }
    }) ();