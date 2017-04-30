## Analysis of the problem

Steps for my analysis
1. As the data had too many variables and many columns consisted of mainly NA/DIV/0 columns so I read the files by replacing all the blanks/NAs/Nan/DIV/0! by NA
2. Next I reduced the number of columns by keeping columns which had only full rows of data and ignoring the NAs
3. I had around 60 columns now including the names/row numbers/TimeStamps
4. I reduced the number of predictors further by doing a PCA on the data excluding the Classe variable.
5. I observed around 33 of the first PCAs explained more than 98% cumulative variance in the data. So I decided to with the 33 PCAs.
6. I used Generalized Boosted Regression models and RandomForests from Caret package for prediction. 
7. But before that I partitioned the training data set into training(70%) and Validation (30%) data sets For Cross Validation.
8. I used different tuning parameters for RandomForest and GBM changing the number of trees.
9. I validated my model using the validation data set and GBM with 150 trees and interaction.depth = 3 gave the best accuracy.
10. Subsequently I used the model with the above parameters to train the entire data set.
11. I Finally applied it to test the 20 test cases and got a accuracy of 85%.
