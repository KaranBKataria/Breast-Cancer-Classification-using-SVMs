Performing PCA for dimensionality reduction and use the top number of Principal Components to train the SVM algorithm for classification. 

The objective of this project was to find an appropriate classifier that can accurately classify patients into 1 of 2 classes: Malignant (Cancerous) and Benign (Not Cancerous) to predict presence of breast cancer. 

The intial step was to explore the dataset for the presence of any missing or duplicated values. After quick exploration, it was evident the dataset had already been cleaned. 

The next step was to reduce the number of features required to be part of the supervised learning model. With 30 predictors/features, eliminating some feaures would significantly reduce model complexitity and computational time. There are many methods of filtering through the features for removal, such as reducing those with colinearity or eliminating those which are unrelated to the labels, but the method I chose was Principal Component Analysis (PCA). 

My incentive for selecting PCA as a dimensionality reduction technique was to allow all 30 features to be used in it's computation, determining the principal component scores which maximises variance whilst remaining completely uncorrelated with one another. After performing PCA and determining the principal components (the projects of the datapoint into to the PC scores/axis), I plotted a scree plot to determine the cumulative proportion of variance explained by each additional principal component. 

After plotting the scree plot, it was evident that we needed 7 PCs to explain more than 90% of the variation within the data. As a result, PCs 1-7 was to be included in my model for training and validation to classify the labels. 
