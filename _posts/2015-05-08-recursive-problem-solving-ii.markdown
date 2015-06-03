---
layout: post
title: "Recursive Problem Solving II"
subtitle: "oh no, he's on about it again"
author: "Sam Calvert"
date: 2015-05-08
categories: samcal
---

![](http://i176.photobucket.com/albums/w200/allievogiovane/MCEscher-DrawingHands.jpg)

I just reread [my most recent post](/samcal/2015/02/12/haskell.html), which was
meant to be about recursion. I took the liberty of writing the examples in
Haskell, mostly because I believe it to be the most elegant language in which to
write recursive functions/data structures. It ended up that the article was just
about this clever solution to a problem, and did a very poor job explaining why
or how to solve problems recursively. That topic seems much more interesting.

# Recursive Data Types

Recursive things are self-referential (s/o *GEB*). This means that a recursive
data type will contain values of the same type. The classic example is the
singly linked list:

{% highlight java %}
class List<E> {
  E value;
  List<E> next;
}
{% endhighlight %}

A more familiar example is a person on a social network:

{% highlight java %}
class Person {
  String name;
  Person[] friends;
}
{% endhighlight %}

The `Person` type has an array of `Person`s that will each have another array of
its own.

Recursive data types are cool because they often produce [directed
graphs](http://en.wikipedia.org/wiki/Directed_graph), and can therefore be
reasoned about with the very powerful tools from graph theory.

# Recursively Enumerable Sets

**Recursively Enumerable Sets** are defined by axioms (or "base cases" in
common computer science jargon), and at least one rule for transforming the
axioms into "theorems" -- members of the set. The classic example of a
recursively enumerable set is the set of Fibonacci numbers.

The set of prime numbers is also a recursively enumerable set, with the axiom of
2, and the rule that members of the set must not be divisible by the previous
numbers in the set.

Recursively enumerable sets must be very simple ways of explaining these complex
ideas, as they only require axioms and rules. They then rely on the emergent
behavior of the iteration of those rules to unleash the complexity.

# Recursive Functions

Recursive functions, at least in the context of computer programming, are often
given a bad rap in computer science classrooms as being complicated and
difficult. When used correctly, they often present themselves as elegant and
simple solutions.

The job of a recursive function is to find and return an element from a
recursively enumerable set. Since we have established that recursively
enumerable sets are simple, recursive functions must then be simple as well. A
proper recursive function takes input, finds the appropriate base case, and then
iterates the rules in the correct way to generate the output.

# Fractals

Fractals are self-referential in a different way: they show self-similarity in
different parts of the images that they generate. This can generate very
beautiful, complex patterns. This following image is the [Mandelbrot
Set](http://en.wikipedia.org/wiki/Mandelbrot_set), perhaps the most famous and
most mathematically-significant fractal. The image is zoomed about
10,000,000 times larger than the original.

![](http://upload.wikimedia.org/wikipedia/commons/a/a4/Mandel_zoom_11_satellite_double_spiral.jpg)

This fractal lies in the complex plane (horizontal axis for the real part,
vertical axis for the imaginary part), and the color at each point $%C%$ is
defined as the nature of the following (recursive!) function at that point:

$$Z \mapsto Z^2 + C$$

This notation means: take the point, square it, add C, and run the function
again. This is equivalent to the following, expanded notation:

$$C + (C^2 + C) + ((C^2 + C)^2 + C) + \dots$$

The color comes from the tendency of the recursive function. If the value of
$%C%$ tends toward zero (that is, $%0+0i%$), or is stuck in a loop, the color
will be black.

In the case that the value of $%C%$ tends toward $%\infty%$, the color of the
point is *how quickly* the value escapes. Blues escape very quickly, oranges
escape more slowly.

# Philosophy

As a palette cleanser from mathematical talk and jargon, I'll end with this
fantastic quote from J. R. Lucas' "Mind, Machine, and Gödel":

> At one's first and simplest attempts to philosophize, one becomes entangled in
> questions of whether when one knows something one knows that one knows it, and
> what, when one is thinking of oneself, is being thought about, and what is
> doing the thinking. After one has been puzzled and bruised by this problem for
> a long time, one learns not to press these questions; the concept of a
> conscious being is, implicitly, realized to be different from that of an
> unconscious object. In saying that a concious being knows something, we are
> saying not only that he knows it, but that he knows that he knows it, and
> that he knows that he knows that he knows it, and so on, as long as we care to
> pose our question: there is, we recognize, an infinity here, but it is not an
> infinite regress in the bad sense, for it is the questions that peter out, as
> being pointless, rather than the answers. The questions are felt to be
> pointless because the concept contains within itself the idea of being able to
> go on answering such questions indefinitely. Although concious beings have the
> power of going on, we do not wish to exhibit this simply as a succession of
> tasks they are able to perform, nor do we see the mind as an infinite sequence
> of selves and super-selves and super-super-selves. Rather, we insist that a
> conscious being is a unity, and though we talk about parts of the mind, we do
> so only as a metaphor, and will not allow it to be taken literally.



























