# Call Stack

### Task Deviation

- Check eMail?
- Boss interrupts.
    - Task deviation. (ADHD Fatality 🐱‍👤 KO!)
- Impress Investors.
    - Task deviation. (ADHD Fatality 🐱‍👤 KO!) x2
- Help Jake Code.
    - Task deviation. (ADHD Fatality 🐱‍👤 KO!) x3

### Stacks 💵

        function A() {
            return "hello "+ B();
        };

        function B() {
            return "my "+ C();
        };

        function C() {
            return "friends!";
        };

        console.log(A());

1. A returns a string, but has depedency on B
2. B returns a string, but has dependecy on C
3. C just returns a string

#### Call Stack:
- I want to execute A but..
- In order to call `hello` and concatenate `B()`
- I need to call `B()`
- I want to execute B but..
- In order to call `my` and concatenate `C()`
- I need to call `C()`
- I cannot return or pop things off the stack until...
- I return `friends!`
- `B()` is fully evaluated, I can return that value to the `B()` method invocation
- and so on until `Hello my friends!`

#### Stack Frame:
`"friends!"`  
`"my " + C`  
`"hello" + B`  

### Call Stack Without Recursion

        function A() {
            return A();
        };

*oh, dear god*

#### Error: Stack Overflow

> This exception happens when we exceed the preallocated buffer of memory that our program has

Must return value, must stop invoking methods.