# Auto_Insurance Fraud Detection_Analysis

### Dataset info:

![1](https://user-images.githubusercontent.com/92646311/201808224-785e00e4-eaa5-4d03-b633-7af74c7440c1.png)


-Marital_status: Whether the applicant is married ("Yes") or not ("No")

-Dependents: Number of dependents of the applicant

-Is_graduate: Whether the applicant is a graduate ("Yes") or not ("No")

-Income: Annual Income of the applicant (in USD)

-Loan_amount: Loan amount (in USD) for which the application was submitted

-Credit_score: Whether the applicant’s credit score is good ("Satisfactory") or not ("Not Satisfactory")

-Approval_status: Whether the loan application was approved ("1") or not ("0")

-Age: The applicant's age in years

-Sex: Whether the applicant is a male ("M") or a female ("F")

-Purpose: Purpose of applying for the loan

## EDA Analysis

**jmv package in R to get some frequencies:**

We will use the descriptives() function. This will provide nice output. We will use the parameter freq=TRUE to get frequencies for factors.

![image](https://user-images.githubusercontent.com/92646311/201808599-0c3cff45-1f6d-4163-ab4c-4a4057f3f5ea.png)
![image](https://user-images.githubusercontent.com/92646311/201808770-49ef0a93-8026-4ebd-b6c5-c8a4029df7e1.png)

"" Summary Stats - skim()""

skim is another function that produces summary statistics. It will also produce a small histogram to show the distribution of your data (for numeric/integers).

![image](https://user-images.githubusercontent.com/92646311/201809636-44cad497-6ae3-4dab-bda8-be9eb59e4770.png)

![image](https://user-images.githubusercontent.com/92646311/201809688-123cab53-db48-4023-879e-88d42f79164b.png)

![image](https://user-images.githubusercontent.com/92646311/201809718-ae49b875-7e25-434a-bd01-441eb91ccf22.png)

# Data Viz:

![image](https://user-images.githubusercontent.com/92646311/201809811-382ad16a-cde9-4b40-b54c-0bece7682bea.png)

![image](https://user-images.githubusercontent.com/92646311/201809972-a35ec069-5382-477c-a68d-629c67706ec6.png)
![image](https://user-images.githubusercontent.com/92646311/201809998-73b9cd7d-0ef4-40ca-bc72-a3f91ee2a323.png)

##  Histogram
A histogram is similar to a bar plot, except that instead of summarizing categorical data, it categorizes a continuous variable like clay content into non-overlappying intervals for the sake of display. The number of intervals can be specified by the user, or can be automatically determined using an algorithm, such as nclass.Sturges(). Since histograms are dependent on the number of bins, for small datasets they’re not the best method of determining the shape of a distribution.

![image](https://user-images.githubusercontent.com/92646311/201810116-334bcf2f-7819-41c8-b9c7-b2df32f79bbb.png)

##  Box plots
Box plots are a graphical representation of the five number summary, depicting quartiles (i.e. the 25%, 50%, and 75% quantiles), minimum, maximum and outliers (if present). Boxplots convey the shape of the data distribution, the presence of extreme values, and the ability to compare with other variables using the same scale, providing an excellent tool for screening data, determining thresholds for variables and developing working hypotheses.

The parts of the boxplot are shown in the figure below. The “box” of the boxplot is defined as the 1st quartile, (Q1 in the figure) and the 3rd quartile, (Q3 in the figure). The median, or 2nd quartile, is the dark line in the box. The whiskers (typically) show data that is 1.5 * IQR above and below the 3rd and 1st quartile. Any data point that is beyond a whisker is considered an outlier.

That is not to say the outlier points are in error, just that they are extreme compared to the rest of the dataset. However, you may want to evaluate these points to ensure that they are correct.

![image](https://user-images.githubusercontent.com/92646311/201810218-59d40f93-bf7c-4920-b2ea-33f06bf0af28.png)

![image](https://user-images.githubusercontent.com/92646311/201810243-66787381-af35-4bea-842f-76b5aa7d3082.png)

##  Scatter plot 
Plotting points of one ratio or interval variable against another is a scatter plot. Plots can be produced for a single or multiple pairs of variables. Many independent variables are often under consideration in soil survey work. This is especially common when GIS is used, which offers the potential to correlate soil attributes with a large variety of raster datasets.

The purpose of a scatterplot is to see how one variable relates to another. With modeling in general the goal is parsimony (i.e., simple). The goal is to determine the fewest number of variables required to explain or describe a relationship. If two variables explain the same thing, i.e., they are highly correlated, only one variable is needed. The scatterplot provides a perfect visual reference for this.

Create a basic scatter plot using the loafercreek dataset.

![image](https://user-images.githubusercontent.com/92646311/201810310-2090d7d1-195c-458e-8d55-82cae2669416.png)

## library(GGally)
The function below produces a scatterplot matrix for all the numeric variables in the dataset. This is a good command to use for determining rough linear correlations for continuous variables.

![image](https://user-images.githubusercontent.com/92646311/201810577-89e3607a-2ee5-46cf-b189-4e5e846c5cca.png)

![image](https://user-images.githubusercontent.com/92646311/201810602-26cf96d0-bc9c-4b81-97f1-75a31fa345b7.png)

![image](https://user-images.githubusercontent.com/92646311/201810688-fd4276f2-8fd5-4234-9d73-1239f48e7f00.png)

![image](https://user-images.githubusercontent.com/92646311/201810728-a480c55e-266d-4133-8a68-90a4a41784d1.png)

## Quantile comparison plots (QQplot)

A QQ plot is a plot of the actual data values against a normal distribution (which has a mean of 0 and standard deviation of 1).

![image](https://user-images.githubusercontent.com/92646311/201810879-e0cdd044-9328-4692-a082-2b75806fd647.png)

# Missing Values:

Let’s quickly view what this new missing object looks like using glimpse(). This will print the columns and first row vertically in the console. Because there are 67 columns, we will just look at the first 10.

![image](https://user-images.githubusercontent.com/92646311/201811324-745e4e90-f0ff-4703-afc6-16079c764d3d.png)

To begin with, I'll first check if this data has missing values. This can be done by using:

![image](https://user-images.githubusercontent.com/92646311/201811395-28237184-85f2-4be4-ad02-9595aa2a9997.png)

If there are missing values, we can check these values by using clSums()

![image](https://user-images.githubusercontent.com/92646311/201811469-0b6d7165-4a50-45f9-8a47-ee641c728f3b.png)

# Imputation with mean / median / mode

Replacing the missing values with the mean / median / mode is a crude way of treating missing values. Depending on the context, like if the variation is low or if the variable has low levermonths_as_customer over the response, such a rough approximation is acceptable and could possibly give satisfactory results.

![image](https://user-images.githubusercontent.com/92646311/201811588-7d818087-5bbd-4fc5-94f2-719b69b008e2.png)

# Dealing With Categorical Data

Categorical variables represent types of data which may be divided into groups. Examples of categorical variables are race, sex, age group, educational level etc.

![image](https://user-images.githubusercontent.com/92646311/201812049-65c7ab1d-3baf-44f1-abb4-1aab9c58f57a.png)

# Classification Algorithms:

## Encoding the target feature as factor

![image](https://user-images.githubusercontent.com/92646311/201812801-8a255670-7187-4e5b-ab80-d75bdec19f62.png)

###  From caTools packages we will be using sample.split function

![R_Python_ML_Libraries](https://user-images.githubusercontent.com/92646311/201812996-487e3998-df35-48b2-aa2b-cc629ee85cb5.png)


Often when we perform classification tasks using any ML model namely logistic regression, SVM, neural networks etc. it is very useful to determine how well the ML model performs agains at dummy classifier. A dummy classifier uses some simple computation like frequency of majority class, instead of fitting and ML model. It is essential that our ML model does much better that the dummy classifier. This problem is even more important in imbalanced classes where we have only about 10% of +ve samples. If any ML model we create has a accuracy of about 0.90 then it is evident that our classifier is not doing any better than a dummy classsfier which can just take a majority count of this imbalanced class and also come up with 0.90. We need to be able to do better than that.


![image](https://user-images.githubusercontent.com/92646311/201812463-70d4f540-2c6d-47b8-8012-bd440b8bbe5e.png)





