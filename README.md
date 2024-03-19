# Sentiment Based Product Recommendation

### Problem Statement

The landscape of modern commerce has evolved significantly, with e-commerce emerging as a dominant force. Gone are the days of traditional brick-and-mortar sales; instead, companies establish online platforms to connect directly with consumers. Giants like Amazon, Flipkart, and others have paved the way, offering a vast array of products accessible with a few clicks.

Enterprises like 'Ebuss' are seizing opportunities in this thriving market, carving out niches across diverse product categories. From household essentials to electronics, Ebuss caters to varied consumer needs, aiming to secure a substantial market share.

Yet, in this dynamic arena, staying competitive demands innovation. Ebuss recognizes the importance of leveraging technology to enhance user experience and solidify its position. To compete with established leaders like Amazon and Flipkart, it's crucial to not just keep pace but to lead the way.

As a seasoned Machine Learning Engineer at Ebuss, the task at hand is clear: develop a model to refine product recommendations based on user feedback. This entails crafting a sentiment-based recommendation system, encompassing several key steps:

**1. Data Acquisition and Sentiment Analysis:** Gather user reviews and ratings to discern sentiment.

**2. Building a Recommendation Engine:** Construct a robust recommendation system leveraging the insights from sentiment analysis.

**3. Enhancing Recommendations with Sentiment Analysis:** Integrate sentiment analysis results to fine-tune and personalize product recommendations.

**4. End-to-End Deployment:** Bring the project to fruition by deploying a seamless user interface, facilitating intuitive interaction for users.

In this fast-paced e-commerce landscape, staying ahead demands not just meeting but exceeding customer expectations. With a sentiment-driven approach to recommendations, Ebuss aims to elevate the shopping experience, fostering customer satisfaction and loyalty.

### Solution

* github link: https://github.com/ankurdhuriya/SentimentBasedProductRecommendation

### Built with

* Python 3.9.12
* scikit-learn 1.4.1.post1
* xgboost 2.0.3
* numpy 1.26.4
* nltk 3.8.1
* pandas 2.2.1
* Flask 3.0.2
* Bootstrap CDN 5.1.3

### Solution Approach

* The dataset and attribute descriptions are provided in the dataset folder for reference.
* Initial steps include Data Cleaning, Visualization, and Text Preprocessing (NLP) on the dataset. TF-IDF Vectorization is employed to convert textual data (review_title + review_text) into numerical vectors, measuring the relative importance of words across documents.
* Addressing the Class Imbalance Issue: SMOTE Oversampling technique is applied to balance the distribution of classes before model training.
* Machine Learning Classification Models: Various models such as Logistic Regression, Naive Bayes, and Tree Algorithms (Decision Tree, Random Forest, XGBoost) are trained on the vectorized data and target column (user_sentiment). The objective is to classify sentiment as positive (1) or negative (0). The best model is chosen based on evaluation metrics including Accuracy, Precision, Recall, F1 Score, and AUC. XGBoost emerges as the top performer.
* Collaborative Filtering Recommender System: Utilizing both User-User and Item-Item approaches, a recommender system is developed. Evaluation is performed using the RMSE metric.
SentimentBasedProductRecommendation.ipynb: This Jupyter notebook contains the code for Sentiment Classification and Recommender Systems.
* Product Sentiment Prediction: Top 20 products are filtered using the recommender system. For each product, user_sentiment is predicted for all reviews, and the top 5 products with higher positive user sentiment are selected (model.py).
* Model Persistence and Deployment: Machine Learning models are saved in pickle files within the pickle directory. A Flask API (app.py) is developed to interface and test these models. The User Interface is set up using Bootstrap and Flask Jinja templates (templates/index.html) without additional custom styles.