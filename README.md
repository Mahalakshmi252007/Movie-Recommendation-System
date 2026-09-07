**🎬 Movie Recommendation System**

**📌 Project Overview**

The Movie Recommendation System is a content-based recommendation project designed to recommend movies based on a user's recently watched movies.

The system analyzes movie information such as title, genres, and overview and converts the textual information into numerical embeddings. Different recommendation approaches are implemented and compared to identify the best-performing model.

The project evaluates:

Legacy / Past Recommendation Model
Word2Vec-based Recommendation Model
Sentence Transformer-based Recommendation Model

The Sentence Transformer (all-MiniLM-L6-v2) achieved the best overall recommendation success rate of approximately 64.75%.

**🎯 Objectives**

Build a movie recommendation system using movie metadata.
Perform data preprocessing and exploratory data analysis.
Apply NLP techniques to movie text data.
Generate movie embeddings using Word2Vec and Sentence Transformers.
Calculate similarity between movies using Cosine Similarity.
Compare different recommendation approaches.
Identify the best-performing recommendation model.
Generate recommendations for an unseen user's watch history.

**🗂️ Dataset**

The recommendation system uses movie-related textual information including:

Feature	Description
title	Movie title
genres	Movie genre information
overview	Movie description/plot
date	Date associated with movie watching/evaluation
movie_watch	Movie actually watched by the user

The movie text information is used as the primary signal for generating content-based recommendations.

**🔄 Project Workflow**

Movie Dataset
      ↓
Data Preprocessing
      ↓
Exploratory Data Analysis
      ↓
Text Processing
      ↓
Feature / Embedding Generation
      ↓
 ┌───────────────┬──────────────────────────┐
 │    Word2Vec   │   Sentence Transformer   │
 └───────────────┴──────────────────────────┘
      ↓
Cosine Similarity
      ↓
Top-N Movie Recommendations
      ↓
Evaluation
      ↓
Model Comparison
      ↓
Best Model Selection

**🧹 Data Preprocessing**

The movie dataset is prepared before building the recommendation models.

The preprocessing stage includes working with movie metadata and preparing the textual information required for embedding generation.

The main text features used for recommendation are:

Movie title
Genres
Movie overview

**📊 Exploratory Data Analysis**

EDA is performed to understand the recommendation performance and user-watch data.

The project includes analysis of recommendation success across different periods and compares the performance of different recommendation approaches.

**🤖 Recommendation Approaches**

Word2Vec Recommendation Model

Word2Vec is used to generate word-level embeddings from movie-related text.

The movie information is converted into numerical vector representations, which are then used to calculate similarity between movies.

Overall Success Rate: ~22.7%

Approach
Movie Text
    ↓
Word2Vec Embeddings
    ↓
Movie Vector
    ↓
Cosine Similarity
    ↓
Top-N Recommendations

Sentence Transformer Recommendation Model

The Sentence Transformer approach uses the pre-trained:

all-MiniLM-L6-v2

The movie's title, genres, and overview are combined and converted into a semantic embedding.

The embeddings of recently watched movies are averaged to create a representation of the user's general taste. Cosine similarity is then used to identify the most similar unwatched movies.

Approach
Title + Genres + Overview
          ↓
Sentence Transformer
          ↓
Movie Embedding
          ↓
Average Watched-Movie Embeddings
          ↓
User Taste Vector
          ↓
Cosine Similarity
          ↓
Top-10 Recommendations

**🏆 Model Comparison**

Recommendation Approach	Overall Success Rate	Embedding Type
Legacy / Past Model	~13.85%	Non-semantic / Rules-based
Word2Vec	~22.7%	Word-level, static
Sentence Transformer	~64.75%	Sentence-level, contextual

The Sentence Transformer model clearly outperformed both the legacy and Word2Vec approaches.


**👤 Unseen User Recommendation**

The best-performing Sentence Transformer model is also demonstrated on an unseen watch history.

Example:

unseen_watched_movies = [
    'The Dark Knight',
    'Inception',
    'Interstellar'
]

The system uses these movies to generate a new Top-10 recommendation list, demonstrating how the recommender can be applied to a new watch history.

Sentence Transformer achieved approximately 64.75% recommendation success rate, making it the best-performing approach in this project.

**🛠️ Technologies Used**

Python
Pandas
NumPy
Matplotlib
Scikit-learn
Word2Vec
Sentence Transformers
Cosine Similarity
Jupyter Notebook / Google Colab

**🚀 Future Improvements**

Implement Precision@K, Recall@K and NDCG@K for stronger evaluation.
Develop a hybrid recommendation system combining content-based and collaborative filtering.
Include user ratings and preferences.
Incorporate movie popularity and recency.
Develop a cold-start recommendation strategy.
Perform an A/B test against the existing recommendation system.
Explore stronger transformer models when computational resources allow.

**🏁 Conclusion**

The project demonstrates that semantic embeddings from Sentence Transformers can significantly improve content-based movie recommendations compared with traditional Word2Vec and legacy approaches.

Among the evaluated models, all-MiniLM-L6-v2 Sentence Transformer performed the best, achieving an overall success rate of approximately 64.75%.

Therefore, the Sentence Transformer-based recommendation engine is selected as the best-performing model for this project.
