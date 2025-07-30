---
layout: default
title: Learning Haskell, Entry 2
tags: Haskell, Functional Programming
published: true
---

# Comparative Literature

Let's grab a page from our high school literature classes and compare how different uses of language can accomplish a similar task. We will compare the function that removes every n'th element from a list between Python and Haskell implementations. See the Haskell function from the first post below:

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

If I call _dropEvery xs n_, _xs_ will never be changed by the function. It has no *side-effects*. In addition, as long as I don't change _xs_ or _n_, the function will always return the same value. These two properties make _dropEvery_ a *pure function*. In Haskell, functions are by default, but not always, pure. For other languages such as Python, this is not always so. Let's take a look at a function that accomplishes the same task in Python:

{% highlight language %}
def dropEverySideEffect(xs, n):
   toRemove = [xs[i] for i in range(n-1, len(xs), n)]
   for el in toRemove:
       xs.remove(el)
   return xs
{% endhighlight %}

If we call _dropEverySideEffects(xs, n)_ where _xs=[1,2,3,4,5,6],n=2_, we will get the correct result _[1,3,5]_. However, _xs_ will now be _[1,3,5]_ in its original scope. This is a *side-effect*. For a small program, this may be easy to manage, but if _xs_ is being passed to many different functions, this could get problematic very fast. Haskell stops us from doing this by forcing us to use mainly pure functions. In Python, we could still avoid side-effects as can be seen in the below example:

{% highlight language %}
def dropEveryNoSideEffect(xs, n):
    ys = []
    for i in range(len(xs)):
        if (i + 1) % n != 0:
           ys += [xs[i]]
    return ys
{% endhighlight %}

By creating a new list, we avoid altering _xs_ in a different scope, but the responsibility to avoid side-effects is on the *programmer* here. In the case of Haskell, the *language* stops us from using side-effects.
