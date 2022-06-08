# Project Title

Credit-Card-Fraud-Detection-using-Machine-Learning

## Description

This project report illustrates the most appropriate performance measures to be used for fraud detection purposes. Next, the dataset will be resampled before training the model. Then, we design and assess a novel learning strategy that effectively addresses detecting credit card frauds. Three techniques are applied to the dataset, and Python language is used to get the job done. According to sensitivity, specificity, accuracy, F1 score, Precision, Recall, and MCC, technical performance is evaluated for various variables. The results were a combination of these models that has been optimized based on the MCC score.

## Getting Started

### Dataframe Implementation


* Dataset


The dataset contained transactions from a European credit card holder for two days in September 2013. Very few transactions are actually fraudulent (less than 1%). The data set is highly skewed, consisting of 492 frauds in a total of 284,807 observations. This resulted in only 0.172% fraud cases. The low number of fraudulent transactions justifies this skewed set.The dataset consists of numerical values from the 28 ‘Principal Component Analysis (PCA)’ transformed features, namely V1 to V28.

![Capture6](https://user-images.githubusercontent.com/81937480/172600440-53e10e2a-596e-4e8b-8be8-ccd343fef70d.JPG)


* Dataset Visualization

Histogram plot chart

![Histogram plot chart](https://user-images.githubusercontent.com/81937480/172600770-f5939263-7108-4044-b3b8-5e6e460259a0.png)


Actual vs SMOTE

![Actual vs SMOTE](https://user-images.githubusercontent.com/81937480/172600539-e9d87c33-2d05-4dd5-998f-4cd80fc17b80.png)


Heatmap of Correlation Matrix

![Heatmap of Correlational matrix](https://user-images.githubusercontent.com/81937480/172600605-d10aea7d-d313-45d6-9f0b-a06da41cde6d.png)



### Methodology


### Proposed Methodology


* Deep Neural Networking (DNN)

* Random Forest (RF)

* Support Vector Machine (SVM)

* XGBoost Classifier (XGB)

* Quadratic Discriminant Analysis (QDA)


### Result Analysis 

* The Weighted Majority Algorithm

For each advisor 𝑖 and question (round) 𝑡, WMA associates a weight 𝑤𝑖𝑡. With w_i^1=1,∀i=1,…,n Assume the game has 𝑇 rounds. If advisor 𝑖 makes a mistake at round 𝑡, its weight is adjusted by a multiplicative factor 1−𝜂 where 𝜂∈(0,12). That is, 𝑤𝑖𝑡+1=(1−𝜂)𝑤𝑖𝑡 if 𝑖 makes a mistake. Otherwise, 𝑤𝑖𝑡+1=𝑤𝑖𝑡. At each round 𝑡, your decision is governed by the sum of weights of advisors who think the answer is True versus that of those who think the answer should be False. Mathematically, denote the answer at round 𝑡 by 𝑦𝑡, and the advisors answers by 𝑥𝑖𝑡. These variables take the values 0 and 1 to represent True and False, respectively. we have 

![Capture5](https://user-images.githubusercontent.com/81937480/172599856-a3d57d6e-f03f-4987-ab35-2b8cc7ef29e4.JPG)


* Constrained optimization problems

We are interested in constrained optimization problems of the form:

![Capture3](https://user-images.githubusercontent.com/81937480/172599958-02dfc53d-c2fe-4b15-a68a-a9a9661d78f5.JPG)

where 𝑓∶ℝ𝑛→ℝ is called the objective, 𝑔∶ℝ𝑚→ℝ represents 𝑚 equality constraints (𝑔(𝑥)=[𝑔𝑖(𝑥)]𝑖=1𝑚) and ℎ∶ℝℓ→ℝ represents ℓ boundary constraints, c represents constant. We will assume that these constraints are given in the explicit form.

This problem can also be formulated as min𝑥∈ℱ 𝑓(𝑥), where:

![Capture 4](https://user-images.githubusercontent.com/81937480/172600014-c9e317c4-9f33-4687-8d5d-e3546d7b3050.JPG) 

is called the feasible set for (1).


* Proposed algorithm

According to The Weighted Majority Algorithm (3.4.1) and Constrained Optimization Problem (3.4.2), we derived our final algorithm based on weights of the three models that have the highest MCC scores, which are DNN, XGB, and RF 


![Capture](https://user-images.githubusercontent.com/81937480/172599298-170665a2-26a9-4c97-80ba-dc89e77a75ef.JPG)


Where 𝑦𝑖 is called prediction of the variable 𝑖, 𝑦𝑖 is rounded up to 1 or round down to 0. 𝑔 represents total weighted quality constraints, and ℎ is a matrix of upper and lower bounds of weight 𝑤. The final problem can be rewritten as follow:


![Capture1](https://user-images.githubusercontent.com/81937480/172599402-328d0d00-4411-4fcf-9514-018fa544ec68.JPG)


We have to optimize maximum 𝑚𝑐𝑐(𝑦𝑡𝑟𝑢𝑒,𝑦𝑖), equivalent to finding a minimum of −1∗𝑚𝑐𝑐(𝑦𝑡𝑟𝑢𝑒,𝑦𝑖). The feasible set ℱ={𝑖∈ℝ𝑛∣𝑤𝑑𝑛𝑛,𝑤𝑥𝑔𝑏,𝑤𝑟𝑓,𝑚𝑐𝑐(𝑦𝑡𝑟𝑢𝑒,𝑦𝑖)} is the optimal solution to the problem. The results after solving the problem with Python are as below:

![Capture](https://user-images.githubusercontent.com/81937480/172598935-72915b05-f312-4235-9baf-6188ca3822ca.JPG)

The optimized mcc score (0.97) is slightly higher than random forests’ mcc (0.96). The final machine learning model to detect fraudulent transaction will be 𝑦𝑖=⁡0.1∗𝑀𝑜𝑑𝑒𝑙𝐷𝑁𝑁(𝑖)+⁡0.18∗𝑀𝑜𝑑𝑒𝑙𝑋𝐺𝐵(𝑖)+⁡0.72∗𝑀𝑜𝑑𝑒𝑙𝑅𝐹(𝑖). The trained models for Deep Neural Network, Random Forests, and XGBoost are saved for further applications such as deploying to websites, and integrating back-end systems.




## Conclusion

We learned that the best technique for fraudulent classification does not exist, and the best for a given dataset can vary with the algorithm and accuracy measure adopted. Combining multiple strategies can be effective in providing a robust solution for this challenging task. Finally, some open issues in fraud detection that we believe are worth investigating, such as: adopting different resampling methods, optimizing non-linear weight instead of linear optimization, defining a good performance measure, and consider the cost penalty associated with each wrongful prediction.

## Final Result

![Final Result visualiyation](https://user-images.githubusercontent.com/81937480/172598522-88451bc4-729b-4d1e-a6b1-b879afec68e4.png)


## License

This project is licensed under the [OVGU-PROF] License - see the LICENSE.md file for details
