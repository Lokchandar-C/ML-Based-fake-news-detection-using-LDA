# ML-based-fake-news-detection-using-LDA

*****************************************************************************************************************
IN PREPROCESSING
{
Preprocessing Text Data
This code uses the gensim library to preprocess text data. The function preprocess_data() preprocesses a list of input texts using the preprocess_string() function from gensim.parsing.preprocessing. The resulting preprocessed texts are then printed to the console.

Usage
To use this code, follow these steps:

Install gensim library using pip install gensim.
Prepare a text file containing the input texts you want to preprocess.
Update the file_path variable in the code to point to the location of your input file.
Run the code.
The preprocessed texts will be printed to the console.

Notes
This code assumes that your input text file has one text per line.
The preprocess_string() function performs a number of preprocessing steps, such as converting all characters to lowercase, removing stopwords, and removing punctuation. You can modify this function to suit your specific preprocessing needs.
This code is a simple example of text preprocessing using gensim. Depending on your use case, you may need to perform additional preprocessing steps or use a different library.
Due to last minute failure the webscaping part was droped and a sample data named newss in same folder is used to check the precess flow
}

*****************************************************************************************************************
the news was saved as"newss" adn the preprocessed file is saved as "newsspreprocessed"


*****************************************************************************************************************
Model Building

The code will perform the following steps:

Load the preprocessed data from the specified file.
Vectorize the preprocessed text using a bag-of-words model.
Train a LSA model with 10 topics and a random seed of 42.
Train a LDA model with 10 topics and a random seed of 42.
The resulting topic models will be saved as lsa_model and lda_model objects, which you can use to infer topics for new text data.

Notes
This code assumes that your preprocessed text file has one preprocessed text per line.
The number of topics for the LSA and LDA models can be modified by changing the n_components parameter.
The LSA model is a type of matrix factorization method that extracts underlying topics from a document-term matrix. The LDA model is a generative probabilistic model that represents documents as probability distributions over topics and words as probability distributions over topics.
Topic modeling can be a useful technique for exploring the latent topics within a corpus of text. However, the quality of the resulting topics can depend on the quality of the input data and the parameter settings for the topic models.

*****************************************************************************************************************

Model implemantaion 
Evaluating LDA model performance on a test set
This code evaluates the performance of an LDA topic model on a test set using various evaluation metrics.

Usage
To use this code, follow these steps:

Load your preprocessed data and labels into memory.
Split your labels into training and test sets.
Define a range of topic numbers and random states to try.
Train an LDA model with different numbers of topics and random states on the training set.
For each model, evaluate its performance on the test set using the following metrics:
Accuracy: the fraction of correct predictions.
Precision: the fraction of true positives among all predicted positives.
Recall: the fraction of true positives among all actual positives.
The evaluation metrics will be printed to the console for each model.

*****************************************************************************************************************
AS A LDA APPROACH THE PREPROCESSED DATA WAS MODELED AS TOPIC MODELING

Load your preprocessed data into memory.
Modify the num_topics variable to specify the desired number of topics for the LDA model.
Train an LDA model on the data using the LatentDirichletAllocation class.
Save the trained LDA model to disk using the joblib module.
Print the top words associated with each topic to the console.
Notes
This code assumes that your preprocessed data is already loaded into memory.
The stop_words parameter in CountVectorizer can be used to exclude common English stop words from the vocabulary.
The n_components parameter in LatentDirichletAllocation specifies the number of topics to be identified in the data.
The random_state parameter in LatentDirichletAllocation is used to ensure that the results are reproducible.
The joblib module is used to save the trained LDA model to disk for later use.
The top words associated with each topic are printed to the console, and can be used to gain insight into the structure and content of the data.

THE OUTPUT OF TOPIC MODELLING WAS ALSO APPLOADED IN THE FILE
*****************************************************************************************************************

Finalllly fact checking 

The code loads preprocessed news data from a file and uses CountVectorizer and LatentDirichletAllocation to identify topics in the data. It then saves the trained LDA model and CountVectorizer to file. The code loads the saved model and vectorizer, preprocesses new text data, vectorizes it, and identifies the most likely topic. It also loads a fact-checking dataset, preprocesses and vectorizes it, identifies the most similar fact, and prints its label (real or fake). The fact-checking dataset is assumed to be a collection of real and fake news articles. The most similar fact is determined by computing the cosine similarity between the topic distribution of the new data and each fact in the fact-checking dataset


*****************************************************************************************************************


