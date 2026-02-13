# Lab 04 - SOP/POS and KMaps - Aiden Smith, Max Martinez (Group 44)

In this lab, you’ve learned how to apply KMaps, Sum Of Products and Products of
sums to simplify digital logic equations. Then, you’ve proven out that they work
using an implemented design on your Basys3 boards.

## Rubric

| Item | Description | Value |
| ---- | ----------- | ----- |
| Summary Answers | Your writings about what you learned in this lab. | 25% |
| Question 1 | Your answers to the question | 25% |
| Question 2 | Your answers to the question | 25% |
| Question 3 | Your answers to the question | 25% |

## Lab Summary

In this lab, we implemented a logic function in 3 different ways:
- The unoptimized (naive) implementation (naive.v): In this implementation, we looked at each line on the truth table with an output of 1, ANDed the inputs for each of those lines together, and ORed each line's equations together.
- The minterm SOP implementation (minterm.v): A more optimized implementation, made from a k-map of the truth table, and using the minterms to encode a SOP equation.
- The maxterm POS implementation (maxterm.v): Another optimized implementation from a k-map, but this time, using the maxterms to encode a POS equation.
Then, after synthesizing the full design testing each of the implementations at once (top.v), we examined the schematic, which showed that our function was implemented in actual hardware using LUTs on the board.

## Lab Questions

### Why are the groups of 1’s (or 0’s) that we select in the KMap able to go across edges?
K-maps are arranged so that adjacent cells differ by only one input bit. Groups that wrap around the edges also have a one bit difference between their cells the same way that non-wrapping groups do, which is why wrap-around grouping is allowed.

### Why are the names Sum of Products and Products of Sums?
They're called sum of products because in boolean algebra, the OR operation behaves like a sum, the AND operation behaves like a product, and SOP equations take the form of groups of ANDed inputs (products) ORed (summed) together.
Products of sums get their name because they take the form of groups of ORed inputs (sums) ANDed (multiplied) together.

### Open the test.v file – how are we able to check that the signals match using XOR?
test.v can check that signals match expected values using XOR because the output of XOR depends on the equality of its inputs. A XOR B is 0 when A == B, and it is 1 when A != B, so it can be used to test for equality between two bits.
