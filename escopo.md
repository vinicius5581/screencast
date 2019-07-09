Escopo
Onde uma variabvel esta disponivel no codigo
___

- Syntax Parsers
- Execution Contexts
- Lexical Environmnents

- Execution Context (Global (not inside a function)) - (Wrapper around code)
   - Global Object (on the browser its window (window object))
   - this ( on the global context, it points to window)
   - Outer Environment (nothing on the global level)
   - Execute Code
   
 
- Create execution context and hoisting

- Create execution
  - Creation Phase
    - Global Object
    - this
    - Outer environment
    - Hoisting (Setup memory space for vars and functions)
  - Execution Phase
    - Global Object
    - This
    - Outer enviroment
    - Execute code line by line
   

- single threaded and synchronous execution

single threaded: one command at a time
synchronous execution: one at the a time and in order

----

- Function invocation and the execution stack


- Invocation: running a function or calling a function. Done by using parenthesis()


- Functions, contexts and variable environments

- variable environments : where the variables live and how they relate to each other in memory

https://www.dropbox.com/s/o4m4mzppg8dc7pc/Screenshot%202019-07-08%2023.03.27.png?dl=0


---

The scope chain

Scope, ES6 and let



---
Esc

Global scope

Block scope

Function scope

code -> syntax parser -> JIT compilation (dynamic translation)

Lexical environment (escope)

Execution context




Lexical execution
Execution call stack

Global
Local



https://medium.com/@js_tut/javascript-tutorial-lexical-environment-3ee161bb2295
