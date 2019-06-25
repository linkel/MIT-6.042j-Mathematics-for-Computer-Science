# Binary Relation

Are two variables with assigned values equal? Is one bigger than the other? Do they have a common divisor? Is the first a member of the second if the second's a set? Is the first the domain of the second if the first is a set and the second is a function? How are they RELATED???? 

These are examples of binary relations. 

Let's get ready to think about some terminology and then some EQUIVALENCE RELATIONS and PARTIAL ORDERS.

## Relations and Functions

Def 1.1:
A binary relation R consists of:
- a set A called the domain of R, 
- a set B called the codomain of R, and
- a subset of A X B called the graph of R. 

Example: "is teaching relation". 
Domain is the names of all the teaching staff.
Codomain is equal to all the subject numbers in the current catalogue. 

Graph looks like
{(Teacher A, 6.042), (Teacher B, 18.062), (Teacher A, 18.062), (Teacher C, 6.046)}

and et cetrea. 

Look, Def 1.1 is the same as a definition of a function, except that it doesn't require that for each domain element there's at most one pair in the graph that has that domain element as its first coordinate. 

A function is a special case of a binary relation. 

A relation whose domain is A and codomain is B is said to be "between A and B" or "from A to B". If domain and codomain are same set, then the relation is "on A". 

"a R b" means the pair a,b is in the graph of R. 

Not totally sure what that means but I guess I'll find out. 

## Notation - Image and Inverse Image

If R is a binary relation from A to B and C is any set, define:

CR ::== {b \in B | cRb for some c \in C}
RC ::== {a \in A | aRc for some c \in C}

The set CR is called the image of C under R. 

If R's a function, then R(C) also describes the image of C under R. 

The set RC is the inverse image of C under R. R(C) = CR, but it doesn't equal RC. Doesn't work for function. 

## Surjective

A relation where every codomain element is related to some domain element is called a surjective relation. 

A relation where every domain element is related to a codomain element is called a total relation. R is total iff A = RB. 

## Equivalence Relations

If we care about some property of the objects but not of the objects themselves, we say they are equivalent. This is an equivalence relation. 

Congruent triangles are those with the same three lengths of sides. Iff they have the same three lengths of sides they are congruent. 

Similar triangles are those with the same three sizes of angles. Iff they have the same three sizes of angles, they are similar. 

Representation-equivalence is the relation between representations of the same abstract data type. If we had an unsorted list of numbers and they had the same numbers in them, they'd be equivalent. 

(2, 4, 1, -3) and (-3, 4, 1, 2) are equivalent. 

## Equivalence by Function

If we assume there's some function that extracts the angles, size, color, or other property of the two elements we're looking at, and the function extracts the same value for each, then those two elements are equivalent. 

Given any total function f with domain A, the binary relation "triple equals sub f" on A is defined as 

a "triple equals sub f" b iff f(a) = f(b)

for all a, b \in A.

A binary relation is an equivalence relation iff it equals that triple equals sub f for some f. 

Show that the equality relation on elements of a set A is actually an equivalence relation according to the above definition by describing an I: A ==> A such that equality is triple equals sub I. 

The set A is made up of elements. The elements can be grouped into subsets of A. Each element in set A is equal to itself, so it's reflexive. Each element x in A if joined in a set with another element y would be the same set if element y was joined with element x, so it is symmetric. If x and y are in a subset B, and y and z are in a subset B, we know that x and z are in a subset B. So they're transitive. So this relation is an equivalence relation. 

I think. 


