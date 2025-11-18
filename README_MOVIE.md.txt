 🎬 Movie Rating Prediction System

A comprehensive machine learning project that predicts user movie ratings using collaborative filtering and ensemble methods. Built as part of my internship at Arch Technologies.

 📋 Table of Contents
- [Overview](#overview)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Models Implemented](#models-implemented)
- [Results](#results)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Key Insights](#key-insights)
- [Future Improvements](#future-improvements)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

 🎯 Overview

This project tackles the challenge of predicting how users will rate movies they haven't seen yet - a fundamental problem in recommendation systems. By implementing and comparing multiple machine learning approaches, we achieved an RMSE of 0.7944 with a Random Forest model, successfully handling a highly sparse (98.3%) user-movie rating matrix.

🔍 Problem Statement

Task: Build a model to predict how a user might rate a movie they haven't seen yet.

Requirements:
- Preprocess movie ratings data
- Implement collaborative filtering techniques
- Build regression models
- Evaluate model performance comprehensively
- Create a functional recommendation system

 📊 Dataset

Source: [MovieLens Latest Small Dataset](https://grouplens.org/datasets/movielens/latest/)

Statistics:
- Total Ratings: 100,836
- Unique Users: 610
- Unique Movies: 9,724
- Rating Scale: 0.5 to 5.0 (0.5 increments)
- Average Rating: 3.50
- Matrix Sparsity: 98.30%

Files Included:
- `ratings.csv` - User ratings for movies
- `movies.csv` - Movie titles and genres
- `tags.csv` - User-generated tags for movies
- `links.csv` - Links to IMDB and TMDB

🤖 Models Implemented
 1. User-Based Collaborative Filtering
- Memory-based approach using cosine similarity
- K-nearest neighbors algorithm (k=30)
- Performance: RMSE: 0.9423, MAE: 0.7099

 2. Matrix Factorization (SVD)
- Singular Value Decomposition with 50 latent factors
- Model-based collaborative filtering
- Performance: RMSE: 2.8584, MAE: 2.6325

3. Linear Regression
- Baseline regression model with engineered features
- Performance:** RMSE: 0.8109, MAE: 0.6159

4. Ridge Regression
- Regularized linear regression (α=1.0)
- Performance:** RMSE: 0.8109, MAE: 0.6159

5. Random Forest Regressor ⭐ (Best Model)
- Ensemble method with 100 trees
- Max depth: 10
- Performance: RMSE: 0.7944, MAE: 0.5934, R²: 0.4264

 🏆 Results

 Model Performance Comparison

| Model | RMSE | MAE | R² Score |
|-------|------|-----|----------|
| Random Forest ⭐ | 0.7944 | 0.5934 | 0.4264 |
| Linear Regression | 0.8109 | 0.6159 | 0.4022 |
| Ridge Regression | 0.8109 | 0.6159 | 0.4022 |
| User-Based CF | 0.9423 | 0.7099 | 0.1858 |
| SVD | 2.8584 | 2.6325 | -6.4913 |

 Feature Importance (Random Forest)

| Feature | Importance |
|---------|-----------|
| Movie Average Rating | 58.66% |
| User Average Rating | 28.65% |
| Movie Rating Std | 4.62% |
| User Rating Count | 3.93% |
| Movie Rating Count | 2.66% |
| User Rating Std | 1.48% |

 🚀 Installation

 Prerequisites
```bash
Python 3.8+
Google Colab (recommended) or Jupyter Notebook
```

 Required Libraries
```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy
```

 Clone Repository
```bash
git clone https://github.com/yourusername/movie-rating-prediction.git
cd movie-rating-prediction
```

 💻 Usage

 Quick Start (Google Colab)

1. Upload the notebook to Google Colab
2. Download the dataset:
   ```bash
   wget https://files.grouplens.org/datasets/movielens/ml-latest-small.zip
   ```
3. Run cells sequentially (Cell 1 → Cell 21)

 Local Setup

1. Download the dataset:
   ```bash
   wget https://files.grouplens.org/datasets/movielens/ml-latest-small.zip
   unzip ml-latest-small.zip
   ```

2. Run the Jupyter notebook:
   ```bash
   jupyter notebook movie_rating_prediction.ipynb
   ```

Making Predictions

```python
 Recommend movies for a specific user
recommendations = recommend_movies_for_user(
    user_id=123,
    top_n=10,
    model_type='rf'  # Options: 'rf', 'lr', 'ridge', 'svd'
)
print(recommendations)
```

 📁 Project Structure

```
movie-rating-prediction/
│
├── movie_rating_prediction.ipynb    # Main notebook with all code
├── README.md                         # Project documentation
├── requirements.txt                  # Python dependencies
├── LICENSE                           # MIT License
│
├── data/                            # Dataset folder (after extraction)
│   ├── ml-latest-small/
│   │   ├── ratings.csv
│   │   ├── movies.csv
│   │   ├── tags.csv
│   │   └── links.csv
│
├── results/                         # Generated results (after running)
│   ├── model_comparison_results.csv
│   ├── genre_statistics.csv
│   ├── top_50_most_rated_movies.csv
│   ├── top_50_highest_rated_movies.csv
│   └── sample_predictions.csv
│
└── visualizations/                  # Generated plots (optional)
    ├── eda_plots.png
    ├── model_comparison.png
    ├── prediction_analysis.png
    └── genre_analysis.png
```

 💡 Key Insights

 1. Feature Engineering Matters
Movie and user average ratings are the strongest predictors, accounting for 87% of feature importance.

 2. Ensemble Methods Win
Random Forest outperformed traditional collaborative filtering methods due to effective feature engineering.

 3. Data Sparsity Challenge
With 98.3% sparsity, traditional matrix factorization struggled. Feature-based approaches handled this better.

 4. Popular Movies
- Most Rated: Forrest Gump (1994) - 329 ratings
- Highest Rated: Shawshank Redemption, The (1994) - 4.43/5 average
- Most Popular Genre: Drama - 41,928 ratings

 5. User Behavior Patterns
- Average ratings per user: 165
- Average ratings per movie: 10
- Most common rating: 4.0 stars

🔮 Future Improvements

- [ ] Implement deep learning models (Neural Collaborative Filtering)
- [ ] Add content-based filtering using movie metadata
- [ ] Incorporate temporal dynamics (time-aware recommendations)
- [ ] Implement online learning for real-time updates
- [ ] Add A/B testing framework for model comparison
- [ ] Build REST API for production deployment
- [ ] Create interactive web dashboard using Streamlit
- [ ] Implement explainable AI features

 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

 🙏 Acknowledgments

- Arch Technologies - For providing this internship opportunity and guidance
- GroupLens Research - For the MovieLens dataset
- scikit-learn community - For excellent machine learning tools
- Stack Overflow & Medium - For countless helpful discussions

 📧 Contact

Your Name - [abdulrafiumohammed2019@gmail.com](mailto:abdulrafiumohammed2019@gmail.com)

LinkedIn: [linkedin.com/in/abdulrafiu-mohammed-aislt-9ab4051ba/](https://www.linkedin.com/in/abdulrafiu-mohammed-aislt-9ab4051ba/)

Project Link: [github.com/Omotosho-2579/Arch_Technologies_Task](https://github.com/Omotosho-2579/Arch_Technologies_Task)


⭐ If you found this project helpful, please consider giving it a star!



 📚 References

1. F. Maxwell Harper and Joseph A. Konstan. 2015. The MovieLens Datasets: History and Context. ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4: 19:1–19:19.
2. Koren, Y., Bell, R., & Volinsky, C. (2009). Matrix factorization techniques for recommender systems. Computer, 42(8), 30-37.
3. Ricci, F., Rokach, L., & Shapira, B. (2015). Recommender systems handbook. Springer.




  Made with ❤️ and ☕ during my internship at Arch Technologies
