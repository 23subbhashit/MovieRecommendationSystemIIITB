# Movie Recommendation System IIITB

## Using Reduced SVD and KMeans:

### Data Loading and Preprocessing:

- The movie, user, and rating datasets are loaded and merged using pandas.
- Missing values and irrelevant columns are handled during preprocessing.
- User ratings are transformed into a matrix format where rows represent users and columns represent movies.

### Dimensionality Reduction (SVD):

- Singular Value Decomposition (SVD) is applied to reduce the dimensionality of the user ratings matrix.
- TruncatedSVD from scikit-learn is used for efficient computation.
- SVD decomposes the user-item interaction matrix into three matrices: U, Σ, and V^T, where U represents user features, Σ is a diagonal matrix of singular values representing the importance of each feature, and V^T represents item features.
- By reducing the dimensionality, we capture the latent features in the data, which helps in understanding user preferences. Latent features represent underlying patterns or characteristics that are not explicitly present in the raw data.

### Clustering (K-Means):

- K-Means clustering is performed on the reduced matrix to group similar users together.
- The optimal number of clusters is determined using the elbow method to find the point where the within-cluster sum of squares (WCSS) starts to level off.
- Each user is assigned to a cluster based on their preferences, allowing us to identify users with similar movie tastes.

### New User Input:

- The system prompts for new user ratings for a set of movies.
- The new user's ratings are stored in a dictionary.

### Recommendation:

- Based on the new user's ratings and similar users' preferences within the same cluster, the system recommends top-rated movies.
- Movies with high average ratings among users in the same cluster are recommended to the new user.
- The top 5 recommended movies are displayed to the user.

## Latent Features in SVD:

Singular Value Decomposition (SVD) helps in extracting latent features from the user-item interaction matrix. These latent features represent underlying patterns or characteristics in the data that are not directly observable. In the context of recommendation systems:

- **User Features (U)**: Each row in the U matrix represents a user's preferences across the latent features. For example, a user's preference for genres like action, comedy, or drama.

- **Item Features (V^T)**: Each column in the transpose of the V matrix represents an item's characteristics across the latent features. For example, a movie's features might include aspects like its genre, director, or actors.

- **Singular Values (Σ)**: The singular values along the diagonal of the Σ matrix indicate the importance of each latent feature. Higher singular values correspond to more significant features that contribute more to the overall structure of the data.

By reducing the dimensionality of the user-item interaction matrix, SVD allows us to capture these latent features, enabling more efficient computation and providing insights into user preferences and item characteristics.
