# Naive Bayes

**Naive Bayes** classifier is a type of algorithm used in **Supervised Learning** to help predict how new data should be classified depending on the classification of previous data.

For example, if we try to classify some fruits:

We are given 100 fruits, some of them are apples and others are bananas.
We know 3 characteristics for each fruit:

* Whether it is long
* Whether it is yellow
* Whether it is soft

This is our training set to help us determine the class of any *new* fruit.

```
Type           Long | Not Long || Soft  | Not Soft  || Yellow |Not Yellow|Total
             ___________________________________________________________________
Banana      |   20  |      0   ||  25   |     5     ||   5    |   5      |   60
Apple       |    0  |     30   ||   5   |     5     ||   0    |   0      |   40
            ____________________________________________________________________
Total       |   20  |     30   ||  30   |    10     ||   5    |   5      |  100
             ___________________________________________________________________
```

According to this test data set, we can calculate the `prior probability` of a new fruit being a banana or an apple:

`P(Banana) = 60 / 100 = 0.6`

`P(Apple) = 40 / 100 = 0.4`

We can also calculate the probability for each `evidence`:

`p(Long) = 20 / 100 = 0.2`
`p(Soft) = 30 / 100 = 0.3`
`p(Yellow) = 5 / 100 = 0.05`

Probability of `Likelihood`:

`P(Long|Banana) = 20 / 100 = 0.2`
`P(Long|Apple) = 0`

Now, let's say we are given a new fruit and we need to determine if it is either an apple or a banana. We are told that this fruit is long, yellow and soft. Is it a banana or an apple?
Even if it may seem obvious, we can run these characteristics against our fruit options to help us classify it.

Probability of it being classified as a banana:

```
P(Banana|Long, yellow and soft) =
      P(Banana|Long) * P(Banana|Yellow) * P(Banana|Soft) * P(Banana)
    ------------------------------------------------------------------
                  P(Long) * P(Yellow) * P(Soft)

    0.2 * 0.05 * 0.25 * 0.6 / 0.2 * 0.05 * 0.3

    0.0015 / 0.06

    0.025
```
 Probability of it being classified as an apple:

 ```
 P(Apple|Long, yellow and soft) = 0 // 0 apples are long so there is no reason to keep calculating because multiplying any number by 0 will still give 0.
 ```

As we can see that `0.025 > 0`, we classify this Long, yellow and soft fruit as likely to be a banana.

Naive Bayes is a very good for text classification.
