# MovieRecomSys_KNNB&SVD&ALS

## Project Overview
This project is a movie recommendation system that utilizes KNNB (K-Nearest Neighbors-Based), SVD (Singular Value Decomposition), and ALS (Alternating Least Squares) algorithms. By analyzing user rating data, the system generates personalized movie recommendations and addresses scalability issues in large datasets.

## Table of Contents
- [Data Visualization](#data-visualization)
- [Model Training and Evaluation](#model-training-and-evaluation)
- [Dataset Source](#dataset-source)

## Data Visualization

### Most Viewed Movies Visualization
By analyzing the viewing records in the dataset and visualizing the most viewed movies, we showcase user interest in different movies.

![Most Viewed Movies](Most_Viewed.png)
### Visualize the Distribution of Average Ratings per User
This visualization displays the distribution of average ratings per user, helping to understand user rating habits and preferences.

![Average Ratings Distribution](Distribution.png)  
### Top 10 Movies with the Highest Average Ratings
This visualization highlights the top 10 movies with the highest average ratings across all users, showcasing popular high-quality movies within the dataset.

![Top Rated Movies](Average_Ratings.png)  

## Model Training and Evaluation

### KNNB - Generating Recommendations
We use the KNNB algorithm to generate recommendations for a specific user. Here are the top 10 recommended movies for user ID `99476`:

1. MovieID: 26524, MovieTitle: Times of Harvey Milk, The (1984)
2. MovieID: 1259, MovieTitle: Stand by Me (1986)
3. MovieID: 2475, MovieTitle: 52 Pick-Up (1986)
4. MovieID: 318, MovieTitle: Shawshank Redemption, The (1994)
5. MovieID: 68319, MovieTitle: X-Men Origins: Wolverine (2009)
6. MovieID: 8810, MovieTitle: AVP: Alien vs. Predator (2004)
7. MovieID: 1041, MovieTitle: Secrets & Lies (1996)
8. MovieID: 2527, MovieTitle: Westworld (1973)
9. MovieID: 4369, MovieTitle: Fast and the Furious, The (2001)
10. MovieID: 4995, MovieTitle: Beautiful Mind, A (2001)

### SVD
The SVD algorithm is employed to enhance the accuracy and personalization of the recommendations.

### ALS - Addressing Scalability Issues
To handle memory errors encountered in the KNNB and SVD models, we implemented an Apache Spark ALS (Alternating Least Squares) model, which is optimized for distributed data processing and can handle larger datasets.<br>
While KNNB and SVD models required data sampling to avoid memory issues, leading to potential accuracy trade-offs, ALS resolves these limitations by processing the full dataset without sampling.<br>
Reference: [Exploring Apache Spark for Movie Recommendation](https://www.kaggle.com/code/aminaromdhani/exploring-apache-spark-for-movie-recommendation)

Below are the personalized movie recommendations for user ID 1, including predicted ratings:<br>
| MovieID | UserID | Prediction |
|---------|--------|------------|
| 5767    | 1      | 4.3713     |
| 4973    | 1      | 4.3191     |
| 3949    | 1      | 4.0553     |
| 8014    | 1      | 4.0485     |
| 5878    | 1      | 4.0041     |
| 7327    | 1      | 3.9329     |
| 6370    | 1      | 3.9317     |
| 1175    | 1      | 3.9191     |
| 5147    | 1      | 3.8945     |
| 5912    | 1      | 3.8761     |
| 307     | 1      | 3.8094     |
| 6539    | 1      | 3.4850     |
| 2632    | 1      | 3.4150     |
| 2011    | 1      | 3.2457     |
| 8729    | 1      | 3.0281     |
| 2012    | 1      | 2.9614     |


### Evaluation Metrics
We evaluate the models using the following metrics:
- RMSE (Root Mean Square Error)
- MAE (Mean Absolute Error)

The ALS model was evaluated with the following results:<br>
Root Mean Squared Error (RMSE): 0.8209

The visualization of the evaluation results of KNNB and SVD is as follows:

![Model Evaluation](RMSE.png) 

## Dataset Source
The datasets used in this project are sourced from Kaggle, containing movie information and user ratings.  
You can download the datasets from the following link:
- [Movie Recommendation System Dataset](https://www.kaggle.com/datasets/parasharmanas/movie-recommendation-system/data)

The dataset includes two files:
- `movies.csv`: Contains movie information.
- `ratings.csv`: Contains user rating information.
