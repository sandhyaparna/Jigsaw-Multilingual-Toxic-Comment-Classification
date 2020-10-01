* Check data languages in Train & Validation data set
* Convert train data into languages present in Validation data set as it is similar to Test data
* 

### Techniques
##### Psuedo Labeling
Pseudo labeling is the process of adding confident predicted test data to your training data. Pseudo labeling is a 5 step process. 
1. Build a model using training data
2. Predict labels for an unseen test dataset
3. Add confident predicted test observations to our training data 
4. Build a new model using combined data 
5. Use your new model to predict the test data and submit to Kaggle. Here is a pictorial explanation using sythetic 2D data
How pseudo labeling works is best understood with QDA (Quadratic Discriminant Analysis). QDA works by using points in p-dimensional space to find hyper-ellipsoids. With more points, QDA can better estimate the center and shape of each ellipsoid (and consequently make better preditions afterward). Pseudo labeling helps all types of models because all models can be visualized as finding shapes of target=1 and target=0 in p-dimensional space. 










