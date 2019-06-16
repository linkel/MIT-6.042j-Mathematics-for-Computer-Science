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

# Faulty Induction Proof Example

False theorem: All horses are the same color. 

Okay, so we need to reformulate this assertion because there's no n in it--we need to make the n explicit. Maybe this is a thing that will usually be done in some other proof examples. 

So we'll formulate it like so:
In every set of n >= 1 horses, all are the same color. 

Since it's a statement about all integers greater or eq to 1, it's fine to prove P(1) is the base case and then prove that P(n) implies P(n+1) for all n greater than or equal to one in the inductive step. 

Proof by induction:

Base case for n = 1 is P(1) is true, since in a set of horses of size 1, there's only one horse and the horse is the same color as itself. 

Inductive step: Assume P(n) is true for some n bigger than or equal to 1. That is, assume that in every set of horses, all are the same color. Now consider a set of n + 1 horses:

h1, h2, ... , hn, hn+1

By our assumption, the first n horses are the same color. 
```
h1, h2, ..., hn, hn+1
|--------------|
```

By our assumption, the last n horses are the same color. 

```
h1, h2, ..., hn, hn+1
    |----------------|
```

Therefore all horses must be the same color! 

Where's the error?

It is in the sentence saying that "therefore, horses h1, h2, ... hn, hn+1 must all be the same color." The ellipses looks like the sets (in my two above code blocks) overlap. But actually, the first set is h1, and the second set is h2, and there is no overlap. 

We proved P(1), and we did prove P(2) --> P(3), and onwards. But we never proved P(1) ---> P(2).

# Strong Induction

Both strong and regular induction are used for the same purpose. They prove that a predicate P(n) is true for all n in N. 

## Principle of strong induction

Let P(n) be a predicate.

1. If P(0) is true and
2. for all n in N, P(0), P(1), ..., P(n) together imply P(n+1)

then P(n) is true for all n in N. 

Strong induction lets me assume more stuff. So if regular induction isn't enough for a proof that feels like it can be proved with induction, maybe strong induction is what I want? 

# Products of Primes example

Lemma 3.1:
Every integer greater than 1 is product of primes. 

Any number is considered to be a product consisting of one term. Every prime is considered to be a product whose terms are all primes. 

We'll prove Lemma 3.1 by strong induction. The induction hypothesis will be:
n + 2 is a product of primes. 

So the lemma will follow if prove that P(n) holds for all n greater or equal to 0. 

Base Case: P(0) is true because 0 + 2 is prime, and so that is also a product of primes by that convention stated up above. 

Inductive step: Suppose that n greater than or equal to 0 and that i + 2 is a product of primes for every natural number i < n + 1. We must show that P(n+1) holds, namely, that n + 3 is also a product of primes. 

So if n+3 is prime, then it's a product of primes by convention as well. But if it isn't, then n + 3 must be equal to k * m for some natural numbers k and m (since you can divide it by something that isn't itself or 1). So 2 is less than or equal to k and k is less than n + 3 since we can divide it down. Same goes for m. 

So k - 2 is a natural number less than n + 1 (because n + 3 we just said is bigger than k when we're talking about k*m where n is not one of them and 1 is not one of them, so subtracting 2 from k is smaller since n + 3 - 2 is n + 1). 

That means that (k - 2) + 2 is a product of primes, since k - 2 is something smaller than n + 1 and we said that n + 2 is a product of primes for our induction hypothesis.

Though I'm getting kind of confused here. 

So if k is a product of primes due to the induction hypothesis and m is also a product of primes, then km = n + 3 is also a product of primes. Therefore P(n+1) holds here too. 

Any theorem that can be proved by strong induction can be proved with regular induction using a more complex induction hypothesis. If P(n) is sufficient to prove P(n+1) then regular induction is fine and simpler.

# Making Change example

6, 10, and 15 unit value coins. 

This country that has coins of the above value can make change for any number of unit values greater than 29. 

Strong induction makes this easy to prove for n + 1 > 35, because (n+1) - 6 > 29, so by strong induction they can make change for ((n+1) - 6) unit value, and can add a 6 coin in to get (n+1). 

What's left is to prove that they can make change for all amounts from 30 to 35. 

## Vacuous truth

If n > 29, then there is a collection of coins whose value is n Strongs (their unit of currency). 

When a hypothesis of an implication like above is false, we know the whole implication is true--vacuously true. So P(n) will be vacuously true whenever n <= 29.

## Back to proving it

So using that above as P(n), we look at the base case.

Base case: P(0) is vacuously true. 

Inductive step: We assume that P(i) holds for all i <= n and prove that P(n+1) holds, we argue by cases.

Case (n + 1 <= 29): P(n+1) is vacuously true.
Case (n + 1 = 30): P(30) holds because 5 x 6 coins gets here. 
Case (n + 1 = 31): 6 + 10 + 15.
Case (n + 1 = 32): 10 + 10 + 6 + 6
Case (n + 1 = 33): 15 + 6 + 6 + 6
Case (n + 1 = 34): 10 + 6 + 6 + 6 + 6
Case (n + 1 = 35): 10 + 10 + 15
Case (n + 1 = 36): Add a 6 coin to the 30 case. Beginning of the strong induction steps. 
So for everything above 35, they can just add a 6 coin to any previous case. 

So P(n+1) is true, and we conclude by strong induction that for all n > 29, they can make change for n strongs. 

The proof also yields a recursive procedure for making change. They can make change for any amount greater than 29 using only one 15 coin, at most 2 10's, and lots of 6 coins. 

# Unstacking example

Begin with a stack of n boxes. Make a sequence of moves. In each move, divide a stack into two nonempty stacks. 

Game ends when I have n stacks, each containing a single box. 

If I divide 1 stack of height a + b into two stacks with heights a and b, I score a*b points for that move. Overall score is sum of the points earned for each move. 

Seems like my strategy would be to make sure I separate stacks into as even separations as possible. 4*5 would get me 20 which is preferred over 8 * 1. 

WAIT NO

Score's determined by the number of boxes. Dammit! 

Theorem 3.2:

Every way of unstacking n blocks gives a score of n*(n - 1) / 2 points. 

## Analysis

So it's okay to adjust indices by the way. We can prove P(1) in the base case and then prove that P(1) ... P(n-1) imply P(n) for all n greater than or equal to 2 in the inductive step.

Proof:

Proof is by strong induction. Let P(n) be that above proposition I wrote down in Theorem 3.2. 

Base case:

If n = 1 then there's only one block. No moves are possible so the score is 0. P(1) is true. 1(1-1)/2 = 0. 

Assume that P(1) ... P(n - 1) are all true and that we have a stack of n blocks. The first move must split the stack into substacks with sizes k and n - k for some k between 0 and n noninclusive. 

Now the total score for the game is the sum of points for this first move plust points obtained by unstacking the two resulting substacks. Yep. 

Total score is equal to (score for 1st move) + (score for unstacking k blocks) + (score for unstacking n - k blocks).

Not gonna write this equation down, but adding these three parts seems to simplify back down to n(n-1)/2. 

We use P(k) and P(n-k) in the equations. 

# Well Ordering Principle

Every nonempty subset of natural numbers has a smallest element. 

Note that you can transform any proof using the Well Ordering Principle into a proof using Strong Induction and vice versa. 

Well-ordering proofs tend to be shorter than induction but usually need proof by contradiction. 

