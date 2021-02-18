# SOTU-Buchanan-1857-Topic-Modelling
Topic modelling of SOTU address by U.S. President James Buchanan in 1857. 

The State of the Union is an annual address by the President of the United States before a joint session of congress. In it, the President reviews previous year and lays out his legislative agenda for the coming year.


# SOTU Buchanan 1857 : Project Overview
* Identified the topic of this address by using Latent Dirichlet Allocation (LDA).
* Employed Term Frequency-Inverse Document Frequency (TF-IDF) to converted tokenized words to vectors.
* Tuned the hyperparameters such as number of topics, alpha, beta in order to maximize the model performance. 
* Evaluated and chose the best model according to Coherence score and Perplexity.

## Code and Resources Used 
* **Python Version:** 3.8.5
* **Conda Version:** 4.9.2
* **Packages:** pandas, numpy, matplotlib, gensim, nltk, wordninja, pyLDAvis
* **Dataset:** https://www.kaggle.com/rtatman/state-of-the-union-corpus-1989-2017?select=Buchanan_1857.txt

## Data Preparation

*	Tokenizing the address into sentences. Here, sentences of address were treated as documents of corpus. So, i aim to discover the distribution over terms (topics) by extracting information from each sentence.
*	Removing stopwords and words of length less than 4 characters.
*	Due to the fact that the original address text contains a lot of concatenated word, wordninja is an appropriate and useful package to split and tokenize words at the same time.
*	Lemmatizing tokenized words in order to normalize text dataset and also converting them to lowercase.
*	Using TF-IDF to create the document term matrices of dataset.
 

## Model Training

From the Gensim library, **models.ldamulticore** was used in order to speed up the training process. After that, hyperparameters of the model were tuned one by one and model was updated according to the previous best hyperparameters. First, i tuned the *num of topics* hyperparameter and compared the score given by each model. The second stage was to tuned the *alpha* and followed by the *beta* hyperparamter. Best hyperparameter of the model was selected by comparing the *Coherence score* and *Perplexity*.

## Results

Best tuned LDA model with *num of topics* : 8, *alpha* : 0.04, *beta* : symmetric, led to the Coherence score of 0.36868 and Perplexity of -6.7241. More information on distribution over terms and visualization can be found in this GitHub code repository.

