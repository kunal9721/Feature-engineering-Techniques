# Feature-engineering-Techniques
Here I have tried to summarize all the steps needed while doing Feature Engineering in Machine Learning with Examples
Feature Engineering
Types of encoding:

1. Nominal Encoding ---------   Includes normal categories like sex, state which have no order.
                                    |
                                    |---------   Can be solved by: -------- 1. One hot Encoding
                                                                                                  2. One hot Encoding with many variables
                                                                                                  3. Mean encoding

2. Ordinal Encoding -------- categories which have rank like education of PhD, Masters, BE.
                                    |
                                    |---------   Can be solved by: -------- 1. Label Encoding
                                                                                                  2. Target guided ordinal encoding
                                                                                                  

1. One hot Encoding: 
 ---  Creates new columns and Assign 1 to the matching row and column and 0 that don’t match, called as dummy variables and have to delete the last column as that two 0 0 will specify   Spain automatically.
So delete the Spain column.
Eg: you have 5 categories include only 4 in one hot encoding and it will create 4 columns. 
Disadvantages:  
If we have many no. of unique categories we can’t apply one hot encoding as it will create that many columns.
                     
State		Germany	France	Spain
Germany		1	0	0
France		0	1	0
Spain		0	0	1

                              
2. Label Encoding: 
---- We give the labels to categories as per their rank based on ascending order and giver the higher values which is most important category.

Education	
BE	2
Masters	3
PhD	4
Diploma	1

3. One hot Encoding with multiple categories:
--- We can see which are most repeating categories and take top 10 (or as many we want) categories and apply one hot encoding on those 10 categories mean on 9 categories.

4 .Target guided ordinal encoding:
--- We will find the mean of specific category from the output feature.
So the classification is the mean of feature.(how many times A occurs and find the mean)
Mean of output for A
Now assign the rank to the classification.

Feature	o/p	Classification	Rank
A	1	0.5	3
B	0	0.6	4 (max mean   so highest rank)
C	1	0.4	2
D	1	0.2	1
B	1	0.6	4
A	0	0.5	3
D	1	0.2	1


5. Mean Encoding: 
--- So here it’s same as above but the feature will be not converted into categories, the mean value will replace those features.
Eg: Like if we have 1000 unique pin codes we can’t convert it into 999 columns we will just replace them with nominal values (mean) and they will be replaced by integers.
Based on the output column we will calculate mean of each category (pin code) and replace that pin code with its mean.















Feature Scaling:

Example: 
Features like height and weight and I want to predict BMI.
Values have 2 things magnitude and units
Height in cm
Weight in kg 
Let’s take same magnitude and plot on graph the distance will be huge so scale down variables.
And there for scaling is imp. Scaling is done on specific column only. Algo run fast than.

Algorithms req. scaling: where there is Euclidian distance…..
      Linear regression
      K-means
      KNN 

No use of feature scaling:
     Decision tree
     Random forest
     Xgboost

Handle Missing Values in Categorical Features:

1. Delete the rows.   
Try not deleting the record

2. Replace the value with most frequent value.  
But lead to imbalanced data set.

3. Apply classifier algo to predict the category.
 Make other feature as independent and make the missing category feature as                             dependent and train the data set is filled value rows and test data set become w                         which u have to predict.

4. Apply unsupervised learning
Clustering techniques: Create cluster as needed and see which group the missing record comes in

