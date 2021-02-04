[toc]

# MA3110 Homework 1

## Question 1

Let $f: (0, \infty) \rightarrow \mathbb{R}$ be defined by
$$
f(x) = 2 + 3x^2 + 4\ln x ~\text{ for } x > 0.
$$
(i) Prove that $f$ is strictly increasing on $(0,\infty)$. 

> From the lecture exercise on Chapter 6, page 14, we concluded that if $f'(x) > 0$ for all $x\in (a, b)$, then $f$ is strictly increasing on $(a,b)$. Since $f'(x) = 6x + \frac{4}{x} > 0 ~\text{ for } x > 0$, $f$ is strictly increasing on $(0, \infty)$. 

(ii) Let $g : \mathbb{R} \rightarrow \mathbb{R}$ be the inverse function of $f$. Find $g'(5)$.

> Note that $f(1) = 5$. Since $f$ is strictly monotone and continuous on $(0, \infty)$, by the Inverse Function Theorem, 
> $$
> \begin{aligned}
> g'(5) &= g'(f(1)) \\ 
>       &= \frac{1}{f'(1)} \\
>       &= \frac{1}{6(1) + \frac{4}{1}} \\
>       &= 0.1.
> \end{aligned}
> $$
> 

___

## Question 2

Let $f: \mathbb{R} \rightarrow \mathbb{R}$ be defined by
$$
f(x) = 
\begin{cases}
e^x + x^2\cos\left(\frac{1}{2x}\right) ~\text{ if } x \neq 0 \\
1 ~~~~~~~~~~~~~~~~~~~~~~~~~~~\text{if x = 0}.
\end{cases}
$$

(1) Find $f'(x)$ for each $x \in \mathbb{R}$. 

> For $x \neq 0$, 
> $$
> \begin{aligned} 
> f'(x) &= \frac{d}{dx} \left(e^x + x^2\cos\left(\frac{1}{2x}\right)\right) \\
>       &= e^x + \frac{1}{2}\sin\frac{1}{2x} + 2x\cos\frac{1}{2x}.                      
> \end{aligned}
> $$
>  For $x = 0$, 
> $$
> \begin{aligned}
> f'(0) &= \lim_{x\rightarrow 0} \frac{e^x + x^2\cos\left(\frac{1}{2x}\right) - 1}{x - 0} \\
>       &= \lim_{x\rightarrow 0} \frac{e^x}{x} + \lim_{x\rightarrow 0} x\cos\left(\frac{1}{2x}\right) - \lim_{x \rightarrow 0} \frac{1}{x} \\
>       &= 1 + 0 - 0 \text{ (by L'Hospital's rule and the Squeeze Theorem)}\\ 
>       &= 1.
> \end{aligned}
> $$

(ii) is $f \in C^1(\mathbb{R})$? Justify your answer.

> We have to check if $f'(x)$ is continuous on $\mathbb{R}$. For $x \neq 0$, $f'(x)$ is clearly continuous. 
>
> However, $f’$ is not continuous at $x = 0$. If $f'$ was continuous at $x = 0$, then for any sequence $x_n \rightarrow 0$, we must have $f'(x_n) \rightarrow f'(0) = 1$. We show that there is a sequence $(x_n)$ which violates sequential criterion, and so $f’$ is not continuous at $x = 0$. 
>
> The sequence $(x_n)$ is defined by $x_n = \frac{1}{\left(4n + \frac{1}{2}\right)\pi}, n \in \mathbb{N}$. Then $x_n \rightarrow 0$, but 
> $$
> \begin{aligned}
> f'(x_n) &= e^{x_n} + \frac{1}{2}\sin\frac{1}{2x_n} + 2x_n\cos\frac{1}{2x_n} \\
>         &= e^{\frac{1}{\left(4n + \frac{1}{2}\right)\pi}} + \frac{1}{2}\sin\left(2n\pi + \frac{\pi}{4}\right) + \frac{1}{\left(4n + \frac{1}{2}\right)\pi}\cos\left(2n\pi + \frac{\pi}{4}\right) \\
>         &\rightarrow 1 + \frac{\sqrt{2}}{4} + 0 \\
>          &\neq  1 = f'(0).
> \end{aligned}
> $$
> 


___

## Question 3

Use the Mean Value Theorem to prove the Bernoulli’s inequality:
$$
(1 + x)^n > 1 + nx,~\forall x \in (-1, 0) \cup(0, \infty) \text{ and } n = 2,3,4\cdots 
$$

> Let $f(x) = (1 + x)^n$. $f(x)$ is differentiable in the range given above. 
>
> First we consider the range $(0, \infty)$. For any $x$, there exists a point $c \in (0, x)$ such that $f'(c) = \frac{f(x) - f(0)}{x - 0}$. This means
> $$
> \begin{aligned}
> n(1 + c)^{n - 1} = \frac{(1 + x)^{n} - 1}{x} \\
> \implies nx(1 + c)^{n - 1} = (1 + x)^{n} - 1 \\
> \implies (1 + x)^n = 1 + nx(1 + c)^{n - 1}
> \end{aligned}
> $$
>   Since $c > 0$ and $n - 1 > 0$, $(1 + c)^{n - 1} > 1$ so $(1 + x)^{n} > 1 + nx$.
>
> Next we consider the range $(-1, 0)$. For any $x$, there exists a point $c \in (x, 0)$ such that $f'(c) = \frac{f(0) - f(x)}{0 - x}$. This means
> $$
> \begin{aligned}
> n(1 + c)^{n - 1} = \frac{1 - (1 + x)^n}{-x} \\
> \implies -nx(1 + c)^{n - 1} = 1 - (1 + x)^n \\
> \implies (1 + x)^n = 1 + nx(1 + c)^{n - 1}
> \end{aligned}
> $$
> Since $x < 0$, $0 < 1 + c < 1$ and $n - 1 > 0$, $n(1 + c)^{n - 1}x > nx$, proving the inequality.  

___

## Question 4

___

Suppose that the function $f$ is continuous on $[a,b]$ and differentiable on $(a,b)$. Prove that if
$$
(f(b))^2 - (f(a))^2 = b^2 - a^2,
$$
then there exists $c \in (a,b)$, such that
$$
f'(c)f(c) = c.
$$

> Define $g(x) = (f(x))^2 - x^2$. Then $g'(x) = 2f(x)f'(x) - 2x$, $g(b) = (f(b))^2 - b^2$ and $g(a) = (f(a))^2 - a^2$.
>
> Since $(f(b))^2 - (f(a))^2 = b^2 - a^2 \implies (f(b))^2 - b^2 = (f(a))^2 - a^2$, we see that $g(a) = g(b)$. Hence by Rolle’s Theorem there exists $c \in (a,b)$ such that $g'(c) = 0$.  
> $$
> \begin{aligned}
> g'(c) = 0 \\
> \implies 2f(c)f'(c) - 2c = 0 \\
> \implies c = f'(c)f(c).
> \end{aligned}
> $$

