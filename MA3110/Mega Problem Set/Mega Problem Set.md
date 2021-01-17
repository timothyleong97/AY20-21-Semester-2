[toc]

# MA2108 Revision

*[Chapter 1, Page 7]* Prove that if $a \in \mathbb{R}$ is such that $0 \leq a \leq \epsilon$ for **every** positive number $\epsilon$, then a = 0.

> Answer: Suppose $a > 0$. Then $\frac{a}{2} > 0$ but $ a > \frac{a}{2}$, which contradicts the claim. 

+++

*[Chapter 1 Page 9]* Prove Bernoulli’s inequality, which says if $x > -1$, then $(1 + x)^n \geq 1 + nx,~~\forall n\in \mathbb{N}$. 

> Answer: We can use mathematical induction. For n = 1, we get equality. 
>
> Then 
> $$
> \begin{aligned}
> 	(1 + x)^{k + 1} =& (1 + x)^k \cdot(1 + x) \\
> 	\geq& (1 + kx) \cdot (1 + x) = 1 + (k + 1)x + kx^2 \\
>     \geq& 1 + (k + 1)x.
> \end{aligned}
> $$

___

*[Chapter 1 Page 9]* Prove the AM-GM-HM inequality.

> Not sure how to do this at this moment

___

*[Chapter 1 Page 11]* Prove the triangle inequality: for $a,b \in \mathbb{R}$, $|a + b| \leq |a| + |b|$. 

> Answer: We start with
> $$
> \begin{aligned}
> -|a| \leq a& \leq |a| \\
> -|b| \leq b& \leq |b|
> \end{aligned}
> $$
> and adding the inequalities gives us
> $$
> -|a| -|b| \leq a + b \leq |a| + |b|.
> $$
> By theorem 1.8.1 (page 10 of MA2108 notes), if $c \geq 0$, then $|a| \leq c \Leftrightarrow -c \leq a \leq c$. 
>
> Let $c := |a| + |b|$. Using the reverse direction of the theorem 1.8.1, we get the triangle inequality.

___

*[Chapter 1 Page  10]* Solve $|x| + |x + 1| < 2$. 

> Answer: On the real line, observe the two critical points 0 and -1. So we partition the real line into three parts - $x \leq - 1$, $-1 < x < 0$, $x >= 0$. 
>
> For each region, let’s say $x \leq -1$, you remove the absolute value operator and put the negative sign in front of $x$ as needed to make x positive. So you solve for $-x + -x + 1 \leq 2$ which gives you $x > -\frac{3}{2}$. 
>
> You return the set representing the union of the three regions as your final answer, which turns out to be $(-\frac{3}{2}, \frac{1}{2})$.   

___

*[Chapter 1 Page 11]* State the other 2 corollaries of the triangle inequality.

> Answer: $||a| - |b|| \leq |a - b|$ and $|a- b| \leq |a| + |b|$. 

___

Squeeze Theorem

# Lecture 1

*[Chapter 4, Page 84]* Define the h-neighbourhood of a point $a$.

> Answer: A ***h-neighbourhood*** of a point $a$ is the set
> $$
> V_h(a) = \{x : |x - a| < h \} = (a - h, a + h).
> $$
> where $h > 0$.
>
> >  **Intuition:** The point $a$, and the set of points within $h$-distance from $a$, constitute the h-neighbourhood of a.

___

*[Chapter 4, Page 84]* Define the deleted neighbourhood of a point $a$. 

> Answer: A ***deleted neighbourhood*** of a point $a$ is the set:
> $$
> V^*_h(a) = V_h(a)\backslash\{a\}
> $$
>
> > **Intuition:** The term *deleted* refers to the point $a$ itself being “**deleted**” from the real line. See diagram below:
>
> ![image-20210111093340988](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210111093340988.png)
>
> > **Intuition**: We do not care at all about the point $a$ itself, only about the points around $a$. 

*[Chapter 4, Page 85]* Define the $\epsilon-\delta$ definition of limits.

> Answer: The ***epsilon-delta*** definition of limits is defined as follows:
>
> Let the function $f$ be defined in a ***deleted neighbourhood*** of $a$. We say that the real number $L$ is the limit of $f$ at $a$ if for **any** given $\epsilon > 0$, there exists a $\delta = \delta(\epsilon) > 0$ such that 
> $$
> 0 < |x - a| < \delta \Longrightarrow |f(x) - L| < \epsilon.
> $$
>  If the limit of $f$ at $a$ exists, we then write 
> $$
> \lim_{x \to a} f(x) = L
> $$
> or 
> $$
> f(x) \rightarrow L ~~~~ \text{as}~ x \rightarrow a.
> $$
>
> >  **Intuition**: The limit of $f$ only focuses on how the points around $x = a$ cause the value of $f(x)$ to behave. Whether $f(x)$ is defined or not does not matter. This allows us to comfortably say, for example, that $\lim \limits_{x \rightarrow \frac{\pi}{2}+} \tan x = -\infty$ without requiring that $\tan \left(\frac{\pi}{2}\right)$ be defined.

___

*[Chapter 4, Page 85]* What does it mean to say that $f$ diverges at $a$?

> Answer:  If $f$ has no limit at $x = a$, we say that $f$ ***diverges*** at $a$.

____

*[Chapter 6, Page 1]* Define the sequential criterion for limits.

> Answer: The sequential criterion states that the following two expressions are equivalent:
> $$
> \lim_{x\rightarrow a} f(x) = L \iff \text{If } (x_n) \text{ is any sequence in the domain of } f \text { such that } x_n \neq a \text{ for all } n \text{ and } x_n \rightarrow a, \text{ then } f(x_n)\rightarrow L.
> $$
>
> > **Intuition**: If $f(x)$ **always** gets close to $L$ whenever $x$ gets close to $a$, then it should not matter *how exactly* x approaches a. 
> > As long as it does, $f(x)$ should tend to $L$.
>
> <u>*Proof*</u> (from page 88 of MA2108 Lecture Notes) 
>
> > We prove the forward direction. Suppose $\lim_{x\rightarrow a} f(x) = L$.  Then if there is a sequence $(x_n)$ in the domain of $f$, satisfying $x_n \neq a$ for all $n$ and $x_n \rightarrow a$, we can link the definition of the convergence of functions to the definition of the conversion of sequences like this: 
> >
> > Let $\epsilon > 0$ be given. 
> >
> > For $f(x)$, since we suppose that  $\lim_{x\rightarrow a} f(x) = L$, by the $\epsilon-\delta$ definition of limits, there exists a $\delta = \delta(\epsilon)$ such that 
> > $$
> > 0 < |x - a| < \delta \Longrightarrow |f(x) - L| < \epsilon. \tag{1}
> > $$
> > For $(x_n)$, since we say that $x_n \neq a$ for all $n$, we have that $|x_n - a| > 0$ for all $n$. Also, since $x_n \rightarrow a$, $\exists K \in \mathbb{N}$ such that 
> > $$
> > 0 < |x_n - a| < \delta,~~~\forall n\geq K. \tag{2}
> > $$
> >
> > >  **Intuition**: When discussing the convergence of a sequence, if we say that a sequence $(x_n)$ converges to $L$, this means that given a certain distance, $\epsilon$ from the supposed limit of $L$, past a certain $x_i$ in the sequence, all subsequent members $x_{i + 1}, x_{i + 2},...$ will all be less than $\epsilon$ - distance away from $L$. This is formally written as:
> > >
> > >  $L$ is the limit of $(x_n)$ if for every $\epsilon > 0$, there exists $K = K(\epsilon) \in \mathbb{N}$ such that $|x_n - L| < \epsilon, ~~\forall n \geq K$.
> >
> > So given an $\epsilon$, we are assured that there is a deleted $\delta$-neighbourhood around $x = a$ within which $f(x)$ is less than $\epsilon$ - distance from $L$. Then we take that $\delta$ and say that since our sequence is convergent, there must be some point after which all members of that sequence is less than $\delta$ - distance from a. So combining $\ref{second}$ with $\ref{first}$, we see that
> >
> > ​																			When $n \geq K$,  
> >
> > ​																   we get $0 < |x_n - a| < \delta$, 
> >
> > ​													  which by $\ref{first}$ implies that $|f(x_n) - L| < \epsilon$.
>
> > To prove the reverse direction, we prove the contrapositive statement. Meaning, we show that if $\lim_{x\rightarrow a} f(x) \neq L$, then there cannot be any sequence for which $f(x_n) \rightarrow L$. 
> >
> > Suppose $\lim_{x \rightarrow a} f(x) \neq L$.  Then there exists some aberrant $\epsilon_0 > 0$ such that for each $\delta > 0$,  $\exists x = x(\delta)$ such that 
> > $$
> > 0 < |x - a| < \delta \text{ but } |f(x) - L| \geq \epsilon_0.
> > $$
> > For each $n \in \mathbb{N}$, take $\delta = \frac{1}{n}$. Then $\exists x_n$ such that $0 < |x_n - a| < \frac{1}{n}$, yet $|f(x_n) - L| \geq \epsilon_0$. This means that $(x_n) \rightarrow a$ yet $f(x_n) \not \rightarrow L$.  
>
> 
>
> We can use the sequential criterion to show that a limit of a function is not equal to some value: 
>
> > If you find a $(x_n)$ such that $x_n \rightarrow a$  yet $f(x_n) \not \rightarrow L$, then $\lim_{x\rightarrow a}f(x) \neq L$. 

___

*[Chapter 6, Page 1]* Define the divergent criterion for functions.

> Answer: $\lim_{x\rightarrow a}f(x)$ **does not exist** if:
>
> - you find a sequence $(x_n)$ that is in the domain of $f$, tends to a, and does not have any $x_i = a$, and you prove that $f(x_n)$ diverges.
> - you find two sequences $(x_n)$ and $(y_n)$ in the domain of $f$, $x_n, y_n \neq a$ for all $n$  and $x_n, y_n \rightarrow a$, yet $\lim_{n\rightarrow \infty} f(x_n) \neq \lim_{n\rightarrow \infty} f(y_n)$.

___

*[Chapter 6, Page 1]* Suppose that the limit $\lim_{x \rightarrow a} f(x) = L$ exists.

1. Prove that if $L > 0$, then there exists $\delta > 0$ such that 
   $$
   0 < |x - a| < \delta \Longrightarrow f(x) > 0.
   $$

   > Answer: By our supposition, we know that for all $\epsilon > 0$, there exists $\delta = \delta(\epsilon) > 0$ such that
   > $$
   > 0 < |x - a| < \delta \Longrightarrow |f(x) - L| < \epsilon. \tag {1}
   > $$
   > Let $\epsilon = \frac{L}{2}$. Clearly $\epsilon > 0$. Then by (1), there must exist some $\delta_0$ such that 
   > $$
   > 0 < |x - a| < \delta_0 \Longrightarrow |f(x) - L| < \frac{L}{2}.
   > $$
   > We can expand the right-hand side of the expression to get
   > $$
   > -\frac{L}{2} < f(x) - L < L/2
   > $$
   > Adding $L$ across the whole expression, we see that
   > $$
   > 0 < \frac{L}{2} <f(x) < L~~~~\square
   > $$

2. Prove that if $L \neq 0$, then there exists $\delta > 0$ such that 
   $$
   0 < |x - a| < \delta \Longrightarrow f(x) \neq 0.
   $$

   > Answer: We note that equation (1) still holds true. Furthermore, if $L > 0$, then our previous answer holds. It suffices to show that if $L < 0$, then there exists $\delta > 0$ such that the above expression is true.
   >
   > Let $\epsilon = -L > 0$. Then there must be a $\delta_0$ such that 
   > $$
   > 0 < |x - a| < \delta_0 \Longrightarrow |f(x) - L| < -L.
   > $$
   > Expanding the right side, we get
   > $$
   > L < f(x) - L < -L
   > $$
   > Again, adding L across the whole expression, we get
   > $$
   > 2L < f(x) < 0 \Longrightarrow f(x) \neq 0. ~~\square
   > $$

___

*[Chapter 6, Page 2]* Define continuity.

> Answer: A function $f$ is said to  be *continuous* at $a$ if $\lim_{x \rightarrow a} f(x) = f(a)$.

___

*[Chapter 6, Page 2]* Technical explanation: Write down the $\epsilon-\delta$ definitions for the 15 types of limits:

![image-20210111082804158](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210111082804158.png)

> Answer: Two sample answers are provided below.
>
> $\lim_{x\rightarrow a^+}f(x) = L \in \mathbb{R}$ means that for all $\epsilon > 0$, there exists a $\delta$ such that
> $$
> a < x < a + \delta \Longrightarrow |f(x) - L| < \epsilon
> $$
> $\lim_{x\rightarrow \infty}f(x) = L \in \mathbb{R}$ means that for all $\epsilon > 0$, there exists a value $M > 0$ such that
> $$
> x > M \Longrightarrow |f(x) - L| < \epsilon
> $$
> 

___

*[Chapter 6, Page 2]* Define differentiability.

> Answer: A function $f$ is *differentiable* at the point $a$ if $f$ is defined in some open interval containing $a$ and the limit 
> $$
> f'(a) = \lim_{x\rightarrow a}\frac{f(x) - f(a)}{x - a}
> $$
> exists. We say that $f'(a)$ is the *derivative* of $f$ at $a$.
>
> An equivalent way of expressing the derivative is to let $h = x - a$, such that
> $$
> f'(a) = \lim_{h \rightarrow 0} \frac{f(a + h) - f(a)}{h}.
> $$
> We call $f'(a)$ the slope of the tangent line to the curve $y = f(x)$ at $x=a$.
>
> > Intuition: See picture below - the secant line PQ approximates the tangent at P. The limit of the tangent of PQ is the limit of the tangent of P.
>
> ![image-20210111083351815](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210111083351815.png)

___

*[Chapter 6, Page 2]* Define differentiability on an open interval and a closed interval.

> Answer: 
>
> **Differentiable functions on open intervals** 
>
> If $f$ is differentiable at every point in $(a,b)$, then we say that $f$ is differentiable on $(a,b)$. 
>
> > **Intuition**: Within the bounds of $(a,b)$, you can always find a small deleted neighbourhood for any point.
>
> **Differentiable functions on closed intervals**
>
> If the function $f : [a,b] \rightarrow \mathbb{R}$ is such that 
>
> 1. $f$ is differentiable on $(a,b)$; and
>
> 2. the one-sided limits
>    $$
>    L_1 = \lim_{x \rightarrow a^+} \frac{f(x) - f(a)}{x - a}, L_2 = \lim_{x \rightarrow b^-} \frac{f(x) - f(b)}{x - b}
>    $$
>    exist, then we say that $f$ is differentiable on $[a,b]$. 
>
>    We define $f'(a) := L_1, ~ f'(b) := L_2$. 
>
> >  **Intuition**: You cannot define a two-sided limit at the two endpoints of the closed range so we must make a concession.

___

*[Chapter 6, Page 3]* How should we define differentiable functions on other types of intervals $[a, b)$, $[a, \infty)$, $(a,b]$, $(-\infty, b]$ and $(-\infty, \infty)$?

> Answer: Where there are closed ranges, use 1-sided limits.
>
> For example: 
>
> - We say that the function $f: [a, b) \rightarrow \mathbb{R}$ is differentiable on $[a,b)$ if:
>   - $f$ is differentiable on (a,b);
>   - and the one-sided limit $L_1 = \lim_{x \rightarrow a^+} \frac{f(x) - f(a)}{x - a}$ exists.

___

*[Chapter 6, Page 3]* Define continuous differentiability.

> Answer: We say that $f$ is continuously differentiable on an interval $I$ if $f$ is differentiable on $I$ and $f'$ is continuous on $I$.
>
> > **Intuition**: Continuously differentiable means there isn’t a point in $I$ where you suddenly cannot differentiate.
>
> The collection of all functions which are continuously differentiable on $I$ is denoted by $C^1(I)$. 

___

*[Chapter 6, Page 3]* Prove that for any constant c, $\frac{d}{dx} (c) = 0$.

> Answer: Let $f(x) = c$. Then 
> $$
> f'(x) = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h} = \lim_{h \rightarrow 0} \frac{c - c}{h} = 0.
> $$
> since $f(x) = c$ for all $x \in \mathbb{R}$.

___

*[Chapter 6, Page 3]* Prove that if $\frac{d}{dx} f(x) = 0$, then $f(x)$ is constant. 

>  **To be demonstrated** 

___

*[Chapter 6, Page 3]* Prove that $\frac{d}{dx} (x) = 1$.

> Answer: Let $f(x) = x$. Then 
> $$
> f'(x) = \lim_{h \rightarrow 0} \frac{f(x + h) - f(x)}{h} = \lim_{h \rightarrow 0} \frac{x + h - x}{h} = 1.
> $$

___

*[Chapter 6, Page 3]* Prove that for $n \in \mathbb{N}$, $\frac{d}{dx}(x^n) = nx^{n -1}.$ 

> Answer:  Let $f(x) = x^n$. Then 
> $$
> \lim_{h \rightarrow 0} \frac{(x + h)^n - x^n}{h} =\lim_{h \rightarrow 0} \frac{nx^{n-1}h + ...}{h} = \lim_{h \rightarrow 0}nx^{n - 1} = nx^{n-1}.
> $$

___

*[Chapter 6, Page 4]* Prove that if $f$ is differentiable at $a$, then it is continuous at $a$. 

*Hint: write down the definition of continuity, then manipulate the left-hand term to create the differential term.*

> Answer: 
>
> $\lim_{x \rightarrow a} f(x) = \lim_{x \rightarrow a}\{f(x) - f(a)\} + \lim_{x \rightarrow a} f(a)$
>
> $= \lim_{x \rightarrow a} \{\frac{f(x) - f(a)}{x - a} \times (x-a)\} + f(a)$
>
> = $\lim_{x \rightarrow a}\frac{f(x) - f(a)}{x - a} \times \lim_{x \rightarrow a}(x - a) + f(a)$
>
> = $f(a)$.
>
> > **Intuition**: The continuity of $f$ depends on the limit of $f$ being equal to $f(a)$ for all $a$. Differentiability of $f$ depends on the value of $\lim_{x \rightarrow a} \frac{f(x) -  f(a)}{x- a}$ being defined. So to derive this proof, first set $\lim_{x \rightarrow a}f(x) = f(a)$, and see how you can fit the term $\lim_{x \rightarrow a} \frac{f(x) -  f(a)}{x- a}$ in between the two terms.
>
> The proof above uses ***Theorem 4.3.2*** from MA2108.
>
> > **Theorem 4.3.2** Suppose that $\lim_{x \rightarrow a}f(x) = L$ and $\lim_{x \rightarrow a}g(x) = M$. 
> >
> > 1. $\lim_{x \rightarrow a}(f \pm g)(x) = \lim_{x \rightarrow a} f(x) \pm \lim_{x \rightarrow a}g(x) = L \pm M$.
> >
> > 2. $\lim_{x \rightarrow a}(f \cdot g)(x) = \lim_{x \rightarrow a} f(x) \times \lim_{x \rightarrow a}g(x) = LM$.
> >
> > 3. If $g(x) \neq 0$ in a deleted neighbourhood of a and $\lim_{x \rightarrow a} g(x) = M \neq 0$, then 
> >    $$
> >    \lim_{x \rightarrow a}\left(\frac{f}{g}\right)(x) = \frac{\lim_{x \rightarrow a} f(x)}{\lim_{x \rightarrow a}g(x)}   = \frac{L}{M}.
> >    $$
>
> The contrapositive of this theorem says that if $f$ is not continuous at $a$, then it is not differentiable at $a$.
>
> The converse is not true, $f$ continuous at $a$ $\not \Longrightarrow$ $f$ differentiable at $a$.
>
> For example: $f(x) = |x|$ is continuous, but not differentiable at 0.

___

*[Chapter 6, Page 4]* Prove that $f(x) = |x|$ is continuous, but not differentiable at 0.

> Answer:  Let $\epsilon > 0$ be given. Then let $\delta = \epsilon$ such that
> $$
> -\delta < x < 0 \Longrightarrow |x| < \delta = \epsilon.
> $$
> Hence $\lim_{x \rightarrow 0^-} |x| = 0$. Similarly we can show that $\lim_{x \rightarrow 0^+} |x| = 0$. Hence $f(x) = |x|$ is continuous at 0. 
>
> Comparing the left and right hand derivatives of f(x), we see
>
> $\lim_{x \rightarrow 0^+} \frac{f(x) - f(0)}{x - 0} = \lim_{x \rightarrow 0^+} \frac{x}{x} = 1,$ but $\lim_{x \rightarrow 0^-} \frac{f(x) - f(0)}{x - 0} = \lim_{x \rightarrow 0^+} \frac{-x}{x} = -1.$ 
>
> Since the two derivatives are not equal, $f’(0)$ does not exist, and $f$ is not differentiable at 0.

___

*[Chapter 6, Page 5]* Prove that $\frac{d}{dx} [f(x) \pm g(x)] \Big|_{x=a} = f'(a) \pm g'(a)$, assuming $f$ and $g$ are differentiable.

> **Answer**: 
> $$
> \begin{aligned}
> \frac{d}{dx} [f(x) \pm g(x)] \Big|_{x=a} &= \lim_{x \rightarrow a} \frac{[f(x)\pm g(x)] - [f(a) \pm g(a)]}{x - a}
> \\ &= \lim_{x \rightarrow a} \frac{f(x) - f(a)}{x - a} \pm \lim_{x \rightarrow a} \frac{g(x) - g(a)}{x - a}
> \\ &= f'(x) \pm g'(x).
> \end{aligned}
> $$

*[Chapter 6, Page 5]* Prove that $\frac{d}{dx}f(x)g(x)\Big|_{x=a} = f'(a)g(a) + f(a)g'(a)$. (Product rule)

> **Answer**: 
> $$
> \begin{aligned}
> 	\frac{d}{dx} f(x)g(x) \Big|_{x=a} =& \lim_{x \rightarrow a} \frac{f(x)g(x) - f(a)g(a)}{x - a} \\
> 	=& \lim_{x \rightarrow a} \frac{f(x)g(x) - f(x)g(a) + f(x)g(a) - f(a)g(a)}{x - a} \\
> 	=& \lim_{x \rightarrow a} \Big\{f(x) \cdot \frac{g(x) - g(a)}{x - a}\Big\} + \lim_{x \rightarrow a} \Big\{g(x) \cdot \frac{f(x) - f(a)}{x - a}\Big\}
>     \\ =& f(a)g'(a) + f'(a)g(a).
> \end{aligned}
> $$
> 

*[Chapter 6, Page 5]* Prove that if $g(a) \neq 0$, then 
$$
\frac{d}{dx}\frac{f(x)}{g(x)}\Big|_{x=a} = \frac{f'(a)g(a) - f(a)g'(a)}{(g(a))^2}
$$

> **Answer**: 
> $$
> \begin{aligned}
> 	\frac{d}{dx}\frac{f(x)}{g(x)}\Big|_{x=a} &= \lim_{x \rightarrow a} \frac{\frac{f(x)}{g(x)} - \frac{f(a)}{g(a)}}{x - a} \\
> 	&= \lim_{x \rightarrow a} \frac{f(x)g(a) - f(a)g(a) + f(a)g(a) - g(x)f(a)}{g(x)g(a)(x - a)}
> \\ &= \lim_{x \rightarrow a} \frac{1}{g(x)g(a)} \Big\{\frac{f(x) - f(a)}{x - a} \cdot g(a) - f(a) \frac{g(x)- g(a)}{x - a}\Big\} \\
> &= \frac{1}{(g(a))^2} \big\{f'(a)g(a) - f(a)g'(a)\big\}.
> \end{aligned}
> $$

___

*[Chapter 6, Page 6] State and prove **Caratheodory’s Theorem.**

> **Answer**: 
>
> ![image-20210113093425701](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113093425701.png)
>
> Let $I$ be an interval,  $f: I \rightarrow \mathbb{R}$ and $c \in I$. Then $f'(c)$ exists if and only if there is a function $\phi$ on I such that $\phi$ is continuous at $c$ and 
> $$
> f(x) - f(c) = \phi(x)(x - c) ~~ \forall x\in I.
> $$
> In this case, $f'(c) = \phi(c)$.
>
> > Proof: 
> >
> > $(\Longrightarrow)$ Assume $f'(c)$ exists. Then 
> > $$
> > \lim_{x \rightarrow c} \phi(x) =\lim_{x \rightarrow c} \frac{f(x) - f(c)}{x - c} = f'(c) \text{ exists.}
> > $$
> > So we define $\phi(c) = f'(c)$. Then $\phi$ is continuous at c (since it’s differentiable).
> >
> > ($\Longleftarrow$) Assume there is a function $\phi$ on $I$ such that $\phi$ is continuous at $c$. Then
> > $$
> > \lim_{x \rightarrow c} \phi(x) = \phi(c) \tag{definition of continuity}
> > $$
> > and since 
> > $$
> > \lim_{x \rightarrow c} \phi(x) = \lim_{x \rightarrow c} \frac{f(x) - f(c)}{x -c} ~~\tag {by definition},
> > $$
> > $f'(c) = \phi(c)$ (implying it’s existence). 

# Lecture 2

Recap:

![image-20210113080752075](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113080752075.png)

___

*[Chapter 6, Page 7]* State the necessary condition for a real function to be composed with another real function.

> **Answer**: Suppose $f: J \rightarrow \mathbb{R}$ and $g: I \rightarrow \mathbb{R}$. 
>
> ![image-20210113081502887](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113081502887.png)
>
> Then $f(J)$ must be a subset of $I$. 
>
> **Intuition**: All outputs from $f$ must be acceptable to $g$.

___

*[Chapter 6, Page 7]* State and prove the **chain rule**.

> **Answer**: If $h = g \circ f$, then $h'(a) = g'(f(a))f'(a)$. 
>
> **Conditions: $f$ and $g$ are differentiable at $a$ and $f(a)$ respectively and $f(J) \subseteq I$.** 
>
> First, recall Theorem 5.2.1 from MA2108.
>
> ![image-20210113094151186](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113094151186.png)
>
> ![image-20210113082722170](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113082722170.png)

___

*[Chapter 6 Page 7]* State the other form of the chain rule and it’s purpose.

> Answer: 
>
> ![image-20210113082915101](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113082915101.png)
>
> ![image-20210113082949267](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113082949267.png)

___

*[Chapter 6 Page 7]* <img src="C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113083014228.png" alt="image-20210113083014228" style="zoom:67%;" />

> **Answer**: 
>
> ![image-20210113083632791](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113083632791.png)
>
> **intuition**: When $x \neq 0$, the derivative of $f$ is the the derivative of $x^2\sin\frac{1}{x}$. 
>
> Also you cannot say derivative is $0$ at $0$ because there is no open interval around $0$ - it’s just a point.
>
> But you can use the definition of limits to get $f’(0)$.

___

*[Chapter 6 Page 8]* Is $f$ in the previous question continuously differentiable on $\mathbb{R}$? That is, is $f \in C^1(\mathbb{R})$?

> **Answer**: Asking if $f$ is continuously differentiable is the same as asking if $f’$ is continuous on $\mathbb{R}$.
>
> This proof uses Theorem 5.2.1 which is pasted 2 questions above.
>
> ![image-20210113084333863](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113084333863.png)

___

*[Chapter 6, Page 8]* State and prove the Inverse Function Theorem.

> **Answer**: 
>
> First recall the definition of inverse functions.
>
> ![image-20210113085401633](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113085401633.png)
>
> **Intuition**: If the inverse wasn’t monotone and continuous, then if you interchange the role of $f$ and $f^{-1}$, you get a contradiction.
>
> 
>
> The inverse function theorem says
>
> <img src="C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113085625390.png" alt="image-20210113085625390" style="zoom:67%;" />
>
> **Proof**:
>
> Starting point: Since $g \circ f (x) = x$, and by the chain rule $g'(f(c))f'(c) = 1$, then the theorem is there.
>
> The problem with writing just the above is that you assume that  $g'(f(c))$ exists already.
>
> So you need to use Caratheodory’s theorem to prove that  $g'(f(c))$ exists.
>
> The proof uses this statement which was set as a question in Lecture 1 : if $L \neq 0$, $\exists ~\delta$ such that $f(x) \neq 0$ in the delta neighbourhood around c.
>
> >  **Intuition:** U is an interval because of the continuous inverse theorem
>
> ![image-20210113091332915](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113091332915.png)

___

*[Chapter 6 Page 8]* What happens if $f'(c) = 0$? in the above slide?

> Answer: Tutorial 1

___

*[Chapter 6, Page 9]* 

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113091507781.png" alt="image-20210113091507781" style="zoom: 67%;" />



> Answer: You need to see that $g(y)$ is strictly monotone and continuous. Use the inverse function theorem. So we must check all the conditions for that theorem.
>
> ![image-20210113091952828](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113091952828.png)
>
> > **Intuition**: 
> >
> > - First you look at its inverse function without saying that it is the inverse, because you need to check if it is strictly monotone and differentiable in the whole interval $I$. 
> > - So after we verify these two conditions for $x^n$, we then check if the composition of $g \circ f$ and $f \circ g$ give us the identity functions for the direct image and inverse image. If we also get this, then we know that $f$ and $g$ are inverses of each other.
> > - Now you say that $x = y^{\frac{1}{n}}$. (Basically create a variable for the inverse of your given variable.)
> > - Then say that $f(x) = y$. (Basically the inverse function applied to the inverted variable gives you your original given variable.)
> > - Differentiate $f(x)$ and say that because the original function $g$ is differentiable at y, you can directly apply the inverse function theorem.

___

*[Chapter 6, Page 9]* 

![image-20210113092052862](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113092052862.png)

> Answer: // need completeness property of Q
>
> // also use ![image-20210113092317722](C:\Users\User\Documents\AY20-21-Semester-2\MA3110\Mega Problem Set\Mega Problem Set.assets\image-20210113092317722.png)
>
> + and chain rule