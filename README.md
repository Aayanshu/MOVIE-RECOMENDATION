# Movie Recommendation System Using Machine Learning with Python

This project implements a **Movie Recommendation System** that suggests movies based on a given input movie. It uses **Cosine Similarity** and the **TF-IDF** vectorizer to calculate the similarity between movies. The system recommends similar movies by analyzing the **genres**, **keywords**, **tagline**, **cast**, and **director** of the movies.

## Table of Contents

1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Data Collection](#data-collection)
4. [Preprocessing](#preprocessing)
5. [Cosine Similarity](#cosine-similarity)
6. [How to Use](#how-to-use)
7. [License](#license)

---

## Introduction

This **Movie Recommendation System** uses a dataset of movies, extracting various features like genres, keywords, tagline, cast, and director. By combining these features into a single string, it uses **TF-IDF Vectorization** to convert the text data into numerical feature vectors. Then, it calculates the **Cosine Similarity** between the movies to recommend the most similar movies based on a user’s favorite movie.

---

## Requirements

Before running the project, ensure you have the following Python libraries installed:

- **NumPy**: For numerical operations.
- **Pandas**: For data manipulation and analysis.
- **Scikit-learn**: For feature extraction (TF-IDF) and calculating cosine similarity.
- **Difflib**: For finding close matches to the user input movie name.

You can install these libraries using the following pip command:

```bash
pip install numpy pandas scikit-learn
