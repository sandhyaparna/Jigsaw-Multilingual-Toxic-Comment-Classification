* Check data languages in Train & Validation data set
* Convert train data into languages present in Validation data set as it is similar to Test data

### EDA: 
Performed only on Train data. Data Preprocessing is performed on entire data
• Word cloud of all the words in the text
• Word cloud of words in Non-Toxic comments vs Word cloud of words in Toxic comments
• For different shapes (persons)  in wordcloud. Images from kernel
• Identify language of the text using polyglot package
• Check the frequency distribution of different languages by Target variable
• World plot of different languages by their number of comments/observations i.e Freq by country on a world plot
• Continents wise plot of different languages
• Histogram of number of the words in a comment
• Within Non-English comments see their distribution separately as English ones are way more than others
• Average number of words in comments by Language and Country
• Get sentiment of the comments. Freq of comments by Negative/Positive sentiment value
• Observe which countries show max number of Negative/Positive sentiments
• Check Sentiment vs Toxicity. If Toxic comments have comparatively more Negative sentiment? 
• Get Readability of comments: Flesch reading ease, automated readability, and Dale-Chall readability
• Flesch reading ease vs Toxicity
• Freq of languages comments in Validation data
• If date of the comment is available -Number of Toxic vs Non-Toxic comments by Date



### Techniques
* Self-Training/Psuedo Labeling: Pseudo labeling is the process of adding confident predicted test data to your training data. Pseudo labeling is a 5 step process. </br>
How pseudo labeling works is best understood with QDA (Quadratic Discriminant Analysis). QDA works by using points in p-dimensional space to find hyper-ellipsoids. With more points, QDA can better estimate the center and shape of each ellipsoid (and consequently make better preditions afterward). Pseudo labeling helps all types of models because all models can be visualized as finding shapes of target=1 and target=0 in p-dimensional space. 
  1. Build a model using training data
  2. Predict labels for an unseen test dataset
  3. Add confident predicted test observations to our training data 
  4. Build a new model using combined data 
  5. Use your new model to predict the test data and submit to Kaggle. </br>
* Test Time Augmentation (TTA) is a technique where we make the prediction on not just a test example, but also some of its variants, to end up with a better final prediction. We employed this technique in some of our underlying models, and it gave us a minor boost, here is how it worked:
  1. Make a prediction on the original comment in the test dataset
  2. Make predictions on the translation of the original comment in various languages
  3. Take a weighted average of predictions on original comment and its translations
* Label creation: Train data has Toxic variable which the actual Target variable(a). But there are other variables in addition to it that similar to Toxic: severe_toxic, obscene, threat, insult, identity_hate. Create a variable that takes max value out of these additional variables(b). 
	* Create max of a & b - AnyToxic
* Train data is translated to different languages (Top 6 Non-English languages that have more number of comments) - GoogleTrans library is used to translate Train data to different languages


### Models
* RoBERTa XLM
* BERT models pre-trained on specific languages of interest 








