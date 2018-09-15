---
layout: post
title: My First Blog Post
---

# Introduction to Possion Distribution

Poisson distribution is one of the most common discrete probability distribution. It was published by French mathematician SimÃ©on Denis Poisson, and named after him.  

If we tried to use one sentence to describe Poisson distribution in a general way, it will be "how many times a certain event can happen in a given time". Sounds easy, right? Let us take a look at follow real life case:

* 2 phone calls are made to customer service per minute on average
* 40 bags of rice are sold in a supermarket every day on average

Knowing this, we'd like to make some decicision, like how many representatives we should hire or how many bags of rice we should prepared. Using Poisson distribution, we can know:

* The possibility that 2 phone calls will happen next minutes
* The possibility that 40 bags will be sold tomorrow

Let's take a look at its definition: 
Given a discrete random variable X to be integer $\ge0$,  the possibility of X happened n times in time t is:

< img src="https://latex.codecogs.com/gif.latex?P(N(t)=n) = \frac{(\lambda t)^n e^{-\lambda t}}{n!} " />

\lambda is the expectation and variance of X,(yes, the expectation equals to the variance). And I'll try to use another example to show you how Poisson distribution can contribute to the real life situation.

Papa Beard is an international chain of cream puff store.  Among 250 stores Japan, every store manager will think of a question everyday: How many puffs should be made today? Knowing this, they can make enough puff and avoid wasting supplies. The store manager of Ikebukuro kept tracking sales number(during open hours which is 10 am to 8 pm)  and here is how many puffs were sold last week (to make the case easier, we use simple data, the real number would be like 100 times more):

| Weekdays | # of Puffs sold |
|:----------:|:-----------------:|
| Monday   |       3         |
| Tuesday  |       7         |
| Wednesday|       4         |
| Thursday |       6         |
| Friday   |       5         |


The mean is 

$$\overline{x}=\frac {3+7+4+6+5}{5}$$

So should they prepare 5 every day? Seems reasonable. However, for Tuesday and Thursday, the puff will be short.  The manage needs to think further. He set open hours 10 hours as T, then, put Monday's number 3 on T which divide T into 4 equal part. Each part became either they sold a puff or they don't, like a coin flip question:

|   T   | Puff sold or not |
|:-------:|:------------------:|
| $\frac{1}{4}$T  |      sold        |
| $\frac{2}{4}$T  |      sold        |
| $\frac{3}{4}$T  |       not        |
|   T   |      sold        |

(I know what you are thinking: What if he sold 2 in the first 1/4T? The manager only do this to make the sample simpler. If we required more precisely, he can devide T into n equal parts. In this way, each $\frac{T}{n}$ period is still leads to a coin flip question.) 

So, in this form, let's calculate the possibility that they sold 3 puffs in T, it's like flip a coin 4 times and get 3 heads, only we don't know if the coin was faired. And the possibility could be expressed using Binomial distribution:

$${n\choose 3}p^3(1-p)$$

Hence, the possibility of k puffs is sold in T could be expressed as:

$$\lim_{n\to \infty}{n\choose k} p^k (1-p)^k$$ 

The only question remains is: What is p's value? 

Since the question has already expressed as Binomial distribution. We can use:

$$E(x)=np=\mu \rightarrow  p=\frac{\mu}{n}$$

Hence, we can calculate the limit:

$$\lim_{n\to \infty}{n\choose k} p^k (1-p)^k= \lim_{n\to \infty}{n\choose k} (\frac{\mu}{n})^k (1-{\frac{\mu}{n}})^k=1$$

Let's use $\lambda$ instead of $\mu$:

$$P(X=k) = \frac{\lambda^k}{k!} e^{-\lambda}$$

We did know the mean is 5:

$$\overline{x}\approx\mu=5 \rightarrow P(X=k)=\frac{5^k}{k!}e^{-5}$$

So the manager calculate the $P(X\le k)$ and found out $P(X\le 8)\approx0.93$. Which means, if they make 8 puffs per day, it will cover 93% of the weekdays. In this way, they won't be short for 93% of the open days and avoid waste.

So what can we learn form this case? If you want to be a storage, you have to learn Poisson distribution first!

Joking aside, Poisson distribution is a handy tool describe real life problem. I'm sure, we will see it a lot in the future.


Citation:
1. https://en.wikipedia.org/wiki/Poisson_distribution

2. https://wiki.mbalib.com/wiki/%E6%B3%8A%E6%9D%BE%E5%88%86%E5%B8%83

3. https://zhuanlan.zhihu.com/p/39287095
