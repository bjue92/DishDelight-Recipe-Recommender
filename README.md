# DishDelight - Recipe Recommender

Food waste is a huge problem that goes subtlety unnoticed in our household as the amount of food thrown out each week may be minimal but accumulates to noticeable effects.

Our goal of this project is to create a recipe recommender based on ingredients leftover in the fridge or provide users the ability to make new and interesting recipes with similar ingredients. This will allow households to reduce food wasted.


## Table of Contents
- Data Source
- Technologies/Packages
- Models
- Results
- Limitations

## Data Source
There were three datasets that were sourced from Kaggle, which were web-scrapped from Food.com. After merging, preprocessing and cleaning the datasets, the recipe dataset totaled 230,000 rows and 11 columns, and the review dataset totaled 765,000 rows and 3 columns. For further information regarding the details of the data columns, please see the Jupyter notebook. 

https://www.kaggle.com/datasets/irkaal/foodcom-recipes-and-reviews?select=reviews.csv
https://www.kaggle.com/datasets/shuyangli94/foodcom-recipes-with-search-terms-and-tags
https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions?select=RAW_recipes.csv

## Technologies/Packages
- Python
- Pandas
- NumPy
- Surprise
- NLTK
- Jupyter Notebook
- Gensim
- Sklearn

## Models
- FunkSVD Collaborative Recommender
- Word2Vec + Mean Embeddings Content-Based Recommender
- Hybrid Recommender

## Results
Out of all our models, the content-based recommender is providing the best results. Although the user’s historical preference is not considered, by providing a large enough list (10-20 recipes), the user has the ability to pick the one that he or she likes the most. If we do look at the recipes recommended though, they are very plain and bland and do not seem like recipes that most people would like. We will need to refine our collaborative and hybrid model to attain better filtering results to help us create a more refined and personalized recommendation list for individual users.

## Limitations
Our initial goal was to create a recipe recommender that allowed the user to utilize leftover ingredients in the fridge to create a dish that they would like. Since we are using cosine similarity for our content-based recommender, we can see from the results that certain recipe ingredients do not match the inputs. We tried to compensate for this using the Jaccard similarity score which compares the same items between lists, but the score came out very poorly at 10%. 

Our hybrid model requires manual hyperparameter tuning in regards to how large the refined dataset should be. In addition, we are only testing on one user when we are running our test trials. We require a better method to determine this hyperparameter as manually tuning this hyperparameter is not the best method.

***How can we quantify the amount of food waste reduced from our project?***

Currently our models won’t be able to quantify this question. The value that we can put on this can only be determined through some sort of customer feedback loop once we implement the model. The issue is that someone could be using the recommender just to suggest a recipe. To counter this issue, prior to entering any sort of input ingredients and recommending any recipe, we can have an initial questionnaire regarding the use of the recommender. This may be a turn-off to some customers as it’s an additional step, but hopefully the environmental impact behind the use case will entice customers.



