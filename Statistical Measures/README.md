

## Exercise 1: Statistical Measures [Pen and Paper]

Whenever we deal with a dataset to solve a particular problem, it is helpful to first analyze the data and extract some information. In this exercise, we are going to take a look at statistical measures which are very basic tools and describe the data by a single number only. However, this does not mean that they are useless or less important than other (more complex) analysis. Every measure conveys a special meaning and must be applied with care since they are also easily misinterpreted. Here, we are using a small one-dimensional dataset

>𝑋 = {5, 4, 10, 1, 5, 25}

where we can easily calculate the results by hand. Besides the measures, we are going to work with a box-and-whisker plot which is a very important visualization technique summarizing a lot of information.

1. Let's start with an overview of the measures. For this, calculate the missing values in below table:

    Measure | Required scaling | Value of measure for 𝑋 |
    :------- | :------: | -------: |
    Mode | **<ins>Nominal</ins>** | **<ins>5</ins>**
    Arithmetic mean 𝑥 | **<ins>Interval</ins>**| **<ins>(1+4+5+5+10+25)/6 = 8.333</ins>**
    Quantile 𝑥̃<sub>0.25</sub>| **<ins>Ordinal</ins>** |**<ins>4</ins>**
    Median 𝑥̃<sub>0.5</sub>  |**<ins>Ordinal</ins>** | **<ins>5</ins>**
    Range 𝑅  | **<ins>Interval</ins>** | **<ins>25-1 = 24</ins>**
    Interquartile range 𝑄 |**<ins>Interval</ins>** |**<ins>10-4 = 6</ins>**
    Variance  s<sup>2</sup> |**<ins>Interval</ins>**| **<ins>𝑠<sup>2</sup> = 75.066 (Note: therefore s = 8.664)</ins>**
    Skewness 𝑔 |**<ins>Interval</ins>** |**<ins>0.6667 (+ve)</ins>**
    Quartile skewness 𝑔<sub>𝑄</sub> |**<ins>Ratio</ins>**| **<ins>1</ins>**
2. Figure 1 shows a box-and-whisker plot of 𝑋. We now want to analyze which information
we can retrieve from this plot. The figure is annotated with labels corresponding to a
value of a statistical measure.
![](../img/sm/figure1.png)
	
	a) Name what the labels 1, 2, 3 and 6 shows us:
   
      **<ins>label 1 = 𝑥̃<sub>0.75</sub>, label 2 = Median value , label 3 = 𝑥̃<sub>0.25</sub> , label 6 = Inter Quartile Range</ins>**

    b) The other labels may deserve a bit of explanation. Unfortunately, it is not strictly defined how the whiskers (4 and 5) are set and what is treated as an outlier (7). The general idea is to show the relevant range of the data via the whiskers and all other data points, where the evidence is strong that they don’t really belong to the dataset, are considered as outliers. Toolkits and libraries usually provide a way to configure this behavior. However, there is a common convention for the whiskers which says that they are set to at most 1.5 times of the interquartile range. “most” because we adjust the whiskers to represent a value which is actually present in the dataset. Every data value which still lies outside this range is considered an outlier.
	
    1. Calculate the lower whisker: min({𝑥 | 𝑥 ∈ 𝑋 ∧ 𝑥  ≥ 𝑥̃<sub>0.25</sub> − 1.5 ⋅ 𝑄}) =  **<ins>4 – (1.5*6) = -5</ins>**
	
    2. Calculate the upper whisker: max({𝑥 | 𝑥 ∈ 𝑋 ∧ 𝑥 ≤ 𝑥̃<sub>0.75</sub> + 1.5 ⋅ 𝑄}) = **<ins>10 + (1.5*6) = 19</ins>**
       
	
   c) Can you infer the sign of the skewness 𝑔 from the box-and-whisker plot? **<ins>Yes</ins>**
   
3. Compared to the skewness 𝑔, the quartile skewness 𝑔<sub>𝑄</sub> has the advantage of being more robust against outliers and the result is normed. Hint: use the figure on slide 56 as help for the following questions.

	a) What is the interval [𝑎; 𝑏] to which the values 𝑔<sub>𝑄</sub> are bounded to? **<ins>[-1, 1]</ins>**

	b) For which values do we say that the distribution is left, right or not skewed at all? **<ins>Not skewed, 𝑔<sub>𝑄</sub> = 0; Left skewed, 𝑔<sub>𝑄</sub> < 0; Right skewed, 𝑔<sub>𝑄</sub> > 0</ins>**

	c) Which conditions must hold in the extreme cases, i.e. when do we get the values 𝑎 or 𝑏 for 𝑔<sub>𝑄</sub>? **<ins>When Q1=Q2 or Q2=Q3 , 𝑔<sub>𝑄</sub>=+1 or 𝑔<sub>𝑄</sub>=-1</ins>**

	d) Give an example of a new dataset 𝑋1 which results in minimal quartile skewness, i.e. 𝑔<sub>𝑄</sub>(𝑋<sub>1</sub>) = 𝑎? **<ins>X={1,3,3,3,9,10}</ins>**
   
    e) Give an example of a new dataset 𝑋2 which results in maximal quartile skewness, i.e. 𝑔<sub>𝑄</sub>(𝑋<sub>2</sub>) = 𝑏? **<ins>X={-10,1,3,3,3,5}</ins>**

4. Look at the cartoons on this blog2 and explain the basic flaw of each mentioned statistical measure, i.e. what are the main problems the author wants to draw your attention to? Or, to put it differently, what do you need to keep in mind when using these measures?

    - The **<ins>arithmetic mean</ins>** is not the best measure to use with data sets containing a few extreme values or with more dispersed (volatile) data sets in general.
    - The **<ins>median</ins>** does not convey information about the max , min and the intermediate values. Hence , it may lead to a false impression .
    - The **<ins>mode</ins>** may be an inaccurate representation of data as it is not based on all the values(unlike the mean).
    - The **<ins>range</ins>** accounts for the difference between the max and the min values . It does not however convey the frequency of data points in the range and thus it would be a wrong representation while displaying diversity of data.
    - The **<ins>correlation coefficient</ins>** may show that two variables are strongly correlated , however it doesn’t mean that they are responsible for each other or depend on each other. Also, the correlation coefficient measures linear relationships : the result is inaccurate is the relationship is non-linear.
    - The **<ins>variance</ins>** tells us how far the dataset values are from the mean . This information should not be used to generalize as to what the actual result is . Also, extreme values affect the variance considerably </ins>