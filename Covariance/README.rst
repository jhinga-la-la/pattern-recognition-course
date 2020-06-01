=========
README.md
=========

.. _header-n2:

Exercise 1: Covariance [Pen and Paper]
======================================

| The covariance is an important measure when we want to know how two
  features influence
| each other linearly. It takes the feature variables 𝑋 and 𝑌 as input
  and returns a single value

.. math:: s_{XY} = \frac1{n-1} \sum_{i=1}^{n}{(x_i - \bar x)(y_i - \bar y)}

| describing the linear relationship between 𝑋 and 𝑌. That is, 𝑠𝑋 𝑌
  describes a tendency of the
| co-occurrence of both features. In this exercise, we want to analyse
  this tendency and see how
| it behaves and changes

1. Let's start with an overview of the measures. For this, calculate the
   missing values in below table:

   +--------------------+------------------+--------------------+---+
   | Measure            | Required scaling | Value of measure   |   |
   |                    |                  | for 𝑋              |   |
   +====================+==================+====================+===+
   | Mode               | **Nominal**      | **5**              |   |
   +--------------------+------------------+--------------------+---+
   | Arithmetic mean 𝑥  | **Interval**     | *                  |   |
   |                    |                  | *(1+4+5+5+10+25)/6 |   |
   |                    |                  | = 8.333**          |   |
   +--------------------+------------------+--------------------+---+
   | Quantile 𝑥̃0.25     | **Ordinal**      | **4**              |   |
   +--------------------+------------------+--------------------+---+
   | Median 𝑥̃0.5        | **Ordinal**      | **5**              |   |
   +--------------------+------------------+--------------------+---+
   | Range 𝑅            | **Interval**     | **25-1 = 24**      |   |
   +--------------------+------------------+--------------------+---+
   | Interquartile      | **Interval**     | **10-4 = 6**       |   |
   | range 𝑄            |                  |                    |   |
   +--------------------+------------------+--------------------+---+
   | Variance s2        | **Interval**     | **𝑠2 = 75.066      |   |
   |                    |                  | (Note: therefore s |   |
   |                    |                  | = 8.664)**         |   |
   +--------------------+------------------+--------------------+---+
   | Skewness 𝑔         | **Interval**     | **0.6667 (+ve)**   |   |
   +--------------------+------------------+--------------------+---+
   | Quartile skewness  | **Ratio**        | **1**              |   |
   | 𝑔𝑄                 |                  |                    |   |
   +--------------------+------------------+--------------------+---+

2. | Figure 1 shows a box-and-whisker plot of 𝑋. We now want to analyze
     which information
   | we can retrieve from this plot. The figure is annotated with labels
     corresponding to a
   | value of a statistical measure.
   | |image0|

   a) Name what the labels 1, 2, 3 and 6 shows us:

   **label 1 = 𝑥̃0.75, label 2 = Median value , label 3 = 𝑥̃0.25 , label 6
   = Inter Quartile Range**

   b) The other labels may deserve a bit of explanation. Unfortunately,
   it is not strictly defined how the whiskers (4 and 5) are set and
   what is treated as an outlier (7). The general idea is to show the
   relevant range of the data via the whiskers and all other data
   points, where the evidence is strong that they don’t really belong to
   the dataset, are considered as outliers. Toolkits and libraries
   usually provide a way to configure this behavior. However, there is a
   common convention for the whiskers which says that they are set to at
   most 1.5 times of the interquartile range. “most” because we adjust
   the whiskers to represent a value which is actually present in the
   dataset. Every data value which still lies outside this range is
   considered an outlier.

   1. Calculate the lower whisker: min({𝑥 \| 𝑥 ∈ 𝑋 ∧ 𝑥 ≥ 𝑥̃0.25 − 1.5 ⋅
      𝑄}) = **4 – (1.5*6) = -5**

   2. Calculate the upper whisker: max({𝑥 \| 𝑥 ∈ 𝑋 ∧ 𝑥 ≤ 𝑥̃0.75 + 1.5 ⋅
      𝑄}) = **10 + (1.5*6) = 19**

   c) Can you infer the sign of the skewness 𝑔 from the box-and-whisker
   plot? **Yes**

3. Compared to the skewness 𝑔, the quartile skewness 𝑔𝑄 has the
   advantage of being more robust against outliers and the result is
   normed. Hint: use the figure on slide 56 as help for the following
   questions.

   a) What is the interval [𝑎; 𝑏] to which the values 𝑔𝑄 are bounded to?
   **[-1, 1]**

   b) For which values do we say that the distribution is left, right or
   not skewed at all? **Not skewed, 𝑔𝑄 = 0; Left skewed, 𝑔𝑄 < 0; Right
   skewed, 𝑔𝑄 > 0**

   c) Which conditions must hold in the extreme cases, i.e. when do we
   get the values 𝑎 or 𝑏 for 𝑔𝑄? **When Q1=Q2 or Q2=Q3 , 𝑔𝑄=+1 or
   𝑔𝑄=-1**

   d) Give an example of a new dataset 𝑋1 which results in minimal
   quartile skewness, i.e. 𝑔𝑄(𝑋1) = 𝑎? **X={1,3,3,3,9,10}**

   e) Give an example of a new dataset 𝑋2 which results in maximal
   quartile skewness, i.e. 𝑔𝑄(𝑋2) = 𝑏? **X={-10,1,3,3,3,5}**

4. Look at the cartoons on this blog2 and explain the basic flaw of each
   mentioned statistical measure, i.e. what are the main problems the
   author wants to draw your attention to? Or, to put it differently,
   what do you need to keep in mind when using these measures?

   -  The **arithmetic mean** is not the best measure to use with data
      sets containing a few extreme values or with more dispersed
      (volatile) data sets in general.

   -  The **median** does not convey information about the max , min and
      the intermediate values. Hence , it may lead to a false impression
      .

   -  The **mode** may be an inaccurate representation of data as it is
      not based on all the values(unlike the mean).

   -  The **range** accounts for the difference between the max and the
      min values . It does not however convey the frequency of data
      points in the range and thus it would be a wrong representation
      while displaying diversity of data.

   -  The **correlation coefficient** may show that two variables are
      strongly correlated , however it doesn’t mean that they are
      responsible for each other or depend on each other. Also, the
      correlation coefficient measures linear relationships : the result
      is inaccurate is the relationship is non-linear.

   -  The **variance** tells us how far the dataset values are from the
      mean . This information should not be used to generalize as to
      what the actual result is . Also, extreme values affect the
      variance considerably

.. |image0| image:: C:\Users\kalim\OneDrive\Documents\ssd-demo\pattern-recognition-course\img\figure1.png
