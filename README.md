# Movie_Recommendation_System

Movie Recommendation System
This repository contains a simple movie recommendation system built using collaborative filtering techniques, specifically leveraging user ratings to find similar movies.

Project Description
This project demonstrates a collaborative filtering movie recommendation system. Given a movie that a user likes, the system recommends other movies that are similar based on the collective ratings of users. The core idea is to represent movies in a user-item matrix and find movies that are 'nearest neighbors' to a given movie in that space.

Data
The ratings.csv file contains the dataset used for this recommendation system. It includes:

userId: Unique identifier for each user.
movieId: Unique identifier for each movie.
title: Title of the movie.
rating: The rating given by the user to the movie.
Setup
To run this project, you'll need to have the following Python libraries installed:

pandas
numpy
scikit-learn
scipy
You can install them using pip:

pip install pandas numpy scikit-learn scipy
Usage
Load the Data: The ratings.csv file is loaded into a pandas DataFrame.
Create User-Item Matrix: A sparse user-item matrix is created where rows represent movies, columns represent users, and values are the ratings. This matrix is essential for calculating similarity between movies.
Define Recommendation Function: The recommend_similar function takes a movie title as input and returns a list of recommended movies.
To get recommendations, simply call the recommend_similar function with your desired movie title and the number of recommendations k:

recommend_similar("The Dark Knight", ratings, X,
                  movie_mapper, movie_inv_mapper, k=5)
Example Output:
Because you liked **The Dark Knight**, you might also enjoy:
- Fight Club
- The Pianist
- Parasite
- 12 Angry Men
- The Lord of the Rings: The Return of the King
Algorithm Explanation
The recommendation algorithm employed is based on Nearest Neighbors and Cosine Similarity, which falls under unsupervised learning.

User-Item Matrix Creation: A sparse matrix is constructed where movies are rows and users are columns. Each cell contains a user's rating for a specific movie. This matrix effectively transforms each movie into a vector of ratings across all users.
Cosine Similarity: When a movie recommendation is requested, the system calculates the cosine similarity between the vector representation of the chosen movie and all other movie vectors. Cosine similarity measures the angle between two vectors; a smaller angle (closer to 0) indicates higher similarity.
Nearest Neighbors: The NearestNeighbors model from scikit-learn is used to efficiently find the 'k' movies that have the highest cosine similarity (i.e., are the closest neighbors) to the input movie. These 'k' movies are then returned as recommendations.
This approach is unsupervised because it doesn't rely on a target variable to train a model. Instead, it discovers patterns and relationships (movie similarities) directly from the inherent structure of the rating data.
