# Water Quality Prediction Models

In this section, we attempt to predict values of ex-situ parameters -- COD and BOD, using in-situ parameters which are measured using sensors. The following figure shows the classification of machine learning techniques. Our prediction problem lies around regression.

![Figure 47: Diagram depicting various machine learning approaches](../../.gitbook/assets/image%20%2823%29.png)

The collected data was subjected to differentregression machine learning techniques such asartificial neural network-multiple layer perceptron\(ANN-MLP\), Support vector mechanism and AdaBoost. Parameters such as temperature, electrical conductivity, pH, turbidity, DO, Chlorophyll-a, CDOM, Tryptophan and nitrateare used in different combinations to predictCOD and BOD. While nitrate can be measured using a sensor as well as in lab, the values used in models here were lab-based values since only limited sensor-based nitrate values were available with us. The respective machine learning techniques were applied to the data collected across various rivers in India from April 19, 2017 to September 24, 2018. The table below shows the descriptive statistics of the data.

![Table 15: Descriptive statistics of water quality data collected across various rivers in India from April 19, 2017 to September 24, 2018](../../.gitbook/assets/image%20%2825%29.png)

**Simple linear regression**  
Regression technique allows not only to investigate the relationship between variables but also to model the relationship between variables. This enables one to make predictions about what one variable will do based on the scores of some other variables. The table belowdepicts the correlation coefficients betweenCOD, BOD and other parameters. There is a weak correlation observed between COD, BOD and conductivity, nitrate, CDOM and tryptophan; negative correlations were observed between COD, pH and DO. Similar trend was observed for BOD. Though these relations are weak, theyshow statistical significance \(since significance \(2tailed\) is &lt;0.05\).

![Table 16: Correlation between COD, BOD and other parameters](../../.gitbook/assets/image%20%2851%29.png)

**Multiple linear regression**  
Simple linear regression enables prediction of the value of one variable based on the value of a single predictor variable whereas multiple regression allows you touse multiple predictors. To predict the COD and BOD, four different combinationsof input parameters are applied. The input parameter combinations are as follows:

a. Model-01 = Temperature, pH, EC, DO and turbidity.  
b. Model-02 = Temperature, pH, EC, DO, nitrate and turbidity.  
c. Model-03 = Temperature, pH, EC, DO, turbidity, chlorophyll-a, CDOM and tryptophan.  
d. Model-04 = Temperature, pH, EC, DO, turbidity, nitrate, chlorophyll-a, CDOM and tryptophan.

Table below depicts the results of multiple regression where R$$^2$$ is the proportion of variance explained by an independent variable in a regression model, RMSE is the root mean square error representingthe difference between predicted and actual observed values and p is the level of significance. The4th combination of parameters is able to explain only 34% and 37% of the data for BOD and COD respectively. All the models show p-value is &lt;0.05 indicating that these models are statisticallysignificant. However, they cannot be used to explain the variability of the targeted parameters fully.

![Table 17: R, R^2, f and p-values resulted from multiple regression](../../.gitbook/assets/image%20%2857%29.png)

**Support Vector Machine**  
As linear models are not able to predict the targeted parameters, the data was treated withnon-linear techniques such as artificial neuralnetwork, support vector regression and AdaBoost. Support vector machine \(SVM\) is based on a technique called the kernel trick to transform the data, and based on these transformations itfinds an optimal boundary between the possibleoutputs. Simply put, it does some extremelycomplex data transformations, then figures outhow to separate the data based on the labels oroutputs as defined. It is a discriminative classifier formally defined by a separating hyperplane.

a. Basic concept: SVMs were developed by Cortes& Vapnik \(1995\) for binary classification. Theirapproach may be roughly sketched as follows:  
b. Class separation: This part looks for the optimal separating hyperplane between the two classes by maximizingthemarginbetweentheclasses.Closest points are the points lying on the boundaries and are called support vectors, and the middle of the margin is our optimal separating hyperplane.  
c. Overlapping classes: Data points on the “wrong” side of the discriminant margin are weighted down to reduce their influence.  
d. Nonlinearity: When we cannot find a linearseparator, data points are projected into a higher-dimensional space where they effectively becomelinearly separable.  
e. Problem solution: The whole task can be formulated as a quadratic optimization problem which can be solved by known techniques.  
A program able to perform all these tasks is called a Support Vector Machine. 

The figure below shows the scatter diagramsbetween measured COD, BOD and predicted COD and BOD with the SVM technique. Table below shows the calculated values of R$$^2$$ , and RMSE and p.

