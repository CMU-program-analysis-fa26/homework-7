# Inductive Program Synthesis (HW7)

Programming by Example (PBE) is the process of generating a program from a set of input-output pairs (or examples). In PBE, the goal is learn a program that can generalize from the given examples and produce correct outputs for inputs not seen before.

In this question, you are going to synthesize two simple function using Z3, an SMT (Satisfiability Modulo Theories) solver. 
Given a set of input-output pairs, your goal is to construct a Z3 formula that represents the constraints imposed by these examples. The Z3 solver will then attempt to find a solution that satisfies all of the constraints. The solution to the formula corresponds to a function that satisfies the input-output pairs.

To accomplish this, you will need to create Z3 variables and expressions that represent the possible operations, and use them to construct constraints based on the input-output pairs.


## Set up

Set up the Python interface for Z3 using `pip install z3-solver` or use Codespaces


## Question 3 

### Function Specification:

The function will take four ORDERED inputs, and produces an output. Based on magic intuition, we know the following about the function:
1. It only uses the operations *, <<, +, and |
2. You may assume that each input is used only once in the expression
3. All values (inputs and outputs) are 16-bits wide

### Function IO Pairs:
   IN: (11, 6, 9, 4)    OUT:  35840  
   IN: (9, 12, 10, 1)   OUT:  46080  
   IN: (2, 4, 0, 4)     OUT:     12  
   IN: (14, 8, 10, 3)   OUT:  52224  
   IN: (1, 13, 9, 4)    OUT:   6656  
   IN: (4, 2, 8, 0)     OUT:   2048  
   IN: (15, 6, 12, 4)   OUT:  57344  
   IN: (7, 12, 6, 0)    OUT:   5376  
   IN: (2, 0, 6, 0)     OUT:      0  
   IN: (16, 4, 3, 1)    OUT:    520  `


You can use the template in `problem.py` to help you get started!


The main steps of the synthesis process are as follows:

- Define Z3 variables and expressions for the possible operations.
- Add a constraints to only allow one operation to be part of the solution.
- Add constraints for each input-output pair.
- Solve the Z3 formula to synthesize the function.


# Resources

- [Python Z3 examples](http://ericpony.github.io/z3py-tutorial/guide-examples.htm)
- [Python API](http://z3prover.github.io/api/html/namespacez3py.html)
- [Programming Z3, a guide](http://theory.stanford.edu/~nikolaj/programmingz3.html)
