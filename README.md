# Music_Recommender
Spotify Million Song Data Analysis and Recommendation System
This Python script  analyzes a dataset of Millennial Spotify songs and builds a song recommendation system.

Functionality
Data Loading and Cleaning:

Loads the CSV file "spotify_millsongdata.csv" into a Pandas DataFrame.
Saves and reloads the DataFrame using pickle for efficiency.
Displays the first 5 and last 5 rows of the DataFrame.
Checks for missing values and displays the count of missing values per column.
Randomly samples 5000 rows from the DataFrame.
Drops the "link" column and resets the index.
Cleans the "text" column by converting it to lowercase, removing leading whitespace, and replacing newlines with spaces.
Text Preprocessing:

Imports the NLTK library for natural language processing.
Defines a function token that tokenizes text, applies Porter stemming, and joins the tokens back into a string.
TF-IDF Vectorization:

Imports the TfidfVectorizer class from scikit-learn for creating TF-IDF vectors.
Creates a TF-IDF vectorizer object, analyzing words and removing English stop words.
Transforms the "text" column into a TF-IDF matrix.
Cosine Similarity Calculation:

Calculates the cosine similarity between all songs in the TF-IDF matrix.
This similarity metric measures how similar the song descriptions are based on the words they contain.
Song Recommendation System:

Defines a function recommender that takes a song name as input.
Finds the index of the song in the DataFrame.
Sorts the cosine similarity scores for that song in descending order.
Returns a list of 20 song recommendations (excluding the input song itself) based on the highest similarity scores.
Data Persistence:

Uses pickle to save the cosine similarity matrix to a file named "similarity.pkl" for later use.
Includes code for loading the pickled data and handling potential errors.
Usage
Prerequisites:
Make sure you have Python installed with libraries like Pandas, NLTK, scikit-learn, and pickle. You can install them using pip install pandas nltk scikit-learn pickle.
Running the Script:
Save the script as a Python file (e.g., mill_song_analysis.py).
Run the script from your terminal using python mill_song_analysis.py.
This will execute the code and potentially generate recommendations based on the "Enough For You" song (or whichever song is used in the recommender function call).
Notes
This script provides a basic example of song recommendation using TF-IDF and cosine similarity.
You can modify the script to:
Use a different dataset.
Preprocess the text data further (e.g., removing punctuation, stemming vs. lemmatization).
Experiment with different recommendation algorithms.
Refine the song recommendation function to take user preferences as input.
