# Gender-Prediction
Gender Prediction by Personal Preferences and Fears

This is the project for Data Science Introduction Course in George Washington University. 
- Authors: Ruyue Zhang, Phoebe Wu, Liwei Zhu, Sheng Luo
- Date: Oct. 2017 - Nov. 2017

### Data Source
This dataset is a survey done among Slovakian young people about their movie preference, music preference, interests, habits, personality traits, views on life, opinions, phobias, and demographics.
- https://www.kaggle.com/miroslavsabo/young-people-survey 
 
After checking every column of the dataset, we decided to take the gender data in demographics as our dependent variable. Based on the survey’s theme and in case that there will be too many variables, we only kept music preferences, movie preferences, interests and phobia as our independent variables.

### Research Question
How can we predict ‘gender’ by personal preferences and fears in 90% accuracy?" 

### Framework 
- R

### Analysis Methods
- Logistic Regression 
- K Nearest Neighbors 


### Introduction 
#### Research question development and relevant research on this topic?
This dataset is a survey done among Slovakian young people about their movie preference, music preference, interests, habits, personality traits, views on life, opinions, phobias, and demographics. After checking every column of the dataset, we decided to take the gender data in demographics as our dependent variable. Based on the survey's theme and in case that there will be too many variables, we only kept music preferences, movie preferences, interests and phobia as our independent variables. Therefore, the question we put forward first was "How can we predict 'gender' by personal preferences and fears". To make it more specific, we developed it into" How can we predict 'gender' by personal preferences and fears in 90% accuracy?"

This dataset was published on kaggle called Young People Survey by Miroslav Sabo. The publisher himself as a scholar published two research based on the survey. One is Gender differences in the prevalence of specific phobias. Forum Statisticum Slovacum. 2014, Vol. 10, No. 6. [Differences (gender + whether people lived in village/town) in the prevalence of phobias.].  The other is Multivariate Statistical Methods with Applications. Diss. Slovak University of Technology in Bratislava, 2014.[Clustering of variables (music preferences, movie preferences, phobias) + Clustering of people w.r.t. their interests.]. But the two research are all in Slovak.

Similar research includes: 1) Ohannessian, C. M., Lerner, R. M., Lerner, J. V., & von Eye, A. (1999). Does self-competence predict gender differences in adolescent depression and anxiety? Journal of Adolescence, 22(3), 397-411.  2) Jones, M. G., Howe, A., & Rua, M. J. (2000). Gender differences in students' experiences, interests, and attitudes toward science and scientists. Science education, 84(2), 180-192. 3)Cao, D., Chen, C., Piccirilli, M., Adjeroh, D., Bourlai, T., & Ross, A. (2011, October). Can facial metrology predict gender? In Biometrics (IJCB), 2011 International Joint Conference on (pp. 1-8). IEEE. 4)Powell, M., Schubert, R., & Gysler, M. (2001). How to predict gender-differences in choice under risk: a case for the use of formalized models (No. 01/21). Economics Working Paper Series.

#### Gathering and Preparation the data for analysis
Before the final best model, we wanted to subset the data, find the best model for every subset and significant variable which should be used in the final model. So we separated our data into music data, movie data, interests data and phobia data and combined gender data to every group thus making it a subset.

#### The selection and determination of the correct regression model 
We ran the basic logistic regression to check coefficients first. Then we used the bestglm package and view the best model. Due to the long running time of bestglm, after running it once we commented it. We picked out the variable in the best model then form a new logistic model, summarizing it to compare the change in coefficients. After we regrouped the data depending on the variable we picked out, we divided it into test and train data. We used the logistic model developed by train data to predict the test data, draw the ROC of every model and calculate the AUC to see how well our model classifies. 

When all subsets were done, we selected all the variables used in subset model to form our final dataset. Then following the same procedure above to get our final best model and its AUC value.

#### The predictions 
The prediction we can make with our model is to predict the gender based on a person's preferences and fears. 
We can also use KNN to do the prediction.

#### The reliability of the results
The AUC of our final logistic model is 0.9449957, which is a rather high value near to 1. So our model can discriminate well between gender and classify the case right 94% of chance. And the accuracy rate in the KNN is around 0.91.

#### Additional information or analysis might improve the model results or work to control limitations
Our data is around 1000 observations but after we remove the missing data it only remains 684 observations. The test dataset only has around 100 observations. The sample size of our data can be improved.   
We can also use the decision tree to do the classification for our data.
