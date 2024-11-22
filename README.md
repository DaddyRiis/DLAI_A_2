# DLAI_A_2

We first download a Kaggle database over Diseases and its related symptoms and treatments.
We load the required packages and load the dataset from filepath. 


We then contruct the semntantic search.
We first load the pre-trained models:
  - Sentence Transformer: Used to convert textual data (symptoms) into numerical embeddings that represent the semantic meaning.
  - Question-Answering Pipeline: Uses a pre-trained model (deepset/roberta-base-squad2) to extract answers from a given context.

Then we define the semantic_search/question-answering function. The search function identifies diseases based on the similarity between user queries and pre-existing symptom descriptions in the dataset and then answers the most related treatments. This is achieved by:
  - Encoding the symptoms and the query into embeddings.
  - Calculating the cosine similarity between the query embedding and each symptom embedding in the dataset.
  - Sorting the results by similarity scores and returning the top results.
The inputs into the semantic_search are a string of text describing symptoms (queries) and number of top matches to recieve, in this code "3".
Key Steps:
  - Encode the query into an embedding.
  - Compute similarity scores using cosine similarity.
  - Sort and return the top matching diseases. 
