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

Congruence Modulo is another kind of equivalence. An integer k and an integer m are congruent modulo an integer n > 1 iff m and k have the same remainder on division by n. This is like that pentagon looking graph you saw in that one explanation of congruent modulo. 

m triple equals k mod n. 

## Partitions

Cutting up a set into a bunch of pieces is called partitioning the set. Each piece is called a block of the partition. 

A partition is a collection of nonempty sets. 

Set A and Partition B with blocks B1, B2, B3...

1. A is equal to the union of all of those blocks together. 

2. If B1 is different from B2 and they're blocks of A, then B1 and B2 are disjoint. 

Basically these blocks are nonoverlapping chunks of A. All of those blocks together is a partition of set A. 

Ex: You can partition the real line into blocks by cutting it at integer points. You can partition pixels in an image according to their color. 

Being in the same block of a partition is an equivalence relation. Any partition then has an equivalence relation we can extract, and we can also define a partition determined by any equivalence relation. If you extract a relation from a partition then use that partition to determine an equivalence relation, you get back the partition you started with. They're interchangeable.

I'm not sure how much I understand this last part. 

### Sameness

You can see that there's a lot of equivalence relations. Really what we're looking at is the sameness of some property of objects. 

## Properties of Equivalence Relations

Reflexive, symmetric, and transitive are the three properties important to think about here. 

For every a in A, if and only if a R a, it's reflective.

For every a and a prime in A, iff a R a prime implies a prime R a, it's symmetric. 

For every a, b, c in A, iff [a R b and b R c] imply a R c, then it's transitive. 

Examples:
- Less than relation. It's transitive, since 4 < 6 and 6 < 8 then do say that 4 < 8. But it isn't reflexive since 4 < 4 is not true, and it isn't symmetric since 5 < 6 does not imply 6 < 5. 
- Proper subset relation. A subset B and B subset C do imply that A subset C. It's transitive. It's not reflexive since proper subsets aren't the same as each other, so A subset A is not true. It's not symmetric since A subset B is not B subset A. 
- Implies relation for math logic. It's not symmetric since A --> B doesn't mean B --> A. It's reflexive since A --> A is valid. It is also transitive, since if A --> B and B --> C then A --> C. 

Let R be the relation on sets, C, D, of natural numbers such that C R D iff C intersects D is finite. This is symmetric but not reflexive. Explain why it is not transitive. 

You can have a set of stuff in a set A that intersects with stuff in set B. Then you can have stuff in set B that intersects with stuff in set C. But it's possible that A's stuff doesn't intersect with C's stuff. Like if A had 2 yellow balls and 3 black balls, B had 3 black balls and 1 white ball, and C has 1 white ball. So it isn't transitive. 

More confusing to me is how the notes say it's not reflexive. I get that it isn't reflexive for N R N because all the natural numbers are infinite and then the intersection is not finite. But what if it's just finite natural numbers like 4, 5, 6, then related with themselves? Isn't that a finite intersection? Or does this have to be true for all possible sets? 




