# Yelp Recommender

# Context and Goal
Nowadays, personalized recommendation systems are implemented by many online businesses, which try to identity user's specific tastes then provide them with relevant products to enhance user's experience. Users, in turn, would be able to enjoy the convenience of exploring what they potentially like with ease. However, mainstream restaurant recommendation apps have not adopted personalized restaurants recommenders. Therefore, finding an ideal restaurant is always a struggle for newcomers and sometimes even for local people, who are looking for places new and exiciting to go. I aim to build a personalized restaurant recommender that not only considers the interactions between customers and restaurants but also consider different aspects of customer's experience and importance. 

# Methodologies

I used natural language processing and unsupervised learning as an approach to the finding different aspects of restaurant experience. The topic modeling allowed me to find 15 categories of food and 4 main aspects of restaurant experience that will later be used as a rating system for recommender system. 

Workflow:

* Gather necessary files from yelp

* Strip text from documents

* NLP pre-processing:
  * removal of non-english words
  * count-vectorizing: best to maintain importance of commonly used words such as "consciousness", so I decided to forgo TF-IDF after trying it.
  * SpaCy lemmatization (most effective out of all tried)
  * stop_words and min_df (min_df set to 0.02 yielded best topics)
  
*Topic Modeling
  * LSA/NMF as baseline
  * LDA
  
* Visualization
  * pyLDAvis for visualizing topic similarity and most important terms
  * Group Type similarity with PCA and t-SNE

* Collaborative Recommendation System

# Findings, Implications and Conclusions
With these methods, I was able to uncover 4 main aspects a user considers important when it comes to rating restaurant experience. Furthermore, I was able to utilize a weighted importance of these aspects to better recommend restaurant based on user input. 

I hope to adopt a hybrid approach to build a personalized restuarant recommender using interaction information between itens and user utilizing LightFM model. The matrix factorization model can capture latent features about attributes of users and items, which represent their tastes as well. 
