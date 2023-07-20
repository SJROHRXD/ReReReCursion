# What Even Is Recursion?

### Analogy 1

You're in line at an ATM:

"How many people are in front of me in this line?"
"I could step out of line and run to the front and count, store these counts in a notebook - external variable - but this is a lot of work."
"How can I be lazy? What's the least amount of work I can do?"

Tap on girl's shirt in front of me, ask, "Hey, what number are you?"
"I don't know, but I will ask the woman in front of me."
This continues until we hit this stopping condition.

Stopping condition = Whoever is using the ATM currently.

If he's "Number 1," which personally I think should be zero, but anyway, the next person is "1 + 1."

1. What's the least amount of work can I do?
2. When is the process completed / what's my stopping condition?

        function getMyPositionInLine(person) {
            if (person.nextInLine == null) {
                return 1;
            }
            return 1 + getMyPositionInLine(person.nextInLine);
        }

If the next person in line is null, we must be the next person in line.
"We are calling ourselves, but the parameter we condition on further progresses us..."

How can I take some large problem, and break it down into a bunch of sub-problems?

### Analogy 2

Write and essay, submit to professor, and the professor denies it - you continue to do this until you obtain an acceptable grade.

        function revise(essay) {
            read(essay);
            get_feedback_on(essay);
            apply_changes_to(essay);
            revise(essay) unless essay.complete?;
        }

## What is Recursion

Recursion is nothing more than a method that calls itself.

When you hit some conditional, you can stop recursing.

Base Case

        function getMyPositionInLine(person) {
            if (person.nextInLine == null) {
                return 1;
            }

Recursive Call

            return 1 + getMyPositionInLine(person.nextInLine);
        }

## Why and Why Not

Pros:
- Bridges the gap between elegance and complexity
- Reduces the need for complex loops and auxiliary data structures (implicit stack)
- Can reduce time complexity easily with *memoization*
- Works well for recursively defined data structures - JSON Objects, Trees, Graphs
- 

Cons:
- Slowness due to CPU overhead (Method calls on the call stack - slow)
- Can lead to "out of memory" errors / stack overflow™ exceptions
- Can be unnecessarily complex if poorly constructed
- 
- 

