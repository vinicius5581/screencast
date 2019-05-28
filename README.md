# screencast

## Tipos

1. Entrevistas com profissionais
   1. Como é o dia a dia na empresa onde você trabalha?
   1. Como foi a sua jornada até aqui?
   1. Que dicas voce daria para quem esta no Brasil e buscando uma carreira fora?
   
1. Design Patterns
   1. Categorias
      1. Creational
      1. Structural
      1. Behavioral
      

1. Algoritimos


## Technical reviewers 

----

1. Constructor
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
   
   2. Square bracket syntax
   //set
   newObject['someKey'] = 'Hello World'
   // get
   const value = newObject['someKey']
   
   3. Object.defineProperty
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
   
   4. Object.defineProperties
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
