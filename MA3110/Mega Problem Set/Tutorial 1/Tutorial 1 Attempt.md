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

> To prove that a function spans $\mathbb{R}$, use the intermediate value theorem. First show $\lim_{x \rightarrow \pm\infty} f(x) = \pm \infty$. Then show that for any $y$, there exists an $x$ such that $f(x) = y$. 
> $$
> \exists M_1 \text{ s.t } ~ x \geq M_1 \implies f(x) > y \\
> \exists M_2 \text{ s.t } ~ x \leq M_2 \implies f(x) < y \\
> $$
> So by IVT there must be some $x_0 \in (M_1, M_2)$ such that $f(x_0) = y$.

## Question 6

Use the Mean Value Theorem to prove that 
$$
\sqrt{1 + x} < 1 + \frac{1}{2}x ~~\forall x > 0
$$

> Answer:
>
> Let $f(x) = \sqrt{1 + x}$. Then $f'(x) = \frac{1}{2\sqrt{1 + x}}$ for all $x > 0$.
>
> By the Mean Value Theorem, there exists $c_1 \in (0, x)$ such that
> $$
> \begin{align*}
> 	f'(c_1) = \frac{f(x) - f(0)}{x - 0} \\
> 	\implies \frac{1}{2\sqrt{1 + c_1}} = \frac{\sqrt{1 + x} - 1}{x}\\
> 	\implies \frac{x - 2\sqrt{1 + c_1}(\sqrt{1 + x} - 1)}{2x\sqrt{1 + c_1}} &= 0.
> \end{align*}
> $$
> Multiply both sides of the equation by $2x\sqrt{1 + c_1} > 0$ to get
> $$
> x - 2\sqrt{1 + c_1}(\sqrt{1 + x} - 1) = 0
> $$
> which gives 
> $$
> x - 2\sqrt{1 + c_1}\sqrt{1 + x} - 2\sqrt{1 + c_1} = 0.
> $$
> Rearranging terms, we get
> $$
> -2\sqrt{1 + c_1}\sqrt{1 + x} = -2\sqrt{1 + c_1} - x
> $$
> and when we multiply both sides of the equation by $-2\sqrt{1 + c_1}$, we get
> $$
> \sqrt{1 + x} = 1 + \frac{1}{2\sqrt{1 + c_1}}x < 1 + \frac{1}{2}x
> $$
> because $c_1 > 0 \implies \sqrt{1 + c_1} > 1$. 
>
> > Intuition: Can use MVT to show $f(x) \leq\geq \text{ some polynomial}$.

## Question 7

Let $I$ be an open interval and let $c \in I$. Let $f: I \rightarrow \mathbb{R}$ be **continuous** and define $g: I \rightarrow \mathbb{R}$ by $g(x) = |f(x)|$ for $x\in I$. 

1. Give an example where $f$ is differentiable at $c$ but $g$ is not differentiable at $c$.

> Answer: 
>
> Let $f(x) = x$ and $c = 0$.
>
> Correction:
>
> Let $f(x) = x - c$ so that $g(x) = |x - c|$ 

2. Prove that if $g$ is differentiable at $c$, then $f$ is also differentiable at $c$.

> Answer: Given $g$ is differentiable at $c$, there exists a function $\phi : I \rightarrow \mathbb{R}$ such that $\phi$ is continuous at $c$,
> $$
> g(x) - g(c) = |f(x)| - |f(c)| = \phi(x)(x - c) ~\text{ for } x \in I,
> $$
> and $g'(c) = \phi(c)$.
>
> ___
>
> Suppose $f(c) > 0$. Then since $f$ is continuous at $c$, this means that 
> $$
> \lim_{x \rightarrow c} f(x) = f(c) > 0.
> $$
> There exists $\delta > 0$ such that
> $$
> 0 < |x - c| < \delta \implies f(x) > 0.
> $$
> Then in $(c - \delta, c + \delta)$, $f(x) = g(x)$ so $f$ is differentiable.
>
> ___
>
> Suppose $f(c) < 0$. Then since $f$ is continuous at $c$, this means that 
> $$
> \lim_{x\rightarrow c}f(x) = f(c) < 0.
> $$
> There exists $\delta > 0$ such that 
> $$
> 0 < |x - c| < \delta \implies f(x) < 0.
> $$
> Then in $(c - \delta, c + \delta)$, $f(x) = - g(x)$ so $f$ is differentiable.
>
> ___
>
> Suppose $f(c) = 0$. Then $g(c) = 0$ which makes $g(c)$ an absolute minimum. Since $c$ is an interior point of $I$, by the Interior Extremum Theorem, $g'(c) = \phi(c) = 0$. Since $f(x) = sign(f(x))g(x)$, $f(x) = sign(f(x))\phi(x)(x-c)$. Not sure how to show that $sign(f(x))\phi(x)$ is continuous.
>
> Correction:
> $$
> \begin{aligned}
> g'(c) = \lim_{x \rightarrow c} \frac{|f(x)| - |f(c)|}{x - c} \\
> = \lim_{x \rightarrow c} \frac{|f(x)|}{x - c} \\
> = \lim_{x \rightarrow c^+} \frac{|f(x)|}{x - c} \\
> = \lim_{x \rightarrow c^-} \frac{|f(x)|}{x - c}
> \end{aligned}
> $$
> Because $x - c$ is negative and positive for left and right hand limit, but the limits are equal, they must equal 0.

3. Compute $f'(c)$ in terms of $g'(c)$.

> Question 8: The straddle lemma is to say that close to a point, the line segment is close to the tangent