---
layout: default
title: "Analytic Number Theory: From Integers to Probability"
permalink: /math-talks/analytic-number-theory/
toc: true
---

See the full PDF [here](/math-talks/analytic-number-theory/index.pdf).

# Analytic Number Theory: From Integers to Probability

## 1 Introduction

Prime numbers grow sparser as integers get larger. Define the **prime-counting function**:

$$
\pi(x) = \#\{p \le x : p \text{ is prime}\}.
$$

Here $$\#$$ counts set elements. $$\pi(x)$$ here is not the circle constant.

Analytic number theory studies integers via sums, integrals and limits. Let $$n, N$$ be positive
integers; let $$p$$ be a prime; let $$x$$ be a counting upper bound. We write $$\log x = \ln x$$,
the natural logarithm with base $$e$$.

## 2 Notation Quick Reference

| Notation | Meaning & Example |
| --- | --- |
| $$\sum, \prod$$ | Sum / product; $$\sum_{n=1}^3 n = 6$$ |
| $$d \mid n$$ | $$d$$ divides $$n$$; $$\sum_{d\mid 6} d = 1+2+3+6$$ |
| $$\lfloor x \rfloor$$ | Floor: $$\lfloor 10/3 \rfloor = 3$$ |
| $$\gcd(a,b)$$ | Greatest common divisor |

Asymptotics for $$x \to \infty$$, $$g(x) > 0$$:

- $$f \sim g$$: $$f(x)/g(x) \to 1$$
- $$f = O(g)$$: $$\lvert f(x) \rvert \le C g(x)$$ for some constant $$C$$
- $$f = o(g)$$: $$f(x)/g(x) \to 0$$

## 3 Series-Integral Estimates

For non-increasing nonnegative $$f$$:

$$
\int_{1}^{N+1} f(t)\,dt \le \sum_{n=1}^{N} f(n) \le f(1) + \int_{1}^{N} f(t)\,dt.
$$

Harmonic number $$H_N = \sum_{n=1}^{N} \frac{1}{n}$$:

$$
\log(N+1) \le H_N \le 1 + \log N \implies H_N = \log N + O(1).
$$

Riemann zeta series:

$$
\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} \quad \text{converges for } s > 1.
$$

Near $$s \to 1^+$$, $$\zeta(s) \sim \dfrac{1}{s-1}$$.

## 4 Arithmetic Functions & Dirichlet Convolution

### 4.1 Multiplicative Functions

An **arithmetic function** is a map from positive integers to numbers.

| Function | Definition | $$n=12=2^2 \cdot 3$$ |
| --- | --- | --- |
| $$1(n)$$ | constant 1 | 1 |
| $$\text{id}(n)$$ | $$\text{id}(n) = n$$ | 12 |
| $$\tau(n)$$ | number of positive divisors | 6 |
| $$\varphi(n)$$ | count integers $$\le n$$ coprime to $$n$$ | 4 |

$$f$$ is **multiplicative** if $$f(ab) = f(a)f(b)$$ whenever $$\gcd(a,b) = 1$$.
Example: $$\tau(p^k) = k+1$$.

### 4.2 Dirichlet Convolution

$$
(f * g)(n) = \sum_{ab=n} f(a)g(b) = \sum_{d \mid n} f(d) g\left(\frac{n}{d}\right).
$$

Every ordered splitting $$ab = n$$ counts once.

Divisor function identity:

$$
\boldsymbol{\tau = 1 * 1}.
$$

Convolution unit:

$$
\varepsilon(n) =
\begin{cases}
1 & n = 1,\\
0 & n > 1.
\end{cases}
$$

Convolution is commutative and associative; $$f * \varepsilon = f$$.

### 4.3 Möbius Inversion

Möbius function $$\mu(n)$$:

- $$\mu(1) = 1$$
- If $$p^2 \mid n$$, then $$\mu(n) = 0$$
- If $$n$$ is a product of $$r$$ distinct primes, then $$\mu(n) = (-1)^r$$

Key identity:

$$
\boldsymbol{\mu * 1 = \varepsilon}.
$$

Möbius inversion: if

$$
F(n) = \sum_{d \mid n} f(d),
$$

then

$$
f(n) = \sum_{d \mid n} \mu(d) F\left(\frac{n}{d}\right).
$$

### 4.4 Euler's Totient Function

We have

$$
\sum_{d \mid n} \varphi(d) = n, \quad \text{i.e. } 1 * \varphi = \text{id}.
$$

Inverting:

$$
\varphi(n) = n \prod_{p \mid n} \left(1 - \frac{1}{p}\right).
$$

Example:

$$
\varphi(30) = 30\left(1-\frac{1}{2}\right)\left(1-\frac{1}{3}\right)\left(1-\frac{1}{5}\right) = 8.
$$

## 5 Averages of Arithmetic Functions

### 5.1 Average of Divisor Function

Total divisor count up to $$N$$:

$$
D(N) = \sum_{n \le N} \tau(n) = \sum_{d \le N} \left\lfloor \frac{N}{d} \right\rfloor = N \log N + O(N).
$$

Average:

$$
\frac{1}{N} \sum_{n \le N} \tau(n) = \log N + O(1).
$$

### 5.2 Hyperbola Trick

Count lattice points $$ab \le x$$. Let $$m = \lfloor \sqrt{x} \rfloor$$. Then

$$
D(x) = 2 \sum_{a=1}^{m} \left\lfloor \frac{x}{a} \right\rfloor - m^2.
$$

This shortens the sum from length $$x$$ to $$\sqrt{x}$$.

## 6 Probabilistic Viewpoint on Integers

### 6.1 Density

**Density** = limiting proportion of integers satisfying a property.

For fixed distinct primes $$p_1, \dots, p_r$$, divisibility events become independent in the limit
$$N \to \infty$$.

### 6.2 Square-Free Integers

An integer is **square-free** if no prime square divides it.

Count up to $$N$$:

$$
Q(N) = \#\{\text{square-free } n \le N\} = \frac{N}{\zeta(2)} + O(\sqrt{N}).
$$

Density:

$$
\frac{1}{\zeta(2)} = \frac{6}{\pi^2} \approx 60.79\%.
$$

### 6.3 Erdős-Kac Theorem

Let $$\omega(n)$$ be the number of distinct prime factors of $$n$$. Pick integer $$U$$ uniformly
from $$\{1, \dots, N\}$$. As $$N \to \infty$$:

$$
\frac{\omega(U) - \log \log N}{\sqrt{\log \log N}}
$$

follows a standard normal distribution.

A typical integer has roughly $$\log \log N$$ distinct prime factors.

## 7 Exercises to Try Yourself

1. Compute $$\tau(12)$$ directly and via convolution $$1 * 1$$.
2. Evaluate $$\mu(n)$$ for $$n = 1, \dots, 10$$. Verify $$(\mu * 1)(6) = 0$$.
3. Use the product formula to compute $$\varphi(21)$$.
4. Use the hyperbola trick to compute $$D(15)$$.
5. What is the density of integers not divisible by 2 or 3?

**Remember:** work from definitions. Do not just look up answers. Good luck!
