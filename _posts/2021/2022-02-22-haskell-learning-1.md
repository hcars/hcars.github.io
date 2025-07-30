---
layout: default
title: Learning Haskell, Entry 1
tags: Haskell, Functional Programming
published: true
---

# First Thoughts

In undergrad, I always heard about FP (functional programming), but I never sat down to actually learn a 
functional language. All I knew about FP was a vague impression of being different from programming in other
languages. After a few chapters in <em>Learn You a Haskell</em> and some of [99 Haskell Problems](https://wiki.haskell.org/H-99:_Ninety-Nine_Haskell_Problems), I am starting to get a grip on this whole functional style. I'll admit that I still haven't seen a functor used practically (beside <em>map</em>), and I can't define monad yet. Other than that progress is good.

Recursion, recursion, recursion. I have learned to love recursion and am becoming well-acquainted with recursive helpers such as in the below:

{% highlight language %}
-- Problem 16: Drop every n-th entry
dropEveryHelper :: [a] -> Int -> Int -> [a]
dropEveryHelper [] _ _ = []
dropEveryHelper xs n cnt
    | (cnt `mod` n == 0) && ( cnt > 0) = dropEveryHelper  (tail xs) n (cnt + 1)
    |  otherwise = x : dropEveryHelper  (tail xs) n (cnt + 1)
        where x = head xs
dropEvery :: [a] -> Int -> [a]
dropEvery xs n = dropEveryHelper xs n 1
{% endhighlight %}

Because functional programming rejects state, we are forced to use recursion. Functions are pure which means that they don't change anything outside themselves. Variables are just values and can't be altered. That means no loop conditions and, thus, no loops. ***NO LOOPS***. This is confusing at first, but you can get over it fast. If you don't believe me, think about every time you have debugged a loop or function to trace some distant part of the code-base messing up the correct value. 
