---
title: Counting Rudiments
lesson: 1
---

----------------------
Contents:
* TOC
{:toc}
----------------------

I want to lay out some basic logic for counting things: Permutations, combinations, etc.

# Alphabets and Strings

An alphabet is a set of letters $$A = \{\alpha_1, \alpha_2, \cdots, \alpha_n\}$$. The alphabet is has $$n$$ elements like this: $$\|A\| = n$$.

Let's start with the basic concept of a **string**. We **string** together letters in a row, with no restrictions or limitations. If $$A$$ is the English alphabet in standard a-b-c order, then $$\alpha_{18} \alpha_{15} \alpha_{18} \alpha_{9} \alpha_{8}$$ spells the word "rorih".

What if we have an alphabet with only two letters, and we want to write a 2-letter word? How many possibilities are there? Here's a table:

| 1st \ 2nd           | $$\alpha_1$$                                 | $$\alpha_2$$                                 |
| ---------------------------------- | -------------------------------------------- | -------------------------------------------- |
| $$\alpha_1$$                       | $$\alpha_1\alpha_1$$                         | $$\alpha_1\alpha_2$$                         |
| $$\alpha_2$$                       | $$\alpha_2\alpha_1$$                         | $$\alpha_2\alpha_2$$                         |



For your first choice, you have 2 letters to choose from. For your 2nd choice, you have 2 letters to choose from. So there are $$2\times2=4$$ possibilities. If our alphabet had 3 letters you can imagine the $$3\times3$$ version of the table.

How about if $$l=3$$? We can start with the table above, adding $$\alpha_1$$ to the end of each string. Then our table doubles. A 2nd layer comes out of the screen with all the same strings augmented by $$\alpha_2$$. The possibilities are $$2\times2\times2 = 8$$.

To add a fourth letter, we take our "cubed" table and repeat the doubling process to get $$2\times2\times2\times2 = 16$$ possible strings.

The generalization goes like this: How many possible strings exist of length $$l$$, in an alphabet of size $$n$$? The answer is given by

$$\overbrace{n\times n \times n \times \cdots \times n}^{l \text{ times}} = n^l.$$

* ## Questions

  Now you should be able to answer these questions fairly easily.

    $$\cdot$$ How many 3-letter initials are possible? (For example, I'm R.R.H.)

    $$\cdot$$ How high can a computer count with 8 bits? (IE, $$A = \{0, 1\}$$)


# Permutations

**Permutations** are orderings of a set. Put another way, they are **strings** that use every letter __exactly__ once. Imagine 3 people lining up in a row for a photograph. Here are some possible orderings:

$$123 \quad 132 \quad 213 \quad 231 \quad 312 \quad 321$$

Did I miss any? 

If we could clone people, like in **strings**, then there would be $$3\times3\times3 = 27$$ possibilities!

But when I pick the first person and lock in my choice, I only have 2 people to draw on for the next option. After I pick the 2nd, then I'm done having options. There's only one left. That's why there are $$3\times2\times1 = 6$$ options here.

What happens if I add a fourth person? Well, say I'm using the $$123$$ ordering. Now there are four possible places for the new guy to stand:

$$*1*2*3*$$ 

The same goes for each of the original 6 orderings. So now we have $$4\times3\times2\times1 = 24$$ possibilities.

So how many permutations exist for an $$n$$-element set?

$$n\cdot(n-1)\cdot(n-2)\cdot\cdots\cdot3\cdot2\cdot1 = n!$$

*Permutations are important in group theory, and I'll hopefully write about that soon and add a link here.*

  * ## Questions
    
    You're lining up 5 people to take a photograph. We already know there are $$5! = 120$$ ways to order them.

    $$\cdot$$ What if the most dominant member insists on standing in the middle?

    $$\cdot$$ What if there are 2 identical twins, and it doesn't matter if they switch places?

# Subsets

At this point we're going to make a crucial change, and stop caring about **order**.

Imagine you have 10 precious toe-rings: Agate, Amethyst, Citrine, Diamond, Emerald, Onyx, Quartz, Ruby, Sapphire, and Turqoise. Every day when you leave home to your job as a surfing teacher, you select a **subset** of them to adorn your toes.

  $$\cdot$$ If you're feeling depressed and bring ZERO toe rings, you've brought a subset.

  $$\cdot$$ If you have designs on a certain student and it's a Ruby and Emerald day, you've brought a subset.

  $$\cdot$$ If you bring a toe ring on EVERY TOE, you've brought a subset (namely, the whole set).

Get the picture? **So, how many subsets are there of your 10 toe-rings?**

We can reduce this to a question about **strings** if we notice that each toe-ring is in one of two states: It's either on your foot making everyone jealous, or it's languishing at home in your special designated drawer. So, make an alphabet with 2 letters. I'll use $$0$$ and $$1$$. Then the 3 cases above correspond to:

  $$\cdot$$ 0000000000
  $$\cdot$$ 0000100100
  $$\cdot$$ 1111111111

But wait! Our question has become: 

How many strings of length 10 can I make with a 2-letter alphabet? It turns out there are $$2^{10} = 1024$$ toe-ring subsets.

So in general, the number of subsets of $n$ items is

$$\overbrace{2\times 2 \times 2 \times \cdots \times 2}^{n \text{ times}} = 2^n.$$

  * ## Questions

      $$\cdot$$ You decide you feel silly if you're wearing only 1 toe ring. How many possibilities do we have if we exclude single-element subsets?
