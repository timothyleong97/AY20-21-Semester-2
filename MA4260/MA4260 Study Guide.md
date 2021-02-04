[toc]

# MA4260 Stochastic Operations Research

## Overview

### Basic info

- Lecturer: SOH Yong Sheng
- Office: S17 #07-02
- Email: matsys@nus.edu.sg (preferred)

### Administrative matters

- Lectures on Wednesday and Friday, 4-6pm
- Tutorial on Tuesday 10-11am
- In-class quizzes (approximately 11) - 10%
- Assignments (3 to 4) - 30%
- Midterm (online, cheat sheet allowed, maybe open-book) - 20%
- Final (online, cheat sheet allowed, maybe open-book) - 40% *(tentatively Tuesday, 4 May 2021 5-7:30pm)*

### Objectives of this course

- Operations research (OR) is about using analytical methods to make better decisions
- Stochastic OR deals with inherent stochasticity and uncertainty in our problem.
- Focus of this course will be
  - the process of abstracting conceptual problems in terms of mathematical models
  - analysing these models
  - deriving useful operation insights from these analyses

> “All models are wrong, but some are useful” ~ generally attributed to G. Box, a statistician

## Lecture 1 - Queueing theory

### Examples of queues

- Cars at a stoplight
- Planes waiting for take off
- Broken machines waiting to be repaired by a repairman.
- Programs waiting to be processed by a digital computer
- Letters waiting to be typed by a secretary

### Conceptual questions

- Average queue length
- Average waiting time
- What fraction of the time is each server idle?
- Probability distribution of a customer’s waiting time?
- Probability distribution of the number of customers present in the queue?
- If a bank manager wants to ensure that only $1\%$ of all customers will have to wait more than 5 minutes for a teller,
  how many tellers should he/she employ?

###  Basic structure of queueing models

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113163817146.png" alt="image-20210113163817146" style="zoom:50%;" />

- Customers are the items that require processing.
- The service mechanism chooses which customer to serve and serves the customer.
- Once a customer is processed, the customer is de-queued.
- If there are insufficient servers for customers, customers must wait

#### Terminology of queue theory

- ***Calling population*** refers to where the customers are coming from. 
- The event of being enqueued is called an ***arrival***.
- The event of leaving the queue is called a ***departure***.

#### Basic elements of a queue

1. **Arrival process**

   - Assume single arrivals (e.g. bulk arrivals are not allowed)

   - Assume arrival process is independent of the number of customers in the system.

   - Characterised by the distribution of the inter-arrival time (how long it takes the next customer to enter the queue).

2. **Service process** (when a customer meets the service mechanism)
   + Assume service process is independent of the number of customers in the system.
   + Characterised by distribution of service time (how long it takes to serve a customer) distribution.

3. **Design of service mechanism**
   - Number of servers
   - In parallel (e.g. bank tellers), in series (e.g. processing a product on a sequence of machines), or in a network (e.g. hospital - different customers bounce around between different servers within the network of doctors).
4. **Queue discipline** 
   - FIFO
   - LIFO
   - SIRO (service in random order)
   - PP (Pre-emptive priority, e.g. emergency cases) 
     - if someone comes in while a customer is being served, and that customer has a higher priority than the one being served, the current customer will get re-enqueued.
   - NPP (Non-pre-emptive priority, e.g. computer time-sharing)
   - GD (General discipline) *(no assumptions)*

5. **System capacity** 
   - Finite or infinite (if a queue runs indefinitely, it’s easier to analyse)
   - Assumed to be in a single line
6. **Calling population**
   - Finite or infinite (if the population is indefinitely large, it’s easier to analyse as well)

### Kendall-Lee Notation 

- Shorthand way of specifying the above parameters



<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113165346197.png" alt="image-20210113165346197" style="zoom:67%;" />

> **Difference between memoryless-ness and independence**
>
> ![image-20210114084233069](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210114084233069.png)
>
> In the case of memoryless-ness, any value can be “ground zero”.

### The waiting time paradox

Suppose the interarrival time between buses at a bus-stop follows an exponential distribution $T \sim exp(\lambda)$ with mean $\frac{1}{\lambda} = 10$ minutes. A random passenger arrives at the bus-stop. What is the expected wait for the next bus? 

> **Answer**: 10 minutes 

It seems unintuitive that if you arrive randomly between bus arrivals, you should still expect to wait 10 minutes.

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113170657670.png" alt="image-20210113170657670" style="zoom:50%;" />

> **Intuition:** For a memoryless probability distribution, even after you have waited 9 minutes and 59 seconds, your expected waiting time is still 10 minutes. This is because how long you have already waited makes no difference in your subsequent waiting time.

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113170946270.png" alt="image-20210113170946270" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113171119754.png" alt="image-20210113171119754" style="zoom:50%;" />

> **Intuition**: $\mathbb{P}(T_A = t_i)$ is derived by taking the total slice of time occupied by all $t_i$s and dividing that by the combined length of all intervals.

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113171819187.png" alt="image-20210113171819187" style="zoom:67%;" />

## Lecture 1.1 The Exponential Distribution and the Poisson Process

### Exponential distribution

We say that a random variable $T \sim \exp(\alpha)$ has an **exponential distribution with parameter** $\alpha$ if it’s probability density function is 

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113172213805.png" alt="image-20210113172213805" style="zoom:50%;" />

The **cumulative density function** of T is 


$$
\mathbb{P}(T \leq t) = 1 - \exp(-\alpha t) \text{ for } t \geq 0,
\\ \text{ and}
\\ \mathbb{E}(T) = \frac{1}{\alpha},~ \text{Var}(T) = \frac{1}{\alpha^2}.
$$

> If someone tells you that some distribution is modelled as an exponential one, you **need to check if one of $\mathbb{E}(T)$ and $\text{Var}(T)$ is a square of the other.** Also plot the histogram to see if it looks like the curve above.

### Poisson distribution

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113172808585.png" alt="image-20210113172808585" style="zoom:50%;" />

> To check if a distribution is Poisson, check if the **sample mean is roughly equal to the sample variance.**

### Counting process

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113173007803.png" alt="image-20210113173007803" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113173037034.png" alt="image-20210113173037034" style="zoom:50%;" />

### Poisson process

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113173236118.png" alt="image-20210113173236118" style="zoom:50%;" />

> **Intuition**; Suppose that in the example above, once a bus comes, the time for the next bus to come follows an exponential distribution. Then we have the property that in any time interval, e.g. from 0 to 5, the number of buses that arrive in that time is a Poisson random variable. Conversely, if for every interval, the number of points in there always follow a Poisson random variable (for any t), then we can say that the time between any 2 buses follows an exponential distribution with a parameter $\alpha$.  

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115161325419.png" alt="image-20210115161325419" style="zoom:50%;" />

### Memoryless Property

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115161554212.png" alt="image-20210115161554212" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115161800634.png" alt="image-20210115161800634" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115161901729.png" alt="image-20210115161901729" style="zoom:50%;" />

> Recall that for a Poisson process, inter-arrival time follows a Poisson distribution.
>
> For the first question, you see 30 glasses of beer ordered per hour.
>
> Now you are using a time unit of 4 hours so the $\alpha = 4 * 30 = 120$,
>
> For a Poisson distribution, the mean equals variance.

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115162149137.png" alt="image-20210115162149137" style="zoom:50%;" /> 

> **Intuition**: If 30 means 30 glasses in an hour, then the inter-order time which is modelled as $T \sim \exp(\lambda)$ means
>
> if you ask for $P(T \leq t)$, the small $t$ is also in units of hour - so if you want units of minutes, the $\lambda$ needs to be divided by 60 to get the probability 
>
> that $P(T \leq t)$ where t is now in minutes.

### Properties of the exponential distribution

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115162537136.png" alt="image-20210115162537136" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115162826992.png" alt="image-20210115162826992" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115163005624.png" alt="image-20210115163005624" style="zoom:50%;" />



### Properties of the Poisson process

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115163310386.png" alt="image-20210115163310386" style="zoom:50%;" />

> Reasoning: They happen together so their means add up. Remember to unitise them as well (not some per hour, some per min for e.g.).

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115163503609.png" alt="image-20210115163503609" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115163844772.png" alt="image-20210115163844772" style="zoom:50%;" />

> **Intuition:** If you model the interarrival events of each type of car as a set of exponentials, then the large car arriving first means that the $T_{large}$ is the  minimum of exponentials. 

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115164036247.png" alt="image-20210115164036247" style="zoom:50%;" />

> **Intuition**: Because of the minimum of exponentials theorem, the time to the next arrival is also following an exponential probability distribution. Because of the memoryless property of a Poisson process, the next arrival is always Poisson with parameter $\lambda$, it does not depend on how many arrivals happened before.

### Marked Poisson Process

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115164721538.png" alt="image-20210115164721538" style="zoom:50%;" />

> Note: The $p_i$s have to be independent.

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115164837085.png" alt="image-20210115164837085" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115165057352.png" alt="image-20210115165057352" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115165554771.png" alt="image-20210115165554771" style="zoom:50%;" />

### Erlang distribution

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115165707187.png" alt="image-20210115165707187" style="zoom:50%;" />

​	<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115170755192.png" alt="image-20210115170755192"  />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115170639351.png" alt="image-20210115170639351" style="zoom:50%;" />

## Lecture 1.2 Birth-death processes

### Introduction

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120160626792.png" alt="image-20210120160626792" style="zoom:80%;" />

### Formal definition

![image-20210120160837518](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120160837518.png)

> $n$ is allowed to depend on the state, i.e. $\lambda_n$ and $\mu_n$ can be different for different $n$.  Also state means customers being served + customers in line.

### Rate diagram

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120161048347.png" alt="image-20210120161048347" style="zoom:67%;" />

> Note: <img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120161249084.png" alt="image-20210120161249084" style="zoom:80%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120161315492.png" alt="image-20210120161315492" style="zoom:80%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120161553788.png" alt="image-20210120161553788" style="zoom: 80%;" />

### Example

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120161719059.png" alt="image-20210120161719059" style="zoom:80%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120161806300.png" alt="image-20210120161806300" style="zoom:80%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120161936281.png" alt="image-20210120161936281" style="zoom:80%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120162156495.png" alt="image-20210120162156495" style="zoom:80%;" />

> State must stop at 12 because you can only have 12 people in the system - that is, in one hour, you have 2 being served and 10 on hold at any instant.

### Checks

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120164047267.png" alt="image-20210120164047267" style="zoom:80%;" />

> **Intuition:** If birth rate always eclipses the death rate, the system cannot have a steady state.

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120164425084.png" alt="image-20210120164425084" style="zoom:80%;" />

### Steady state

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120164502575.png" alt="image-20210120164502575" style="zoom:80%;" />

#### Proof

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120164834703.png" alt="image-20210120164834703" style="zoom:80%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120165035125.png" alt="image-20210120165035125" style="zoom:80%;" />

> It’s like the max-flow, min-cut argument where how much outflow you see from state n must be matched by inflow into state n

#### Balance Equations

![image-20210120165420180](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120165420180.png)

> Our goal was to understand what $p_i$ is for all $i \in \{0\cdots n\}$

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120165536500.png" alt="image-20210120165536500" style="zoom:80%;" />

> Name of the game: Start from $p_0$, then $p_1\cdots$ 

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120165821306.png" alt="image-20210120165821306" style="zoom:80%;" />

### Example

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120170046630.png" alt="image-20210120170046630" style="zoom:80%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120170423181.png" alt="image-20210120170423181" style="zoom:80%;" />

### Important things to remember

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210120170447485.png" alt="image-20210120170447485" style="zoom:80%;" />

## Lecture 1.3 Performance measures

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122160906321.png" alt="image-20210122160906321" style="zoom:50%;" />

> **Explanation**: For $L$, N is the total number of people in the system. $s$ is the number of people being served. $\bar\lambda$ is the average number of people who successfully enter the system

### Little’s Law

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122161535713.png" alt="image-20210122161535713" style="zoom: 67%;" />e

### Example

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122161915121.png" alt="image-20210122161903226" style="zoom: 67%;" />



![image-20210122161905633](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122161905633.png)

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122161955442.png" alt="image-20210122161955442" style="zoom: 50%;" />

> Setup is always that you know the $\lambda$ and $\mu$. But once you know either 1 of the 4 things in the rectangle above, you can derive the rest.
>
> The $p_n$ for L is the steady state probabilities. So we must compute those first then get L. 

### Proof

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122162538631.png" alt="image-20210122162538631" style="zoom: 50%;" />

### M/M/1 Systems

- Arrival memoryless
- Service process memoryless
- 1 server only

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122163157529.png" alt="image-20210122163157529" style="zoom:50%;" />

> Name of the game is to represent all the $p_i$ as a multiple of $p_0$.

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122163459948.png" alt="image-20210122163459948" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122163752999.png" alt="image-20210122163752999" style="zoom:50%;" />

### Example

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122163851025.png" alt="image-20210122163851025" style="zoom: 50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122164047016.png" alt="image-20210122164047016" style="zoom:50%;" />

> For question 4, on average means in the steady state so entering rate = leaving rate

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122164057943.png" alt="image-20210122164057943" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122164247630.png" alt="image-20210122164247630" style="zoom: 50%;" />

> **Add on**: You can weight the expected waiting cost or expected service cost according to your priorities.
>
> **Intuition**: Use Little’s law to derive expected number of customers per hour, multiply that by hourly cost per customer and add cost of hiring the server.

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122165336465.png" alt="image-20210122165336465" />



<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122165704236.png" alt="image-20210122165704236" style="zoom:80%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122165827677.png" alt="image-20210122165827677" style="zoom: 67%;" />

> The cursor is covering $p_n$. 

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122170013930.png" alt="image-20210122170013930" style="zoom: 67%;" />

> **Intuition for the second equation:** Use the formula $p_{n + 1} = \rho^{n + 1}p_0$. 

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122170717819.png" alt="image-20210122170717819" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129192944655.png" alt="image-20210129192944655" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122170857668.png" alt="image-20210122170857668" style="zoom:67%;" />

> On average means in the steady state, then entering rate = leaving rate.

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122171315397.png" alt="image-20210122171315397" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122171544740.png" alt="image-20210122171544740" style="zoom: 67%;" />

> $\exp((K - n)\lambda)$ is because of the minimum of exponentials

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210122171853397.png" alt="image-20210122171853397" style="zoom: 67%;" />

## Recap



<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127161154487.png" alt="image-20210127161154487" style="zoom: 50%;" />

> How to check if steady state exists:
>
> ![image-20210127161733141](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127161733141.png)
>
> ![image-20210127161944880](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127161944880.png)

![image-20210127162056661](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127162056661.png)

### Little’s law

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127162431989.png" alt="image-20210127162431989" style="zoom: 67%;" />

> Little’s Law holds for G/G/s

![image-20210127162730876](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127162730876.png)

> GD / K / infty: Steady state always exists (slide 18)

## Lecture 1.4 Finite source queueing models

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127163301564.png" alt="image-20210127163301564" style="zoom: 67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127163410086.png" alt="image-20210127163410086" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127163612739.png" alt="image-20210127163612739" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127163730068.png" alt="image-20210127163730068" style="zoom:67%;" />

![image-20210127165120073](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127165120073.png)

![image-20210127165552539](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127165552539.png)

![image-20210127165822763](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127165822763.png)

### Example

![image-20210127165944234](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127165944234.png)

![image-20210127170151501](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127170151501.png)

![image-20210127170441147](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127170441147.png)

![image-20210127170817309](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127170817309.png)

![image-20210127171041505](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127171041505.png)

![image-20210127171312035](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127171312035.png)

![image-20210127171505902](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127171505902.png)

![image-20210127171735608](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127171735608.png)

![image-20210127172017800](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127172017800.png)

![image-20210127172557892](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127172557892.png)

![image-20210127173054808](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210127173054808.png)

## Lecture 1.6

### GI / G / $\infty$ 

- Infinite number of servers means no waiting time

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129161020333.png" alt="image-20210129161020333" style="zoom: 67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129161324016.png" alt="image-20210129161324016" style="zoom: 67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129161530466.png" alt="image-20210129161530466" style="zoom:67%;" />

> State is number of customers in the system (queueing + being served). Since number of servers is $\infty$,  combined service rate is number of customers $\times$ service rate per server

### Example

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129161940438.png" alt="image-20210129161940438" style="zoom:67%;" />

> State is number of ice cream shops that are open. Arrival rate is 3 per year, service rate is 1/10 per year.

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129162315102.png" alt="image-20210129162315102" style="zoom:67%;" />

### Models with priority queue discipline

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129163113394.png" alt="image-20210129163113394" style="zoom:67%;" />

> Pre-emptive - examples could be ER doctors, operating systems (sudden ddos-es)

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129163728664.png" alt="image-20210129163728664" style="zoom:67%;" />

![image-20210129164013065](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129164013065.png)

> PP means pre-emptive priority, with infinite queue lengths and calling populations
>

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129164853070.png" alt="image-20210129164853070" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129165238240.png" alt="image-20210129165238240" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129170002534.png" alt="image-20210129170002534" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129165831890.png" alt="image-20210129165831890" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129170018330.png" alt="image-20210129170018330" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129170218426.png" alt="image-20210129170218426" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129170410198.png" alt="image-20210129170410198" style="zoom:67%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210129170535143.png" alt="image-20210129170535143" style="zoom:67%;" />

![image-20210203160436529](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203160436529.png)

## Lecture 7

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203160846750.png" alt="image-20210203160846750" style="zoom: 50%;" />

### M/M/s: NPP/ $\infty$ /$\infty$ 

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203161014968.png" alt="image-20210203161014968" style="zoom: 33%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203161921205.png" alt="image-20210203161921205" style="zoom:33%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203162409950.png" alt="image-20210203162409950" style="zoom: 33%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203162640388.png" alt="image-20210203162640388" style="zoom: 33%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203163135624.png" alt="image-20210203163135624" style="zoom:33%;" />![image-20210203163418558](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203163418558.png)

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203163434100.png" alt="image-20210203163434100" style="zoom:33%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203163556577.png" alt="image-20210203163556577" style="zoom:33%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203163759748.png" alt="image-20210203163759748" style="zoom:33%;" />

> $P(N \geq 2)$ is a result from $M/M/s$  systems

![image-20210203164251993](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203164251993.png)

![image-20210203164306072](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203164306072.png)

![image-20210203164328180](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203164328180.png)



<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203164338924.png" alt="image-20210203164338924" style="zoom:67%;" />

![image-20210203164112101](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203164112101.png)

![image-20210203164200660](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203164200660.png)

### Recap

![image-20210203165510842](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203165510842.png)

![image-20210203165529729](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203165529729.png)

![image-20210203165648296](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203165648296.png)

## Non-exponential models

![image-20210203165933440](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203165933440.png)

![image-20210203170450707](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203170450707.png)

![image-20210203170528345](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203170528345.png)

![image-20210203170714570](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210203170714570.png)