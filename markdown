# Stats 2 notes

## Discrete random variables

**Discrete random variable** A random variable for which a list of all possible values could be made

**Probability distribution** A list or table showing the probability of each value occurring

The sum of the probabilities in the probability distribution equals $1$

**Probability function** A function which provides  $P(X = x)$ for all $x$

**Cumulative distribution function** A function which provides $P(X \leq x)$ for all $x$

Mean $\mu = E(X^2) = \sum x_i p_i $ (The expectation of $X$)

Variance $\sigma ^2 = E(X^2) - E(X)^2 = \sum x_i ^2 p_i - \sum x_i p_i$

### Expectation of a function of a random variable

$$ E(g(X)) = \sum g(x_i)p_i $$

### Mean and variance of functions of a random variable

$$ E(aX) = aE(x) \quad E(X+b) = E(X) + b \quad E(aX + b) = aE(X) + b$$

$$Var(aX) = a^2Var(x) \quad Var(X+b) = Var(X) \quad Var(aX+b) = a^2Var(X)$$

## The poisson distribution

### Conditions

 - The time or position of each event is independent of previous events
 - The probability of each event occurring in a given time interval or space if fixed
 - Two events cannot occur at exactly the same time or in the same position


$$P(X=x) = \left\{
        \begin{array}{ll}
            e^{-\lambda} \frac{\lambda^x}{x!} & \quad x \in \mathbb{N}^0 \\
            0 & \quad otherwise
        \end{array}
    \right.$$

### The recurrence formula

In order to calculate the succession of values of $x$: $P(X=1), P(X=2), ...$

$$P(X= x_n) = \frac{\lambda}{x}  \times P(X = x_{n-1})$$

### Sum of independent random variables

Two or more independent Poisson distributions can be combined as follows

If $X_1  \sim P(\lambda _1), X_2 \sim P(\lambda _2), ..., X_n  \sim P(\lambda _n)$

then 

$$\sum _{k=1} ^n X_k \sim P(\sum _{k=1} ^n \lambda _k )$$

This also shows that if $X \sim P(\lambda)$

then $nX \sim P(n \lambda)$

Example

> At a checkpoint an average of $300$ cars pass per hour and the mean time between lorries is $5$ minutes. 
> Find the probability that exactly $6$ vehicles pass the checkpoint in a $1$ minute period.
>  ---
> $300$ cars per hour $\to$ $5$ cars per minute
> $1$ lorry per $5$ minutes $\to$ $0.2$ lorries per minute
>  
>  $5.2$ vehicles per minute
>  $P(X = 6) = e^{-5.2}\times \frac{5.2^6}{6!} \approx  0.1515$

### Binomial 

Questions on the poisson distribution can include the use of the binomial theorem.

Example (Following from the above example)

> What is the probability that exactly $6$ cars pass the checkpoint in at least $3$ or the next $4$ minutes?
>   ---
>  Probability of success = $0.1515$,  $n = 4$
>  $$\begin{align} P(X \geq 3) &= P(X = 3) + P(X = 4)  \\ &= {4 \choose 3}(0.1515)^3 + {4 \choose 4}(0.1515)^4 \\ &\approx 0.0123 \end{align}$$

### Mean and variance of a Poisson distribution

Mean = Variance = $\lambda$


## Continuous random variables

**Continuous random variable** A variable which can take an infinite number of possible values

$$P(X = 0) = 0 \\ P(X < t) = P(X \leq t)$$

### Probability density functions $f(x)$

  - The area under the graph of a probability density function represents the probability
  - The total area under the graph must always equal $1$

### Cumulative distribution function $F(x)$

  - Is the integral of  the probability density function $f(x)$
  - Gives the probability that the values is less than $x$. $P(X < x) = P(X \leq x)$
  - Useful when finding medians and percentiles. e.g. $F(x) = 0.5$ gives the median
 
 Example
 
> Find $F(x)$ for the following probability density function
> $$f(x) = \left\{
        \begin{array}{lll}
            \frac{x^2}{18} & \quad 0 \leq x \leq 3 \\
            \frac{1}{4}(5-x) & \quad 3 \leq x \leq 5 \\
            0 & \quad otherwise \\
        \end{array}
    \right.$$
>  ---
> The function $f(x)$ must be integrated in sections
> The first section is a quadratic. If $0 < c < 3$ then
> $$P(X < c) = \int_{0}^{c} \frac{x^2}{18}  dx =\frac{c^3}{54}  $$
> Using the above formula, $P(X < 3) = 0.5$
> The second section is linear. If $3 < c < 5$ then
> $$P(X < c) = \frac{1}{2} + \int_{3}^{c} \frac{1}{4}(5-x) dx =   \frac{1}{8}(10c - c^2 -17)$$
> $F(x)$ is then given by the piecewise function
> $$f(x) = \left\{
        \begin{array}{llll}
            0 & \quad x < 0 \\ 
            \frac{x^3}{54} & \quad 0 \leq x \leq 3 \\
            \frac{1}{8}(10x - x^2 -17) & \quad 3 \leq x \leq 5 \\
            1& \quad x \geq 5 \\
        \end{array}
    \right.$$

### Rectangular / Continuous uniform distribution

A rectangular distribution is given by

$$f(x) = \left\{
        \begin{array}{ll}
            \frac{1}{b-a} & \quad a < x < b \\
            0 & \quad otherwise
        \end{array}
    \right.$$
and

$$F(x) = \left\{
        \begin{array}{ll}
            0 & \quad x \leq a \\
            \frac{x-a}{b-a} & \quad a \leq x \leq b \\
            1 & \quad x \geq b
        \end{array}
    \right.$$

#### Mean and variance of a rectangular distribution

$$E(X) = \mu = \frac{1}{2}(a+b)$$

$$Var(X) = \sigma^2 = \frac{1}{12}(b-a)^2 $$

Given the mean and the variance of a rectangular distribution, $a$ and $b$ can be found by solving simultaneously.

## Estimation

### Mean

$$\begin{align} \overline{x} &= \frac{\sum x}{n} \\ &= \frac{\sum fx}{\sum f} \end{align}$$

### Sample variance

$$\begin{align} (\sigma _n)^2 &= \frac{(x-\overline{x})^2}{n} \\
&= \frac{x^2}{n} - \mu ^2 \\ 
&= \frac{\sum f x^2}{\sum f} - \mu ^2 \end{align}$$

### Unbiased estimator of the population variance

$$(\sigma _{n-1})^2 = \frac{n}{n-1} \times (\sigma _n)^2$$

### Confidence intervals

#### Interpretation of confidence intervals

For a $k$ percent confidence interval for the mean, across a number of different samples $k$ percent of the confidence intervals for the mean will contain the true population mean.

#### Writing confidence intervals

Confidence intervals should be written to a high degree of accuracy in the format (lower limit, upper limit)

#### Calculating confidence intervals

If the population variance is given for a normally distributed population the Z tables are used and the confidence interval is given by:

$$\overline{x} \  \pm \ Z_{\alpha} \times \sqrt{\frac{\sigma ^2}{n}}$$


If the population variance is unknown, but the sample size is greater than 30 the $Z$ tables are used due to central limit theorem. The above formula is still used, with the following assumptions:

  - The data can be regarded as a random sample
  - Central limit theorem allows the distribution to be assumed to follow a normal distribution

If the population variance is unknown, and the sample size is less than $30$, the $t$ tables are used with $\nu = n - 1$ degrees of freedom. The confidence interval is then given by:

$$\overline{x} \  \pm \ t_{\alpha} \times \sqrt{\frac{S^2}{n}}$$

Example

> $20$ bottles are selected from a production line. The volume of liquid in each is recorded as $x$ ml
> $$\sum x = 1518.9 \quad \sum (x - \overline{x})^2 = 7.2895$$
> Stating any assumptions made, construct a $95\%$ confidence interval for the mean.
>  ---
> $$n = 20 \\ mean = \frac{\sum x}{n} \\ sample\ variance = \frac{\sum (x - \overline{x})^2}{n} \\ unbiased\ estimator\ of\ population\ variance = \frac{\sum (x - \overline{x})^2}{n-1}$$
> Using  $\nu = 20 - 1 = 19$ degrees of freedom, the $95\%\ t%$ values is $2.093$
> The confidence interval is then given by
> $$75.945\ \pm \ 2.0893 \times \sqrt{\frac{0.38366}{20}} = (75.66, 76.23)$$
> The assumptions made were that 
>   - The contents of the bottles are normally distributed
>   - The sample was selected randomly

## Hypothesis testing

### Procedure

#### Step 1

State the null hypothesis and the alternate hypothesis.

$H_0:\ \mu = a$

$H_1:\ \mu \neq a$

Two tailed test

#### Step 2
 Choose the test statistic

For a known variance, or $n > 30$

$$ Z = \frac{x - \mu}{ \sqrt{\frac{\sigma ^2}{n}}}$$

For an unknown variance, and $n < 30$

$$ t = \frac{x - \mu}{ \sqrt{\frac{\sigma ^2}{n}}}$$

#### Step 3

Use tables to find the critical value

If a $t$ distribution is used, there are $n - 1$ degrees of freedom

State the critical value, or draw a graph and mark it with the critical value and the test statistic

#### Step 4

Conclude the hypothesis test

As [condition] there is / isn't significant evidence at the $\%$ level that the mean differs from a.
We therefore reject/accept $H_0$ and conclude that... [context].

### Errors

#### Type 1 error

This type of error occurs when H<sub>0</sub> is reject, and H<sub>1</sub> is accepted when H<sub>0</sub> is in fact correct.

The probability of obtaining a type 1 error is the level of significance of the test hypothesis.

#### Type 2 error

This type of error occurs when $H_0$ is accepted, when it is in fact false.

The probability of a type 2 error is not fixed, since it depends upon the extent to which the value of $\mu$ deviates from the value given in $H_0$. If the value of $\mu$ is closed to the value given in $H_0$ the probability of a type 2 error is large.

## Chi-squared goodness of fit test

 - Used for testing bias, or the independence of variables
 - The test statistic involves squares, as we are only interested in upper limit critical values
 - $H_0$ is always that the variables are independent

### Calculating 

#### Calculating expected frequencies

For a table of values, the expected frequency of each value is 

$$\frac{\sum row \times \sum column}{total}$$

If the expected frequency of a particular value is less than $5$, its row or column must be merged.

#### The test statistic

For the general case

$$\chi ^2 = \sum \frac{(O_i -  E_i)^2}{E_i}$$

For the case where the table is $2\times2$ we have only one degree of freedom, and the test statistic is

$$\chi ^2 = \sum \frac{(|O_i -  E_i| - 0.5)^2}{E_i}$$

#### The critical value

The degrees of freedom, $\nu$ , of a chi-squared contingency table is given by $n - 1$ where $n$ is the number of groups in the table.

The critical value is then found from the table or from a calculator.

Example of the comparison of two variables

> Natives of England, Africa, and China were classified by blood group
> |     | O | A | B | AB |
> | --- | --- | --- | --- | --- |
> | English | 235 | 212 | 79 | 83 |
> | African | 147 | 106 | 30 | 51 |
> | Chinese | 162 | 135 | 52 | 43 |
> 
> Is there any evidence at the $5\%$ level that there is a connection between blood group and nationality?
>  ---
>  $H_0$: There is no connection between blood group and nationality
>  $H_1$: There is a connection between blood group and nationality
>   
>   For each cell we find the expected value by multiplying the row total and column total before dividing by the table total
> | | | | | |
> | --- | --- | --- | --- | --- |
> | 24.816 | 206.65 | 73.44 | 80.74 |
> | 136.10 | 113.33 | 40.28 | 44.28 | 
> | 159.74 | 133.02 | 47.27 | 51.97 | 
> 
>  We have that $\nu = (4-1)(3-1) = 6$ degrees of freedom and then that 
>  $$\chi^2 _6 (5\%) = 12.592$$
>  From the table of expected frequencies
>  $$\sum \frac{(O_i - E_i)^2}{E_i} = 8.39$$
>   
>   As $8.39 < 12.592$ we do not reject $H_0$ at the $5\%$ level and therefore conclude that there is no connection between nationality and blood group.

 
