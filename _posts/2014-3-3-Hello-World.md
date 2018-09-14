---
layout: post
title: My First Blog Post
---

# Introduction to Possion Distribution

Poisson distribution is one of the most common discrete probability distribution. It was published by French mathematician SimÃ©on Denis Poisson, and named after him.  

If we tried to use one sentence to describe Poisson distribution in a general way, it will be âhow many times a certain event can happen in a given timeâ. Sounds easy, right? Let us take a look at follow real life case:

* 2 phone calls are made to customer service per minute on average
* 40 bags of rice are sold in a supermarket every day on average

Knowing this, we'd like to make some decicision, like how many representatives we should hire or how many bags of rice we should prepared. Using Poisson distribution, we can know:

* The possibility that 2 phone calls will happen next minutes
* The possibility that 40 bags will be sold tomorrow




Letâ s take a look at its definition: 
Given a discrete random variable X to be integer greater and equal to 0,  the possibility of X happened k times in unit time is:
æå¥å¬åŒ
e isïŒ lanmuda is the expectation and variance of X,(yes, the expectation equals to the variance). You must have noticed that X has to be integer which makes And Iâll try to use an example help you understand it in an easy way.
Papa Beard is an international chain of cream puff store.  Among 250 stores Japan, every store manager will think of a question everyday: How many puffs should be made today? Knowing this, they can make enough puff and avoid wasting supplies. The store manager of Ikebukuro kept tracking sales number(during open hours which is 10 am to 8 pm)  and here is how many puffs were sold last week (to make the case easier, we use simple data, the real number would be like 100 times more):
 Weekdays. Puff sold
Monday.      3
Tuesday       7
Wed             4
Thurs            6
Fri                   5
The mean is 3+7+4+6+5/5 = 5. So should they prepare 5 every day? Seems reasonable. However, for Tuesday and Thursday, the puff will be short.  The manage needs to think further. He set open hours â 10 hours â as T, then, put Mondayâs number 3 on T which divide T into 4 equal part. Each part became either they sold a puff or they donât. like a coin flip question:
T  Sold or not
1/4T  Sold
2/4T Sold
3/4T Sold
T       not
(I know what you are thinking:  How can he make sure the 4 part is same? What if he sold 2 in the first 1/4T? Youâre right, he canât. But he can separate T into n part, for each part T/n is the same. In this way, each T/n period is still leads to a coin flip question.) So, in this form, letâs calculate the possibility they sold 3 puffs in T, it is like flip a coin 4 times and get 3 coins, only we don't know if the coin was faired. And the possibility could be expressed using Binomial distribution
(43)p3-p1: 
Hence, the possibility of k puffs is sold in T could be expressed as limit(nk)pk1-pn-k. And what is pâs value? 
Since the question has expressed as Binomial distribution. We can use:
Ex=np=u p=u/p
So 

This is the pmf of Poisson distribution. In this case mean is u =5, so P(X=k)5k/k!e-5.
Letâs draw the pmf, we can have,
åŸç
P(X<=8) similar to 0.93.
Which means, if they make 8 puffs per day, it will cover 93% of the days.
So what can we learn form this case? If you want to be a storage, you have to learn Poisson distribution first!
Poisson distribution is used to describe real life problem. Let me show you some more general cases:




Knowing these possibilities can help us making decisions, if we want to simulate or model real life problem, Poisson distribution would be our best tool.
