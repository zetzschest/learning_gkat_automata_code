# Guarded Kleene Algebra with Tests: Automata Learning
> Guarded Kleene Algebra with Tests (GKAT) is the fragment of Kleene Algebra with Tests (KAT) that arises by replacing the union and iteration operations of KAT with predicate-guarded variants. GKAT is more efficiently decidable than KAT and expressive enough to model simple imperative programs, making it attractive for applications to e.g. network verification. In this paper, we further explore GKAT’s automata theory, and present GL∗, an algorithm for learning the GKAT automaton representation of a black-box, by observing its behaviour. A complexity analysis shows that it is more efficient to learn a representation of a GKAT program with GL∗ than with Angluin’s existing L∗ algorithm. We implement GL∗ and L∗ in OCaml and compare their performances on example programs.

## About this repository

This repository allows one to compare, for any GKAT expression e, the number of membership queries to its language semantics [e] required by GL∗  for learning a GKAT automaton representation of *e*, with the number of membership queries to [e] required by L∗ for learning a Moore automaton representation of e. For each run, we output, for both algorithms, a trace of the involved hypotheses as tables in the .csv format and graphs in the .dot format, as well as an overview of the numbers of involved queries in the .csv format. 

### Example 1: 

In [ife_results](ife_results) we present the results for the expression e =  **if** t1 **then** p1 **else** p2, the primitive actions {p1, p2, p3}, and primitive tests {t1,...,tn} parametric in n = 1,...,9. We find that GL∗ outperforms L∗ for all choices of n. The difference in the number of membership queries increases with the size of n. For n = 9 the number of atoms is 2^9, resulting in an already relatively large number of queries for both algorithms.
