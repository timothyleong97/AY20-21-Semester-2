[toc]

# Tutorial 1

## Question 1

Suppose that the function $f$ is defined in a deleted neighbourhood of a point $c$ and $L \in \mathbb{R}$. Prove that 
$$
\lim_{x\rightarrow c}f(x) = L \text{ if and only if } \lim_{x\rightarrow c^+}f(x) = L = \lim_{x\rightarrow c^-}f(x). \tag {MA2108 Thm 4.4.1}
$$

> **Answer**:  
>
> $(\Longrightarrow)$ Suppose that $\lim_{x\rightarrow c}f(x) = L$. Let $\epsilon > 0$ be given. Then $\exists \delta > 0$ such that 
> $$
> 0 < |x - c| < \delta \Longrightarrow \big|f(x) - L\big| < \epsilon.
> $$
> Since 
> $$
> \begin{aligned}
> |x - c| < \delta \Longleftrightarrow& -\delta < x - c < \delta \\
> \Longleftrightarrow& c - \delta < x < c + \delta
> \end{aligned}
> $$
> then 
> $$
> \begin{aligned}
> c - \delta < x < c \Longrightarrow& c-\delta < x < c < c + \delta \\
> \Longrightarrow& c - \delta < x < c + \delta \\
> \Longrightarrow& 0 < |x - c| < \delta \\
> \Longrightarrow& \big|f(x) - L\big| < \epsilon
> \end{aligned}
> $$
> which gives $\lim_{x \rightarrow c^-}f(x) = L$. Similarly, 
> $$
> \begin{aligned}
> c < x < c + \delta \Longrightarrow& c-\delta < c < x < c + \delta \\
> \Longrightarrow& c - \delta < x < c + \delta \\
> \Longrightarrow& 0 < |x - c| < \delta \\\Longrightarrow& \big|f(x) - L\big| < \epsilon
> \end{aligned}
> $$
> which gives $\lim_{x\rightarrow c^+}f(x) = L$.
>
> $(\Longleftarrow)$ Suppose that $\lim_{x\rightarrow c^+}f(x) = L = \lim_{x\rightarrow c^-}f(x).$ Let $\epsilon > 0$ be given. Then $\exists \delta_1> 0$ such that
> $$
> c - \delta_1 < x < c \implies \big|f(x) - L\big| < \epsilon.
> $$
> Likewise, $\exists\delta_2 > 0$ such that  
> $$
> c < x < c + \delta_2 \implies \big|f(x) - L\big| < \epsilon.
> $$
> Let $\delta = \min\{\delta_1, \delta_2\}$. We get
> $$
> \begin{aligned}
> c - \delta_1 \leq c - \delta < x < c \implies& \big|f(x) - L\big| < \epsilon \\
>  c < x < c + \delta \leq c + \delta_2 \implies& \big|f(x) - L\big| < \epsilon.
> \end{aligned}
> $$
> Then since
> $$
> c - \delta < x < c + \delta \implies |x - c| < \delta 
> $$
>  
>
> we get  $\lim_{x\rightarrow c}f(x) = L$.

___

## Question 2

Let $f : (0, 1) \rightarrow \mathbb{R}$ and $L \in \mathbb{R}$. Prove that $\lim_{x \rightarrow 0^+}f(x) = L$ if and only if $\lim_{y \rightarrow \infty}f(\frac{1}{y}) = L$.

> Answer:
>
> $(\Longrightarrow)$ Let $\lim_{x \rightarrow 0^+}f(x) = L$. Let $(y_n)$ be any sequence in the domain $(1, \infty)$ such that  $y_n \rightarrow \infty$. 
>
> Then let $t_n = \frac{1}{y_n}$. By the sequential criterion, $t_n > 0$ for all $n$ and $t_n \rightarrow 0$, so  $f(t_n) \rightarrow L$. Since this is true for all $(y_n)$, by the sequential criterion, $\lim_{y \rightarrow \infty}f\left(\frac{1}{y}\right) = L$. 
>
> $(\Longleftarrow)$ Let $\lim_{y \rightarrow \infty}f(\frac{1}{y}) = L$. Then let $(x_n)$ be any sequence in the domain $(0, 1)$ such that $x_n > 0$ for all $n$ and $x_n \rightarrow 0$. Then let $t_n = \frac{1}{x_n}$. By the sequential criterion, $f(t_n) \rightarrow L$.  Since this is true for all $(x_n)$, by the sequential criterion, $\lim_{x \rightarrow 0^+}f(x) = L$. 

___

## Question 3

Let $r$ be a positive rational number, and let $f(x) = x^r$ for $x > 0$. Prove that 
$$
f'(x) = rx^{r - 1} ~~\forall x>0.
$$
> Answer: Let $r = \frac{m}{n}$. Then $x^r = (x^{\frac{1}{n}})^m$. We let $g(x) = x^m$ and $h(x) = x^{\frac{1}{n}}$, where $m, n \in \mathbb{N}$  and express $f(x) = (g \circ h)(x)$.  By the chain rule, 
> $$
> \begin{aligned}
> f'(x) =& g'(h(x))h'(x) \\
> =& g'\left(x^{\frac{1}{n}}\right)\frac{1}{n}x^{\frac{1}{n} - 1} \\
> =& m\left(x^{\frac{1}{n}}\right)^{m - 1}\frac{1}{n}x^{\frac{1}{n} - 1} \\
> =& \frac{m}{n}\left(x^{\frac{m}{n} - 1}\right)
> \end{aligned}
> $$

___

## Question 4

*What happens if $f’(c) = 0$ in Theorem 6.2.4?* 

Let $I$ be an interval, and let $f: I \rightarrow \mathbb{R}$ be strictly monotone and continuous on $I$. Let $J := f(I)$ and let $g: J \rightarrow \mathbb{R}$ be the inverse function of $f$. Prove that if $f$ is differentiable at $c \in I$ and $f'(c) = 0$, then $g$ is not differentiable at $d:=f(c)$. 

> Answer:  Assume that $g'(d)$ exists.  Then since $(g \circ f) (x) = x$,  we can apply the chain rule to get
> $$
> (g \circ f)'(x) = \frac{d}{dx} x= 1
> $$
> But because $(g \circ f) '(c) = g'(f(c))f'(c)$ and $f'(c) = 0$, it is not possible for  $(g \circ f)'(c)$ to equal 1. Hence our assumption that $g'(d)$ exists is wrong.

+++

## Question 5

Let $f(x) = x^5+4x+3$ , $x \in \mathbb{R}$ and let $g = f^{-1}: \mathbb{R} \rightarrow \mathbb{R}$ be the inverse function of $f$. Calculate $g’(8)$. 

> Answer: 
>
> Let $c \in \mathbb{R}$ be such that $f(c) = 8$. Then $g'(f(c)) = \frac{1}{f'(c)}$ by the inverse function theorem.
>
> Then $c = 1$. So $g'(8) = \frac{1}{f'(1)} = \frac{1}{9}$.