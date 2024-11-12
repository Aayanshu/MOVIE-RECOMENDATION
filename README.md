This project implements a movie recommendation system using machine learning techniques, specifically cosine similarity, to suggest movies that are similar to a given movie. The recommendation is based on a combination of features such as genres, keywords, tagline, cast, and director.

Table of Contents
Introduction
Requirements
Data Collection
Preprocessing
Recommendation Logic
How to Run
License
Introduction
This Movie Recommendation System provides personalized movie suggestions based on the user's favorite movie. It uses the cosine similarity metric to calculate the similarity between movies based on selected features, including:

Genres
Keywords
Tagline
Cast
Director
The system then suggests the top 30 movies most similar to the movie provided by the user.

Requirements
Before running the code, ensure you have the following Python libraries installed:

NumPy: For numerical operations.
Pandas: For data manipulation and analysis.
Scikit-learn: For feature extraction (TF-IDF) and calculating cosine similarity.
Difflib: For finding close matches to the user input movie name.
To install these libraries, run the following command:

bash
Copy code
pip install numpy pandas scikit-learn
Data Collection
The dataset used in this project should be in CSV format with the following essential columns:

title: The name of the movie.
genres: The genre(s) of the movie (e.g., action, drama).
keywords: Keywords related to the movie.
tagline: The tagline or slogan of the movie.
cast: A list of cast members involved in the movie.
director: The director of the movie.
index: A unique identifier for each movie (used for indexing purposes).
The dataset is loaded using pandas.read_csv().

python
Copy code
movies_data = pd.read_csv('/content/movies.csv')
Make sure to replace the file path with the correct location of your dataset.

Preprocessing
The following preprocessing steps are performed on the dataset:

Handling Missing Data: Missing values in the relevant columns (genres, keywords, tagline, cast, director) are replaced with empty strings.

Feature Combination: The genres, keywords, tagline, cast, and director columns are combined into a single string for each movie. This combined feature will be used to generate the feature vectors.

python
Copy code
combined_features = movies_data['genres'] + ' ' + movies_data['keywords'] + ' ' + movies_data['tagline'] + ' ' + movies_data['cast'] + ' ' + movies_data['director']
TF-IDF Vectorization: The combined features are transformed into numerical feature vectors using TfidfVectorizer from Scikit-learn.
python
Copy code
vectorizer = TfidfVectorizer()
feature_vectors = vectorizer.fit_transform(combined_features)
Recommendation Logic
Cosine Similarity
The core of the recommendation system is based on cosine similarity, which measures the similarity between two non-zero vectors. A higher cosine similarity indicates that two movies are more similar.

python
Copy code
similarity = cosine_similarity(feature_vectors)
User Input and Movie Matching
The user is asked to input the name of their favorite movie.
The system finds the closest match to the user’s input from the dataset using difflib.get_close_matches().
python
Copy code
movie_name = input('Enter your favourite movie name: ')
find_close_match = difflib.get_close_matches(movie_name, list_of_all_titles)
The system calculates similarity scores for the selected movie and sorts the movies by their similarity score.

The top 30 most similar movies are displayed to the user.

How to Run
Step 1: Install Dependencies
Make sure to install the required libraries using the following command:

bash
Copy code
pip install numpy pandas scikit-learn
Step 2: Download or Prepare Data
The project uses a CSV file with movie information. You can either:

Upload your own CSV file with columns like title, genres, keywords, tagline, cast, director, and index, or
Use a publicly available dataset, such as the MovieLens dataset.
Ensure that the file path to your CSV file is correct in the code:

python
Copy code
movies_data = pd.read_csv('/content/movies.csv')
Step 3: Execute the Code
Open a Jupyter notebook, Google Colab, or any Python environment.
Run the script.
Enter the name of your favorite movie when prompted.
The system will suggest the top 30 movies most similar to your input.
