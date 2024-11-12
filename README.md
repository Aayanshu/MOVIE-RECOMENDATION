# Movie Recommendation System Using Machine Learning with Python

This project implements a **Movie Recommendation System** that suggests movies based on a given input movie. It uses **Cosine Similarity** and **TF-IDF Vectorization** to calculate the similarity between movies. The system recommends movies by analyzing various features such as **genres**, **keywords**, **tagline**, **cast**, and **director**.

## Table of Contents

1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Data Collection](#data-collection)
4. [Preprocessing](#preprocessing)
5. [Cosine Similarity](#cosine-similarity)
6. [How to Use](#how-to-use)
7. [Example](#example)
8. [License](#license)

---

## Introduction

This **Movie Recommendation System** uses a dataset of movies, extracting features like genres, keywords, tagline, cast, and director. These features are then combined into a single text feature for each movie. The **TF-IDF Vectorization** technique is used to convert these text features into numerical feature vectors, which are then used to calculate **Cosine Similarity** to recommend the most similar movies based on a user's favorite movie.

---

## Requirements

Before running the project, ensure you have the following Python libraries installed:

- **NumPy**: For numerical operations.
- **Pandas**: For data manipulation and analysis.
- **Scikit-learn**: For feature extraction (TF-IDF) and calculating cosine similarity.
- **Difflib**: For finding close matches to the user input movie name.

You can install these libraries using the following pip command:

movies_data = pd.read_csv('/path/to/movies.csv')
combined_features = movies_data['genres'] + ' ' + movies_data['keywords'] + ' ' + movies_data['tagline'] + ' ' + movies_data['cast'] + ' ' + movies_data['director']
vectorizer = TfidfVectorizer()
feature_vectors = vectorizer.fit_transform(combined_features)
similarity = cosine_similarity(feature_vectors)

