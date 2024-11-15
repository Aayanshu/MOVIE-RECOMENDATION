# Movie Recommendation System Using Machine Learning with Python

This project implements a movie recommendation system using **machine learning techniques**, specifically **cosine similarity**, to suggest movies based on a given input movie. The recommendation is based on multiple features like **genres**, **keywords**, **tagline**, **cast**, and **director**.

## Table of Contents

1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Data Collection](#data-collection)
4. [Preprocessing](#preprocessing)
5. [Recommendation Logic](#recommendation-logic)
6. [How to Run](#how-to-run)
7. [License](#license)

---

## Introduction

This **Movie Recommendation System** suggests movies based on a user's favorite movie. The system uses **cosine similarity** to compute the similarity between movies based on various features. It calculates similarity scores for each movie in the dataset and then recommends the most similar ones.

Key features used for calculating similarity:
- **Genres**
- **Keywords**
- **Tagline**
- **Cast**
- **Director**

The system outputs the top 30 most similar movies based on the movie entered by the user.

---

## Requirements

Before running the code, ensure that you have the following Python libraries installed:

- **NumPy**: For numerical operations.
- **Pandas**: For data manipulation and analysis.
- **Scikit-learn**: For feature extraction (TF-IDF) and calculating cosine similarity.
- **Difflib**: For finding close matches to the user input movie name.

You can install these dependencies using the following command:

```bash
pip install numpy pandas scikit-learn
