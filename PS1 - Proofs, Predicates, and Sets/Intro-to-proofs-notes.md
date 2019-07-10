# Intro to Proofs

## Some definitions

Proposition: a statement that can be true or false. 

Predicate: a proposition whose truth depends on value of 1 or more variables.

That'd be something like... "N is a perfect square." This states something that can be true or false, but it depends on the variable N. 

Now if I revealed that N = 4, then it becomes "4 is a perfect square" and this proposition is true. 

Axiom: A proposition that is accepted as true. 

Proof: A sequence of logical deductions from axioms and previously proved statements. 

Theorem: A true proposition.

Lemma: A preliminary proposition useful for proving later propositions.

Sometimes lemmas can end up way more important than the proposition they later prove.

Corollary: A proposition that follows in just a few logical steps from a theorem.

## Logical Deductions

There's something called a modus ponens. It's a proof of P together with proof that P implies Q, which makes it a proof of Q. 

Can be written like...

P, P implies Q
______________
Q

Where the top part is the antecedent(s) and the bottom is the consequent (also known as conclusion).

Likewise, 

NOT(P) implies NOT(Q)
____________________
Q implies P

But be aware that NOT(P) implies NOT(Q) does NOT make P implies Q. Common error. 

## Patterns of Proof

Here are some methods for making proofs. 

### Method 1

1. Assume P.
2. Show that Q logically follows.

In the book example, they have an equation that is said to be bigger than 0 for values between 0 and 2, inclusive. They show that you can factor part of the equation and describe that each individual factored piece is nonnegative. Then point out that the product of those terms must also be nonnegative. Adding 1 to the product always gives a positive number, so it proves that the whole equation is > 0. 

### Method 2

Prove the contrapositive. P implies Q is logically the same as NOT Q implies NOT P.

1. We prove the contrapositive. State the contrapositive.
2. Go to Method 1. 

Book gives example on "If r is irrational then square root of r is also irrational."

We prove the contrapositive. If the square root of r is rational then r is rational. 

Assume that square root of r is rational. There exist integers m and n such that square root of r is equal to m / n. Square both sides, you get r = m squared / n squared. They are still integers, so r is rational. 

## If and only if

P iff Q is basically P implies Q, Q implies P. So they're both connected both ways. 

### Method 1

1. We prove P implies Q and vice versa.
2. First we show P implies Q.
3. Now we show Q implies P. 

### Method 2

Construct a chain of iffs. 

Book has a cool example involving proving that standard deviation of a sequence of values x, ...xn is 0 iff all vals are equal to the mean. 

Square of real numbers always non negative, so every term on the left side is nonneg. And that holds if every term on L is zero. Term (x - u)^2 is 0 if and only if x = u. So that statement is true only if every x = mean. 