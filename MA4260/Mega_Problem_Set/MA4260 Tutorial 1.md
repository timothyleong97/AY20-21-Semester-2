# MA4260 Tutorial 1

1. Suppose I arrive at an $M/M/k/FCFS/k + 1/\infty$ queueing system when all servers are busy. What is the probability that I will complete service before at least one of the k customers in service? 

   **Answer:**

   We can calculate the complement probability instead, which is the probability that I am last to finish service.

   Since service time is governed by a memoryless distribution, my service time has the same distribution as that of the other $k - 1$ customers who are already being served. Hence,  I should have a $\frac{1}{k}$ chance of being the last to complete service by symmetry. Therefore, the probability that I complete service before at least one of the k customers in service is $\frac{k - 1}{k}$. 

---

2. The time between arrivals of buses follows an exponential distribution with a mean
   of one hour.

   *What is the probability that exactly four buses will arrive within the next 2 hours?*

   **Answer:**

   Since the inter-arrival times of buses follows an exponential distribution with $\lambda = 1$, the number of buses arriving within 2 hours follows a Poisson distribution with $\lambda = 2$. Let $X$ be the number of buses arriving within the next 2 hours. Then $P(X = 4) = \frac{e^{-2}(2)^4}{4!} = \frac{2e^{-2}}{3}$.

   +++
   
   *What is the probability that at least two buses will arrive during the next 2 hours?*
   $$
   \begin{aligned}
   P(X >= 2) &= 1 - P(X = 1) - P(X = 0) \\
   &= 1 - 3e^{-2}
   \end{aligned}
   $$
   ___
   
   *What is the probability that no buses will arrive during the next 2 hours?*
$$
   P(X = 0) = e^{-2}
$$
+++

   *A bus has just arrived. What is the probability that the next bus will arrive between 30 and 90 minutes?*

   Let $X$ be the time in hours between successive bus arrivals. The mean number of arrivals per hour is exponential with parameter 1. $P(0.5 \leq X \leq 1.5) = P(X \leq 1.5) - P(X \leq 0.5) = 1 - e^{-1.5} - 1 + e^{-0.5} = e^{-0.5} - e^{-1.5}$.

___

3. Suppose a queueing system has two servers and each of them has an exponentially distributed service time with a mean of 2 hours. Suppose the interarrival time is exponentially distributed with a mean of 2 hours. Furthermore, suppose a customer just arrived at 12:00 noon.

   *What is the probability that the next arrival will come (i) before 1:00pm? (ii) between 1:00pm and 2:00pm? (iii) after 2:00pm?*

   Let $T$ be the time in hours between successive arrivals. The mean number of customers per hours is exponential with parameter or rate $\frac{1}{2}$ customer per hour. Thus $T\sim \exp(\frac{1}{2})$ and $P(T \leq 1) = 1 - e^{-\frac{1}{2}}$. $P(1 \leq T \leq 2) = P(T \leq 2) - P(T \leq 1) = e^{-\frac{1}{2}} - e^{-1}$. $P(T \geq 2) = e^{-1}$.

   ___

   *Suppose that no additional customers arrive before 1:00pm. Now, what is the probability that the next arrival will come between 1:00pm and 2:00pm*

   Since exponential distributions are memoryless, $P(T \leq 1) = 1 - e^{-\frac{1}{2}}$.

   ___

   *What is the probability that the number of arrivals between 1:00pm and 2:00pm is (i) zero, (ii) one or two or (iii) two or more?*

   Let $X$ be a Poisson variable for the number of arrivals between 1:00pm and 2:00pm. Then $X \sim Poisson(\frac{1}{2})$. $P(X = 0) = e^-{\frac{1}{2}}$, $P(X = 1) + P(X = 2) = \frac{1}{2}e^{-\frac{1}{2}} + \frac{1}{8}e^{-\frac{1}{2}} =  \frac{5}{8}e^{-\frac{1}{2}}$, $P(X > 1) = 1 - P(X = 0) - P(X = 1) = 1 - e^{-\frac{1}{2}} - \frac{1}{2}e^{-\frac{1}{2}} = 1 - \frac{3}{2}e^{-\frac{1}{2}}$.  

   ___

   *Suppose that both servers are serving customers at 1:00pm. What is the probability that neither customers will have service completed (i) before 2:00pm? (ii) before 1:10pm? (iii) before 1:01pm?*

   Let X and Y be exponential variables for the service time of each server.

   i) $P(X > 1)*P(Y > 1) = e^{-1}$

   ii) $P(X > \frac{1}{6}) * P(Y > \frac{1}{6}) = e^{-\frac{1}{6}}$

   ii) $P(X > \frac{1}{60}) * P(Y > \frac{1}{60}) = e^{-\frac{1}{60}}$. 

___

4. Let T be the random variable for waiting time. Then $\mathbb{E}(T) = \frac{1}{2} * \frac{1}{4} + \frac{1}{4} + 1  = 1 \frac{3}{8}h$. 

___

5. Let $X$ be exponentially distributed, i.e. $X \sim \exp(\lambda)$.

   $P(X < \frac{1}{\lambda}) = 1 - e^{-1} = 63.2\%$.

   $P(X < \frac{1}{2\lambda}) = 1 - e^{-\frac{1}{2}} = 39.3\%$.  

   ii) Reasonable when arrival rate is stationary, arrivals defined on non-overlapping time intervals are independent and there are no bulk arrivals. Unreasonable when otherwise

---

6. It is known that the interarrival time $T\sim U[0,u]$. Let $t_0$ denote the time now and
   suppose that there has not been any arrivals since $a_0$. Suppose $t_0 - a_0 < u$. What
   is the distribution of the remaining waiting time?

   For $t \in [a_0, u]$, 
   $$
   \begin{aligned}
   P(T \geq t_0 | T \geq a_0) =& \frac{P(T \geq t_0 \cap T \geq a_0)}{P(T \geq a_0)} \\
   =& \frac{P(T \geq t_0)}{P(T \geq a_0)} \\
   =& \frac{\frac{u - t_0}{u}}{\frac{u - a_0}{u}} \\
   =& \frac{u - t_0}{u - a_0}
   \end{aligned}
   $$
   So 
   $$
   \begin{aligned}
   P(T \leq t_0 | T \geq a_0) &= 1 - P(T \geq t_0 | T \geq a_0) \\
   &= 1 - \frac{u - t_0}{u - a_0} \\
   &= \frac{t_0 - a_0}{u - a_0}.
   \end{aligned}
   $$

---

