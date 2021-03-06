1. datatypes
1. var, let & const 
1. Funções
1. Escopo
1. Hoisting
1. Closures
1. This
1. Apply, call, and bind
1. Call stack
1. Heap
1. Promises queue
1. Events queue
1. Events loop



- Scope
- Currying
- Memoization
- Callback function
- ES6 Class
- Prototype
- Recursion
- Hoisting
- First-class objects
- IIFE
- Closures
- Module Pattern
- Apply, call, and bind
- Polymorphism
- Asynchronous
- Promises
- Async & Await



- http://pythontutor.com/javascript.html#mode=edit
- https://tylermcginnis.com/javascript-visualizer/
- https://developer.mozilla.org/en-US/docs/Glossary


----

1. Object Creation
   1. Create an object
   ```javascript
   const newObject = {}
   const newObject = Object.create(Object.prototype)
   const newObject = new Object()
   ```
   1. Adding keys and values to object
   ```javascript
   // 1. Dot syntax
   // set
   newObject.someKey = 'Hello World'
   // get
   const value = newObject.somekey
   
   // 2. Square bracket syntax
   //set
   newObject['someKey'] = 'Hello World'
   // get
   const value = newObject['someKey']
   
   // 3. Object.defineProperty
   // set
   Object.defineProperty(newObject, 'someKey', {value: 'Hello World', writable: true, enumerable: true, configurable: true})
   
   // wrapping it with a function
   const defineProp = (obj, key, value) => {
       Object.defineProperty(obj, key, {
           value,
           writable: true,
           enumerable: true,
           configurable: true
       })
   }
   
   // using the defineProp function
   const person = Object.create(Object.prototype)
   
   defineProp(person, 'car', 'Ferrari')
   defineProp(person, 'dateOfBirth', '1981')
   defineProp(person, 'hasBeard', false)
   
   // 4. Object.defineProperties
   // set
   Object.defineProperties(newObject, {
       'somekey': {
           value: 'hello world',
           writable: true
       },
       'anotherKey': {
           value: 'foo bar',
           writable: false
       }
   })
   ```
   1. Using create method to inherit
   ```javascript
   const drriver = Object.create(person)
   defineProp(drive, 'topSpeed', '100mph')
   console.log(driver.dateOfBirth) // inherited from person
   console.log(driver.topSpeed)
   ```
1. Constructors
   ```javascript
   const Car = (model, year, miles) => {
      this.model = model
      this.year = year
      this.miles = miles      
   }
   
   Car.prototype.toString = () => `${this.model} has done ${this.miles} miles`
   
   // using class
   
   class Car = {
      constructor(model, year, miles) {
         this.model = model
         this.year = year
         this.miles = miles  
      }
      toString = () => `${this.model} has done ${this.miles} miles`
   }
   
   const civic = new Car('Honda Civic', 2009, 20000)
   const mondeo = new Car('For Mondeo', 2010, 5000)
   console.log(civic.toString())
   console.log(mondeo.toString())
   ```
1. Object Literals
   ```javascript
   const myObjectLiteral = {
      variableKey: variableValue,
      functionKey: () => {}
   }
   
   myObjectLiteral.property = 'someValue'
   ```
1. The Module Pattern
   ```javascript
   // selfcontained module
   const testModule = const testModule = (() => {
      let counter = 0;
      return {
         incrementCounter: () => counter++,
         resetCounter: () => {
            console.log(`coutner value prior to reset: ${counter}`)
            counter = 0
         }
      }
   })();

   // usage
   testModule.incrementCounter()
   testModule.resetCounter()
   ```

   ```javascript
   const Namespace = (() => {
     // Module pattern template
     let myPrivateVar, myPrivateMethod

     // a private counter variable
     myPrivateVar = 0

     // a private function which logs any arguments
     myPrivateMethod = foo => console.log(foo)

     return {
         // a public variable
         myPulicVar: 'foo',

         // a public function utilizing privates
         myPublicFunction: bar => {
            myPrivateVar++

            // Cal our private method using bar
            myPrivateMethod(bar)
         }         
     }
   })()
   ```

1. The Revealing Module Pattern
   ```javascript
   const myRevealingModule = (() => {

      let privateVar = "Ben Cherry",
         publicVar = "Hey there!";

      const privateFunction = () => {
         console.log(`Name: ${privateVar}`);
      }

      const publicSetName = strName => {
         privateVar = strName;
      }

      const publicGetName = () => {
         privateFunction();
      }

      // Reveal public pointers to
      // private functions and properties

      return {
         setName: publicSetName,
         greeting: publicVar,
         getName: publicGetName
      };

   })();
 
   myRevealingModule.setName( "Vini" );
   ```
