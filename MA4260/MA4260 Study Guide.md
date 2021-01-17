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

5. Queue capacity 
   - Finite or infinite (if a queue runs indefinitely, it’s easier to analyse)
   - Assumed to be in a single line
6. Calling population
   - Finite or infinite (if the population is indefinitely large, it’s easier to analyse as well)

### Kendall-Lee Notation 

- Shorthand way of specifying the above parameters



<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113165346197.png" alt="image-20210113165346197" style="zoom:67%;" />

> **Difference between memoryless-ness and independence**
>
> ![image-20210114084233069](C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210114084233069.png)
>
> In the case of memoryless-ness, any value can be “ground zero”,

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

## Exponential distribution

We say that a random variable $T \sim \exp(\alpha)$ has an **exponential distribution with parameter** $\alpha$ if it’s probability density function is 

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113172213805.png" alt="image-20210113172213805" style="zoom:50%;" />

The **cumulative density function** of T is 


$$
\mathbb{P}(T \leq t) = 1 - \exp(-\alpha t) \text{ for } t \geq 0,
\\ \text{ and}
\\ \mathbb{E}(T) = \frac{1}{\alpha},~ \text{Var}(T) = \frac{1}{\alpha^2}.
$$

> If someone tells you that some distribution is modelled as an exponential one, you **need to check if one of $\mathbb{E}(T)$ and $\text{Var}(T)$ is a square of the other.** Also plot the histogram to see if it looks like the curve above.

## Poisson distribution

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113172808585.png" alt="image-20210113172808585" style="zoom:50%;" />

> To check if a distribution is Poisson, check if the **sample mean is roughly equal to the sample variance.**

## Counting process

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113173007803.png" alt="image-20210113173007803" style="zoom:50%;" />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4264\MA4264 Study Guide.assets\image-20210113173037034.png" alt="image-20210113173037034" style="zoom:50%;" />

## Poisson process

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

## Erlang distribution

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115165707187.png" alt="image-20210115165707187" style="zoom:50%;" />

​	<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115170755192.png" alt="image-20210115170755192"  />

<img src="C:\Users\User\Documents\AY20-21-Semester-2\MA4260\MA4260 Study Guide.assets\image-20210115170639351.png" alt="image-20210115170639351" style="zoom:50%;" />