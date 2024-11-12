This project implements a movie recommendation system using machine learning techniques, specifically cosine similarity, to suggest movies similar to a given input movie. The recommendation is based on a combination of features such as genres, keywords, taglines, cast, and director.

Table of Contents
Introduction
Requirements
Data Collection
Preprocessing
Recommendation Logic
How to Run
License
Introduction
The movie recommendation system provides personalized movie suggestions based on a user's favorite movie. The system calculates the similarity between movies using cosine similarity and recommends movies that are most similar to the one provided by the user.

The data is sourced from a CSV file that contains information about various movies, including their genres, keywords, tagline, cast, and director.

Requirements
Before running the code, make sure to install the following Python libraries:

NumPy: For numerical operations.
Pandas: For data manipulation and analysis.
difflib: For finding close matches to the user input movie name.
Scikit-learn: For feature extraction (TF-IDF) and calculating cosine similarity.
To install these libraries, you can run:

bash
Copy code
pip install numpy pandas scikit-learn
Data Collection
The dataset used for this project is in CSV format and includes details of various movies, such as:

Movie title
Genres
Keywords
Tagline
Cast
Director
The dataset is loaded using pandas.read_csv() method:

python
Copy code
movies_data = pd.read_csv('/content/movies.csv')
Preprocessing
The following steps are performed during preprocessing:

Handling Missing Data: Missing values in the columns related to genres, keywords, tagline, cast, and director are replaced with empty strings.
Combining Features: A new column is created by concatenating the relevant features (genres, keywords, tagline, cast, and director), which are then used to generate feature vectors.
python
Copy code
combined_features = movies_data['genres'] + ' ' + movies_data['keywords'] + ' ' + movies_data['tagline'] + ' ' + movies_data['cast'] + ' ' + movies_data['director']
TF-IDF Vectorization: The combined textual features are transformed into feature vectors using the TfidfVectorizer from sklearn.
python
Copy code
vectorizer = TfidfVectorizer()
feature_vectors = vectorizer.fit_transform(combined_features)
Recommendation Logic
Cosine Similarity
The similarity between movies is calculated using cosine similarity, which measures the cosine of the angle between two non-zero vectors in an inner product space. The closer the cosine value is to 1, the more similar the movies are.

python
Copy code
similarity = cosine_similarity(feature_vectors)
User Input and Movie Matching
The user is prompted to input the name of their favorite movie.
The system searches for the closest match to the user input using the difflib.get_close_matches() method.
Based on the index of the matched movie, the system calculates similarity scores with all other movies.
The movies are then sorted by their similarity score in descending order.
Top 30 Recommendations
The system prints the top 30 most similar movies to the user:

python
Copy code
i = 1
for movie in sorted_similar_movies:
  index = movie[0]
  title_from_index = movies_data[movies_data.index == index]['title'].values[0]
  if i < 30:
    print(i, '.', title_from_index)
    i += 1
How to Run
Step 1: Install Dependencies

Make sure to install the required libraries using the command mentioned above.

Step 2: Download the Data

Download the CSV file containing movie data. You can either upload your own dataset or use a sample dataset such as MovieLens dataset.

Step 3: Execute the Code

You can run the code in a Jupyter notebook, Google Colab, or any Python environment of your choice.

To get recommendations:

Run the notebook.
When prompted, enter the name of your favorite movie.
The system will suggest a list of movies based on your input.
