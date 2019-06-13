# Induction

My friends, principle of induction is when you have a predicate, P(n), and 
1. if P(0) is true and 
2. for all n in N, P(n) implies P(n+1), 

then P(n) is true for all n in N. 

Notes talk about all students getting candy because of saying student 0 gets candy and if student n gets candy then student n+1 will too. 

So how the hell do I use this? 

# Using Induction

It's the strongest and most common proof technique, says the notes. 

Use of induction is a defining! characteristic! of DISCRETE math. This is in opposition to CONTINOUS math. 

Let's look at a classic formula. 

Notes gives the formula for calculating the sum of i where i is numbers from 1 to n. How can we use the induction principle to prove this? 

We need to prove that P(0) is true. Then we prove that for all n in N, P(n) implies P(n+1). 

Okay, so P(0) in our case is saying that a sum of 0 is equal to 0(0+1)/2. That's 0. So that's good.

How do we prove that for all n in N, P(n) implies P(n+1)? 

Assume the left, and prove the right. 

Let's assume P(n) and see if we can prove P(n+1)

So first we just write down the left and right, which was P(n). Then we wrote down what it'd be if it was P(n+1), just plugging in n+1 for that right hand side. Finally we went back to P(n) and just added n+1 to both sides. We saw that they're the same. So we are good now because we've shown it's true for n and true for n+1, and the argument we made is valid for every natural number n. So we satisfied the two requirements for proving it. 

Hmm, I'm still a bit confused on how that was enough. 

# A Template for Induction Proofs

1. State that the proof uses induction.
2. Define an appropriate predicate P(n). The induction hypothesis. If it's got multiple variables, make clear which is n. 
3. Prove that P(0) is true. Base case. 
4. Prove that P(n) implies P(n+1) for every natural number n. Inductive step. Well, this is the hard part, honestly. 
5. Invoke induction. Conclusion. 

# Clean Writeup

Dang, that's short. I feel like I need tons of explanation in my own head to understand the steps right now. 

# Fibonacci example

Fib numbers are defined recursively by the rules:

F0 is 0,
F1 is 1,
Fi is F subscript i-1 + F subscript i-2, for i bigger than or equal to 2.

0, 1, 1, 2, 3, 5, 8, 13, 21...

For all n bigger or equal to 0, F sub 0 squared plus F sub 1 squared onwards to F sub n squared is equal to F sub n times F sub n+1.

Induction hypothesis is then the sum of F sub i squared from 0 to n is equal to F sub n times F sub n+1. 

Okay, so we know that for all n bigger or equal to zero, the fibonacci equation holds by definition. That's F sub n + F sub n+1 equals F sub n+2. 

We can actually multiply both sides by F sub n+1 and then rearrange the term to give us that f squared sub n+1 term, which would be the last term of that sum of squared Fs if we added it to it. So we have the equation, we add it to the induction hypothesis one, and it pops out with what we wanted to assert about the sum from 0 to n+1 of the F sub i squared. 

We figured out how to pick that term from playing around with the induction hypothesis and the predicate P(n+1), where we subtracted the equation off of the other to get that equation that I originally stated we'd stick inside the induction hypothesis one in the earlier paragraph. 

Man typing this probably has ZERO CLARITY for reading purposes, but I wrote the steps out on scratch paper to understand the notes, so it's fine. This is just to document my thought process. 

I don't know that I'd be clever enough to think of subtracting the eq from the other to come up with the bridge to the gap, and then inserting it in the right spots. I can follow this but I don't know that I can write a proof for something new yet on my own. 

That's pretty cool though. 

# Induction as a Reasoning Tool

This section's example shows a courtyard grid with dimensions 2^n x 2^n. 

In the special case n = 0, the entire courtyard is just one square--otherwise there's four central squares. 
The example says that a central square will have a statue. However, this courtyard is tiled with L shaped tiles that consist of three squares. 

For larger values of n, is there a way to tile this courtyard with L-shaped tiles and a statue in the center? 

We have a theorem 2.3:
For all n bigger than or equal to zero, there exists a tiling of a 2^n x 2^n courtyard with state in a central square. 

## Doomed attempt at proof

We might try...

Let P(n) be the proposition that there exists a tiling of a 2^n x 2^n courtyard with statue in the center. 

Base case: P(0) is true because statue fills the whole courtyard. 

Inductive step: Assume that there is a tiling of a 2^n x 2^n courtyard with statue in the center for some n greater than or equal to 0. We must prove that there is a way to tile a 2^(n+1) x 2^(n+1) courtyard with statue in the center. 

Whoa, I guess being able to tile a small courtyard with the statue in the center doesn't help me with tiling a larger one. Don't know how to bridge this gap between P(n) and P(n+1). What the heck do we do then?

Look for a stronger induction hypothesis...one that implies the previous one. 

How about a P(n): For every location of Bill in a 2^n x 2^n courtyard, there exists a tiling of the remainder. 

## Successful attempt at proof

Let P(n) be the proposition that for every location of Bill in a 2^n x 2^n courtyard, there exists a tiling of the remainder. 

Base case: P(0) is true because statue fills the whole courtyard. 

Inductive step: Assume that P(n) is true for some n greater than or equal to 0. That is, for every location of statue in this courtyard, there exists a tiling of the remainder. Divide the 2^(n+1) x 2^(n+1) courtyard into four quadrants, each 2^n x 2^n. One quadrant contains statue. Place a temporary statue in each of the three centra squares lying outside this quadrant. We can tile each of the four quadrants by the induction assumption. Replacing the three temporary statues with the single L-shaped tile now leaves us with one statue again. Looks like P(n) implies P(n+1) for all n bigger than or equal to zero. Our theorem follows as a special case. (Is it the case of when the statue is only in the central squares?)

I'm not sure how much I understand this! Why is it that having the statues in the central square, then replacing them with the L tile, also imply that the statue in that upper right central subsection can be moved to that gap in the L shaped tiles and also tile the rest of it acceptably?