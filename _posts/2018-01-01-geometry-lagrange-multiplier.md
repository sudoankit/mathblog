---
layout: post
comments: true
title: "Geometrical Explorations of the Lagrangian Multipliers"
excerpt: "A river bed, some beads and a 3D surface plot."
date: 2018-01-01 08:52:01 +0530
mathjax: true
---
<style>
.boxx {
	border: 1px solid black;
	width: 400px;
}
</style>

<style>
p {
  text-align: justify;
}
</style>
The Lagrangian Multipliers is an important strategy in mathematical optimization to find the local maxima or minima of a function subject to equality constraints. 

Let's develop some intuition about them.

## The River Bed

<div class="imgcap">
<img src="/assets/lagragian/riverbed.svg" style="border: solid; ; width:100%;">
<div class="thecap" style="text-align:center">
You saw your friend at the river bed after 10 years. ( it happens all the time doesn't it? ) The friend calls you but you are very very thristy. You have to optimize your way. Drink some water and then proceed to meet him.
</div>
</div>

Let's assume that the curve equation for the river bed is $g(x,y) = c$ for some constant $c$. The ellipses of the form $f(x,y) = c_{i}$ are the possible areas where your path lies when you walk to meet your friend. When an area touches the riverbed, that area would contain the path where you drank water and went to meet your friend. The area which satisfies your contraint ( _drinking water_ ) as well as the equation ( _meeting your friend_ ).

So, this develops an optimization problem. 

<center>
<div class="boxx">
<center>Maximize or Minimize $f(x,y)$,</center>
<center>Subject to $ g(x,y) = 0$ where $c = 0$</center>
</div>
</center>

In our weird example we need to minimize the time taken to drink water and 
meet our friend ( because the 'friend' has to leave...). Let's look closely at the intersection point to determine conditions which are needed solve this optimization problem. (look below why $c = 0$)


<div class="imgcap">
<img src="/assets/lagragian/hitpoints-01.png" style="border: solid; ; width:100%;">
<div class="thecap" style="text-align:center">
The point of intersection of the ellipse and the riverbed curve $f(x,y)$. They have a common tangent. The normals are also shown. 
</div>
</div>

A lot of interesting stuff happens here at the interection point. First, you can easily verify that both the curves have a common tangent equations. Nice. Next, the point has two normals acting on it, in the opposite directions. This is what we care about. 

<font color="blue">Normals.</font>  

Let's focus on normals. As we know the normal is given by the gradient of the curve, (since the gradient of a function is perpendicular to the contour lines)

$$ \nabla_{x,y} g = \Bigl( \frac{\partial{g}}{\partial{x}}, \frac{\partial{g}}{\partial{y}}  \Bigr) $$ 

and,

$$ \nabla_{x,y} f = \Bigl( \frac{\partial{f}}{\partial{x}}, \frac{\partial{f}}{\partial{y}}  \Bigr) $$ 

So, we never know whether these normal are balanced. It depends on the curve and elipse equations. Thus we introduce a scalar, non-zero constant, <font color='blue'> $\lambda$ </font> (to balance the point of interection, where the maxima or minima lies).
<center>
<div class="boxx">
$$ \nabla_{x,y} f = \lambda \nabla_{x,y} g $$
</div>
</center>

This constant is called the <font color='blue'>Lagrange multiplier.</font>

We continue solving this equation,

<center>
<div class="boxx">
$$ \nabla_{x,y} f - \lambda \nabla_{x,y} g = 0$$
</div>
</center>

Note, setting $\lambda = 0$ is a solution if $f(x,y)$ is at the level (horizontal) regardless of $g(x,y)$. 

Let us define another function $\mathscr{L}(x,y,\lambda) \equiv f(x,y) + \lambda g(x,y)$ to include all the conditions into one equation and solve for $\nabla_{x,y,\lambda}\mathscr{L}(x,y,\lambda) = 0.$ [ this function is also called the <font color="blue">Lagrangian Function</font>, also note that $\lambda$ can be positive or negative ]

As there are three unknowns, $x,y$ and $\lambda$, would need to solve three equations. 

The constraint condition, $\nabla_{x,y} f = \lambda \nabla_{x,y} g $ is found by setting $\nabla_x \mathscr{L} = 0$ and further, the condition $\nabla_{\lambda} \mathscr{L}(x,y,\lambda) = 0$ leads to $g(x,y) = 0$.

An example will make this much more clear. 

<div class="definition">
<strong>Example 1.</strong> Let us find stationary points of the function $f(x,y) = x^2 + y^2 + 1$ subject to constraint $g(x,y) = x + y - 1 = 0$.
<br>
<strong>Answer.</strong> 
<div class="imgcap">
<img src="/assets/lagragian/lagrange1.jpg" style="border: solid; width:60%;">
<div class="thecap" style="text-align:center">
Plot of $f(x,y) = x^2 + y^2 + 1$ and $g(x,y) = x + y - 1 = 0$.
</div>
</div>

First let's write the correspoding Lagragian Function for this problem. 

$$\mathscr{L}(x,y,\lambda) = f(x,y) - \lambda g(x,y) = x^2 + y^2 + 1 + \lambda(x + y - 1)$$

Now the following conditions must be satisfied, 

$$2x + \lambda = 0 \quad [\nabla_x \mathscr{L} = 0 ]$$
$$2y + \lambda = 0 \quad [\nabla_y \mathscr{L} = 0 ]$$
$$x + y - 1 = 0 \quad [\nabla_{\lambda} \mathscr{L} = 0 ]$$

Next solving these equations, we get the solution of stationary points as $(x^*,y^*) = (\frac 12, \frac 12)$ and the value of the Lagragian Multiplier is $\lambda = -1$.
</div>

I hope this example made the concept much clear! Let's move forward and discuss Lagrangian Multipliers with some physics!

## The Necklace

<div class="imgcap">
<img src="/assets/lagragian/necklace.png" style="border: solid; ; width:100%;">
<div class="thecap" style="text-align:center">
A necklace as a curved fucntion. At different time $t$, the bead is at different points $a,b,c,d$. By the figure we can verify points $b$ and $c$ are the maxima and minima points. 
</div>
</div>

This section is more on the the physical approach in understanding why we don't consider the tangent but the normal. 

The points $a,b,c,d$ are the points where the necklace is perpendicular to the downward force and only at these points the normal reaction ( $f$ ) is balanced by the gravitional potential $\phi = mgh$.

As it's balanced ( if not the necklace won't be parallel to the surface) we get, 
<center>
<div class="boxx">
$$ \nabla_{x,y} f = \lambda \nabla_{x,y} \phi $$
</div>
</center>

Let's forget about the other points and only consider $d$ and say this is where the maximum occurs. Then it can be seen that $\nabla F$, the gradient of $F$ must be perpedicular to the necklace at $d$. If any component of $\nabla F$ were parallel we could move away from $d$ and arive at another point which would be the maxima contrary to our claim that $d$ is the maxima. Thus,

<center>$\nabla F \perp$ Necklace.</center>

Another way is looking closely at point <font color="red"> $d$ </font> for which a force $F$ acts at angle $\theta$ and we can find the components of this force as $F\cos \theta $ and $F\sin \theta $. Now as it's a stationary point, 

<center>$$ F\cos \theta = F$$
$$\cos \theta = 1$$
$$\theta = \frac \pi 2$$
</center>

.....which again proves that $\nabla F \perp$ Necklace.

<div class="definition">
<strong>Example 2.</strong> Let $S$ be a surface in 3-dimensional space. Look below. Find the maximum value attained by $\phi$ on $S$.  

<div class="imgcap">
<img src="/assets/lagragian/surf.png" style="border: solid; width:75%;">
<div class="thecap" style="text-align:center">
3-dimensional plot of $S$. Try finding where the maxima might lie.
</div>
</div>
<strong>Answer.</strong> 
<div class="imgcap">
<img src="/assets/lagragian/surfa.png" style="border: solid; width:75%;">
<div class="thecap" style="text-align:center">
Look for the $\nabla \perp S$. Other's can't be possible.
</div>
</div>
</div>
 
## Few Words

I hope this post has been a bit helpful in visually understandng what Lagrangian Multipliers through geometric explorations. As always recap, 

<center>
<div class="boxx">
	Normals are given by,
$$ \nabla_{x,y} g = \Bigl( \frac{\partial{g}}{\partial{x}}, \frac{\partial{g}}{\partial{y}}  \Bigr) $$ 
$$ \nabla_{x,y} f = \Bigl( \frac{\partial{f}}{\partial{x}}, \frac{\partial{f}}{\partial{y}}  \Bigr) $$ 
</div>
</center>
<center>
<div class="boxx">
$$ \nabla_{x,y} f = \lambda \nabla_{x,y} g $$
</div>
</center>

<center>
<div class="boxx">
$\mathscr{L}(x,y,\lambda) \equiv f(x,y) + \lambda g(x,y)$ to solve set,

$$\nabla_x \mathscr{L} = 0$$
$$\nabla_y \mathscr{L} = 0$$
$$\nabla_{\lambda} \mathscr{L} = 0 $$
</div>
</center>
<center>
<div class="boxx">$\nabla F \perp$ $S$, where $S$ is the surface</div>
 </center> 

<hr>

References include <font color="blue">my father's lecture notes on numerical methods and FEM at NITC (riverbed) </font>, <a href="https://en.wikipedia.org/wiki/Lagrange_multiplier">Wikipedia</a>, <a href="https://math.stackexchange.com">math.stackexchange</a>, <a href="https://www.microsoft.com/en-us/research/people/cmbishop/">Pattern Recognition and Machine Learning, Bishop</a> and <a href="https://ocw.mit.edu/courses/mathematics/18-02-multivariable-calculus-fall-2007/video-lectures/lecture-13-lagrange-multipliers/">MIT OWC Multivariable Calculus. (necklace intuition)</a>

All images are mine and are licensed under CC-BY-4.0. Softwares used include MATLAB, OSX Grapher, Preview.app and Adobe illustrator.
<hr>

I hope you had as much fun reading than I had writing this up! 

Wish you all a happy near year 2018!

Ankit.