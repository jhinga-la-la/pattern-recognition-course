

# Exercise 1: Statistical Measures [Pen and Paper]

Whenever we deal with a dataset to solve a particular problem, it is helpful to first analyze the data and extract some information. In this exercise, we are going to take a look at statistical measures which are very basic tools and describe the data by a single number only. However, this does not mean that they are useless or less important than other (more complex) analysis. Every measure conveys a special meaning and must be applied with care since they are also easily misinterpreted. Here, we are using a small one-dimensional dataset

>𝑋 = {5, 4, 10, 1, 5, 25}

where we can easily calculate the results by hand. Besides the measures, we are going to work with a box-and-whisker plot which is a very important visualization technique summarizing a lot of information.

1. Let's start with an overview of the measures. For this, calculate the missing values in below table:

    Measure | Required scaling | Value of measure for 𝑋 |
    :------- | :------: | -------: |
    Mode | **Nominal** | **5**
    Arithmetic mean 𝑥 | **Interval**| **(1+4+5+5+10+25)/6 = 8.333**
    Quantile 𝑥̃<sub>0.25</sub>| **Ordinal** |**4**
    Median 𝑥̃<sub>0.5</sub>  |**Ordinal** | **5**
    Range 𝑅  | **Interval** | **25-1 = 24**
    Interquartile range 𝑄 |**Interval** |**10-4 = 6**
    Variance  s<sup>2</sup> |**Interval**| **𝑠<sup>2</sup> = 75.066 (Note: therefore s = 8.664)**
    Skewness 𝑔 |**Interval** |**0.6667 (+ve)**
    Quartile skewness 𝑔<sub>𝑄</sub> |**Ratio**| **1**
2. Figure 1 shows a box-and-whisker plot of 𝑋. We now want to analyze which information
we can retrieve from this plot. The figure is annotated with labels corresponding to a
value of a statistical measure.

	a) Name what the labels ‹, ›, fi and – shows us:
    
    **label 1 = ​𝑥​̃0.75, label 2 = Median value , label 3 = 𝑥​̃0.25 , label 6 = Inter Quartile Range**

    b) The other labels may deserve a bit of explanation. Unfortunately, it is not strictly 		defined how the whiskers (fl and ⑤) are set and what is treated as an outlier (†).
	The general idea is to show the relevant range of the data via the whiskers and all
	other data points, where the evidence is strong that they don’t really belong to the
	dataset, are considered as outliers. Toolkits and libraries usually provide a way to
	configure this behavior. However, there is a common convention for the whiskers
	which says that they are set to at most 1.5 times of the interquartile range. “most”
	because we adjust the whiskers to represent a value which is actually present in the
	dataset. Every data value which still lies outside this range is considered an outlier.
	
	i. Calculate the lower whisker: min ({𝑥 | 𝑥 ∈ 𝑋 ∧ 𝑥 ≥ ̃𝑥0.25 − 1.5 ⋅ 𝑄}) =  **4 – (1.5*6) = -5**
	
	ii. Calculate the upper whisker: max ({𝑥 | 𝑥 ∈ 𝑋 ∧ 𝑥 ≤ ̃𝑥0.75 + 1.5 ⋅ 𝑄}) = **10 + (1.5*6) = 19**
        
	c) Can you infer the sign of the skewness 𝑔 from the box-and-whisker plot? **Yes**
    
3. Compared to the skewness 𝑔, the quartile skewness 𝑔𝑄 has the advantage of being more
robust against outliers and the result is normed. Hint: use the figure on slide 56 as help
for the following questions.

	a) What is the interval [𝑎; 𝑏] to which the values 𝑔𝑄 are bounded to?

	b) For which values do we say that the distribution is left, right or not skewed at all?

	c) Which conditions must hold in the extreme cases, i.e. when do we get the values 𝑎or 𝑏 for 𝑔𝑄.

	d) Give an example of a new dataset 𝑋1 which results in minimal quartile skewness, i.e. 𝑔𝑄(𝑋1) = 𝑎.
    
    e) Give an example of a new dataset 𝑋2 which results in maximal quartile skewness, i.e. 𝑔𝑄(𝑋2) = 𝑏.

4. Look at the cartoons on this blog2 and explain the basic flaw of each mentioned statistical
measure, i.e. what are the main problems the author wants to draw your attention to?
Or, to put it differently, what do you need to keep in mind when using these measures?