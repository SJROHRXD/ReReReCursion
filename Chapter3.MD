# Strings

https://youtu.be/IJDJ0kBx2LM?t=1021

### Recursion with Strings
- Manipulating input parameters on call stack recursively
- input: the simple engineer
- output: reenigne elpmis eht // reverse order

- How do we build really concise recursive function that gives us this

        function reverseString() {
            // What is base case? When can I no longer continue?
            // What is smallest amount of work I can do in each iteration? Between each invocation, what's the smallest unit I can modify to get us closer to goal
        }

- Smallest input I can pass in, would be one letter, or essentially, one array element by index
- Lazier! The empty string

        function reverseString(input) {
            if ( input === "" ) {
                return input;
            }
            // other logic
        }

- Whittle down decision space within each recursive call
- What's the smallest unit I can deal with within a string?
- A string is just a bunch of characters, so maybe I can modify a single character - let me pick a character out of the string, and maybe where I position it, we can concatonate in reverse order???

        function reverseString(input) {
            if (input === " ") {
                return "";
            }
            if (input.length === 0) {
                return input;
            }
            return reverseString(input.substring(1)) + input.charAt(0);
        }

