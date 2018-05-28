---
layout: post
comments: false
title: "Everything Eigen"
excerpt: "A matrix, some eigenvalues and vodka at the party...."
date: 2018-08-25 07:52:00 +0530
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

> Warning: Subtle humour and sarcasm in this post. 

We start with a table of content for I believe this is going to be a long, long post so I am pushing this online every week, like a part by part basis (I have other work too!). 


- <a href="#intro">Introduction to Matrices.</a> [June 1st week]
- A better introduction to spaces, operations and stuff.
- Meet Hilbert.
- Hilbert's space.
- Fields, linear transformation and scalars. WTF?
- Charismatic Characteristic Root.
- Everything Eigen.
- More Than Required.
- Banach Spaces.
- A trailer of Spectral Theory. 
- Thoughts. Questions. F.A.Q. 
- Klein bottled vodka.
- Unnecessary Bullet Point.

Supercharged content right? Should take around 3 months to write ;) Perfect for the summer vacations! I hope this will help you to look at mathematics in a much fun, interesting and different way to develop some mathematical maturity and intuition.

---

<p id="intro">

<h2> Introduction to Matrices. </h2>

Why do we need to represent numbers is this way?

$$
\begin{bmatrix}
1 & 69 & 12 \\
12 & 25 & 4 \\
0 & 10 & 2 
\end{bmatrix}
$$

Not just numbers but functions and other stuff too.

$$
\begin{bmatrix}
1 & 42i & \cos(x) \\
\xi(x) & 25 & 4 \\
\int x dx & e & \sqrt{2} 
\end{bmatrix}
$$

Actually you can <b>put anything</b> inside it. Even emoji's.

<center>
<img src="/mathblog/assets/eigen/emoji-matrix.png" style=" width:20%;">
</center>

Nice! I bet you have started to trust matrices now as you just met them online. Let's get serious for some time. 

Meet this equation. 

$$ 4x - 8 = 0$$

You immediately think $x = 2$. It's easy to solve for $x$, right?

How about we have more than one variable? 

$$
4x + 7y + 8z - 2 = 0 \\
7x + 3y + 5z - 4 = 0 \\
8x + 9y + 2z - 4 = 0
$$

</p>
<p>

What are the values for $x, y, z$? You immediately think $ x = \frac{99}{169} , y = \frac{-14}{169}$ and $z = \frac{5}{169}$.
<br>
<br>
No? Don't worry! Very few people can inverse a matrix in their head. Just to give you comfort, I can't.

Let's go back and analyze this previous equation,

$$
4x - 8 = 0 \quad \text{or} \quad 4x = 8
$$

<center>
<img src="/mathblog/assets/eigen/p1.jpg" style=" width:70%;">
</center>


</p>
<hr>

<h2>Under Construction.
