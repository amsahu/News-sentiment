# News-sentiment
News sentiment prediction

### Task
Design and develop the solution to predict sentiments for headline and title of news.

### Process followed

![image](https://user-images.githubusercontent.com/60923910/132124080-a6df5bc9-cdfd-434e-b07e-016b9dc346d4.png)

### Dataset
* Contains news title, headline and their respective sentiments.
* Train data shape (row, column): (55932, 11)
* Test data shape (row, column): (37288, 9)
* Important columns: “Title”, “Headline”, “SentimentTitle”, “SentimentHeadline”

### EDA

* Histogram of “SentimentTitle”

![image](https://user-images.githubusercontent.com/60923910/132124212-69c564f0-ca27-47d0-9e08-ae805056fd41.png)

* Histogram of “SentimentHeadline"

![image](https://user-images.githubusercontent.com/60923910/132124220-9c4fcb38-c89b-4c56-bd51-bc9ed40d6cc2.png)

* Histogram of length of sentence for “Title”

![image](https://user-images.githubusercontent.com/60923910/132124231-33bc11db-3336-45cc-8ac0-8c7e64027f20.png)

* Max token length for “Title”: 24
* Min token length for “Title”: 1

* Histogram of length of sentence for “Headline”

![image](https://user-images.githubusercontent.com/60923910/132124273-a8b6a867-ab27-4899-ad9e-95e16f9cae10.png)

* Max token length for “Headline”: 80
* Min token length for “Headline”: 0

### Approach description

* Solved the problem with neural networks.
* Solved the problem as a regression problem with considering output inside the boundary of -1 to 1.

### Data Preparation / Pre-processing

* Combined all data to create a single sentiment model.
* Removed data containing NULL values.
* Removed hyperlinks/ websites using regex.
* Removed numbers and punctuations.
* Used spacy to lemmatize the words.
* Removed Pronouns.
* Created one-hot encodings for the corpus.
* After cleaning, found that maximum sentence length is 87, so taken 90 as maximum length.
* Added padding to all the data which are less than 90 words.
* Created training and validation sets.

### Models used

* LSTM: Long Short Term Memory networks are a special kind of RNN, capable of learning long-term dependencies.
* BiLSTM: It contains LSTM only but with bidirectional flow, which helps to store information from both the directions.

### Model metrics summary

<img src="https://user-images.githubusercontent.com/60923910/132124397-3a10c4f5-9499-4e17-89a4-c3683155ad35.png" width=700>

### Metrics plot

![image](https://user-images.githubusercontent.com/60923910/132124404-3510de4b-3606-4517-ac65-d1a37a706a3a.png)

![image](https://user-images.githubusercontent.com/60923910/132124406-dd5ffd36-26cd-4dbc-964e-c6a08679d863.png)

### Training plots for losses

![image](https://user-images.githubusercontent.com/60923910/132124428-2931f02a-e9aa-43a5-8dee-b7f629661137.png)

### Final model architecture

![image](https://user-images.githubusercontent.com/60923910/132124444-7291c935-c359-4524-bc72-73cc00d62d82.png)

<br />

![image](https://user-images.githubusercontent.com/60923910/132124459-1b76409e-6dec-41ca-bf4a-a31df3aca9fa.png)

### Achievements

* Achieved a sentiment prediction model to predict news title and headline sentiments.
* Achieved comparison of various combinations of parameters for two different models.

