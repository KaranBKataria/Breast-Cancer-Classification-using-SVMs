The objective of this project was to find an appropriate classifier that can accurately classify patients into 1 of 2 classes: Malignant (Cancerous) and Benign (Not Cancerous) to predict the presence of breast cancer. 

The initial step was to explore the dataset for the presence of any missing or duplicated values. After a quick exploration, it was evident the dataset had already been cleaned. 

The next step was to reduce the number of features required to be part of the supervised learning model. With 30 predictors/features, eliminating some features would significantly reduce model complexity and computational time. There are many methods of filtering through the features for removal, such as removing those with colinearity, those which are correlated or eliminating those which are unrelated to the labels. The method I selected was Principal Component Analysis (PCA). 

My incentive for selecting PCA as a dimensionality reduction technique was to allow all 30 features to be used in the computation in determining the principal component scores which maximise variance whilst remaining completely uncorrelated with one another. After performing PCA and determining the principal components (the projections of all data points onto all 30 PC scores/axis), I plotted a scree plot to determine the cumulative proportion of variance explained by each additional principal component. 

After plotting the scree plot, it was evident that we needed 7 PCs to explain more than 90% of the variation within the data. As a result, PCs 1-7 were to be included in my model for training and validation to classify the labels. 

Plotting PC1 against PC2 as well as a 3D plot of PC1 against PC2 against PC3, it was evident that the data had some degree of linear separability within it in the feature space defined by PCA. Despite the linear separation not being perfect, the data spread was sufficient enough to justify the use of a linear classification rule. In this project, we used the Support Vector Machine (SVM) algorithm. 

The justification for selecting SVMs over other linear classification rules such as the Perceptron Algorithm is due to SVMs nature of finding the 'optimal' decision boundary by maximising the margin between 2 support vectors in each of the 2 classes. The Perceptron Algorithm however would have simply found a linear boundary which leads to 100% perfect linear separability or until a specified number of weight refinements/iterations had been complete, as opposed to finding the 'optimal' boundary.
