
**Validation includes:**
1. **Formal reasoning** about a program, usually called ==_verification_==. Verification constructs a formal proof that a program is correct.
2. **Code review.** Having somebody else carefully read your code, and reason informally about it, can be a good way to uncover bugs.
3. **Testing**. Running the program on carefully selected inputs and checking the results.


## Test-first programming

  
A ==_specification_== (or spec) describes the behavior of a module. For a function, the specification gives the types of the parameters and any additional constraints on them (e.g. `sqrt`’s parameter must be nonnegative). It also gives the type of the return value and how the return value relates to the inputs. In TypeScript code, the specification consists of the function signature and the comment above it that describes what it does.

  
A ==_test case_== is a particular choice of inputs, along with the expected output behavior required by the specification.

A ==_test suite_== is a set of test cases for a module

1. **Spec**: Write a specification for the function.  
    
2. **Test**: Write tests that exercise the specification.  

3. **Implement**: Write the implementation.  


##   Systematic testing
1. correct 
		A correct test suite is a legal client of the specification, and it accepts all **legal implementations** of the spec without complaint. This gives us the freedom to change how the module is implemented internally without necessarily having to change the test suite.
2. thorough
3. small


## Choosing test cases by partitioning
  
The idea behind subdomains is to divide the input space into sets of similar inputs on which the program has similar behavior. Then we use one representative of each set. This approach makes the best use of limited testing resources by choosing dissimilar test cases, and forcing the testing to explore areas of the input space that random testing might not reach.

####   Example: `abs()`
```ts
/**
 * ...
 * @param a  the argument whose absolute value is to be determined
 * @returns the absolute value of the argument.
 */
function abs(a: number): number
```

**abs : number → number**

![[Pasted image 20250314134139.png]]

```ts
/**
 * ...
 * @param a  an argument
 * @param b  another argument
 * @returns the larger of a and b.
 */
function max(a: number, b: number): number
```

**max : number × number → number**

![[Pasted image 20250314135414.png]]
```ts
partition: a < b; a > b; a = b
```

### Include boundaries in the partition

## Black box and glass box testing

==**Black box testing**== means choosing test cases only from the specification, not the implementation of the function.

==**Glass box testing**== means choosing test cases with knowledge of how the function is actually implemented.

## Iterative test-first programming

1.   Write a specification for the function.
2.  Write tests that exercise the spec. As you find problems, **iterate** on the spec and the tests.
3.  Write an implementation. As you find problems, **iterate** on the spec, the tests, and the implementation.

**Plan for iteration:**
1. For a large specification, start by writing only one part of the spec, proceed to test and implement that part, then iterate with a more complete spec.
2. For a complex test suite, start by choosing a few important partitions, and create a small test suite for them. Proceed with a simple implementation that passes those tests, and then iterate on the test suite with more partitions.
3. For a tricky implementation, first write a simple brute-force implementation that tests your spec and validates your test suite. Then move on to the harder implementation with confidence that your spec is good and your tests are correct.
