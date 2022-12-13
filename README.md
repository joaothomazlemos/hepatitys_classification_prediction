# hepatitys prediction
Predicted results for hepatitys based on 18 correlated features,  150 samples.

Hepatitis is inflammation of the liver. It can be caused by viruses or by the use of some medicines, alcohol and other drugs,
as well as by autoimmune, metabolic and genetic diseases. In some cases, they are silent diseases that do not always show symptoms.

Viral hepatitis are inflammations caused by viruses that are classified by letters of the alphabet in A, B, C, D (Delta) and E.
In Brazil, more than 70% (23,070) of deaths due to viral hepatitis are due to Hepatitis C, followed by Hepatitis B (21.8%) and A (1.7%). 
The country registered 40,198 new cases of viral hepatitis in 2017.

# Methods
First,  separated 90% of data for training using that was later used in crossvalidation. I explored the dataset to treat missing our unkown values, outliers, skewness. I also did setup the coluns into the right datatypes, which are categoricals and numericals. I also treated the testset in the same separated way, to avoid dataleak.
Then, I used gridsearch on 5 popular classification models (logistic regression, SVM, gaussianGB, random forest and XGBoost), to get the best parameters for each.
Finally, I applied the model with the best accuracy metric given the best parameters, against the unseen testset of 13 samples.

# Results and analisys

![image](https://user-images.githubusercontent.com/62029505/207414402-30eda9be-2758-4e76-83eb-00960c36c191.png)

![image](https://user-images.githubusercontent.com/62029505/207414633-5c1117f8-14a5-4261-85d3-e73b62599469.png)

As we can see, the precision (77%) was a bit lower than our traning precision (85%). Thats clearly because of our small test sample.
We could say that this model performs well if we consider that  when we see in the probabilities table that the model makes a mistake, on the 3 rows of 13,
its always a close call, and when it predicts correctly, it always is certain of the decision with +90% of certainty.
With that, I conclude that with a little more of data as the total is only 150 without treatment, and maybe treating the outliers that we have pointed out early,
we could make this model even more reliable.



