[[Checking]]
[[Immutability]]
[[SFB]]
[[ETU]]
[[RFC]]

## Static checking, dynamic checking, no checking

**Static checking** can catch:
1. syntax errors
2. misspelled names
3. wrong number of arguments, 
4. wrong argument types
5. wrong return types

**Dynamic checking** can catch:
1. specific illegal argument values.   x/y   0 value
2. illegal conversions
3. out of range indices
4. call undedined

## Mutating values vs. reassigning variables

  
Change is a necessary evil. But good programmers try to avoid things that change, because they may change unexpectedly. Immutability – intentionally forbidding certain things from changing at runtime – will be a major design principle in this course.

Programs have to be written with two goals in mind:

1. communicating with the computer. First persuading the compiler that your program is sensible – syntactically correct and type-correct. Then getting the logic right so that it gives the right results at runtime.
2. communicating with other people. Making the program easy to understand, so that when somebody has to fix it, improve it, or adapt it in the future, they can do so.


**software engineering is not hacking. Engineers are pessimists:**

Good: write a little bit at a time, testing as you go. In a future class, we’ll talk about test-first programming.
Good: document the assumptions that your code depends on.
Good: defend your code against stupidity – especially your own! Static checking helps with that.

## The goal of 6.031

**Safe from bugs**. Correctness (correct behavior right now) and defensiveness (correct behavior in the future) are required in any software we build.

**Easy to understand**. The code has to communicate to future programmers who need to understand it and make changes in it (fixing bugs or adding new features). That future programmer might be you, months or years from now. You’ll be surprised how much you forget if you don’t write it down, and how much it helps your own future self to have a good design.

**Ready for change**. Software always changes. Some designs make it easy to make changes; others require throwing away and rewriting a lot of code.
