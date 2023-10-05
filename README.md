# SupQA
A dataset for subjective question answering on products (SubjPQA). The satisfactory answer should contain objective facts and various subjective viewpoints among user review or community answers.
- telescope.json is a sample in SupQA dataset.
- The full dataset will release soon.


## Data Intriduction

Each example contains the following fields:

- `category`: The general product category 
- `ASIN`: The Amazon product identifier
- `question`: The question asked about the product
- `q_sum`: A short summary of the question
- `multi_answers`: Multiple answers to the question provided by different users in community question answering part
- `bm25_score_answers`: The BM25 relevance score of each answer
- `polarity_answers`: The sentiment polarity (positive/negative/neutral) of each answer
- `objective_answer`: The objective answer to the question
- `subjective_answer`: The subjective summary of the various answers/reviews
- `use_template`: A template for generating the subjective answer summary
- `product_info`: Additional structured info about the product
  - `product_title`
  - `description`
  - `feature_bullets` 
  - `attributes`
  - ...
- `product_reviews`: Text reviews for the product
- `question_length`: Number of characters in the question
- `objective_answer_length`: Length of characters in the objective answer
- `subjective_answer_length`: Length of characters in the subjective answer 
- `review_length`: Length of characters in each review
- `product_reviews_scores`: Score/rating for each review
- `sentiment_scores`: Sentiment score for each review
- `knowledge`: Relevant commonsense knowledge for each question from LLMs

## Usage

This dataset can be used to train SubjPQA models to answer product questions by incorporating multiple answers, product info, and reviews.

The `objective_answer` provides the ground truth answer to train answer generation. 

The `subjective_answer` summarizes multiple opinions, and can be used to train abstractive summarization for multi-answer questions.

The additional context such as `product_info` and `reviews` allows models to incorporate external evidence.

The variety of scores and metrics allow for different training objectives, such as optimizing for relevance, accuracy, and sentiment.
