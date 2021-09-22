# TacoChacos
**Steps Followed for Movie Recommender System**:

**1.	Collecting Movie Data: (Scraping.ipynb)**

   	1. Here we used python library Beautiful Soup by using loop for Different Genres limiting Data to 140000 rows.

	2. We Removed rows with Null Values and Filtered Duplicate Rows using Movie Name as Reference.

**2.	Model Building: (Model.ipynb)**

	1. After going through different tutorials, we found that with from the Data set we scraped, we can build Content Based Recommender System Based on NLP

	2. We Imported Necessary Libraries and data (with Necessary Columns) set we scraped

	3. The method we followed is based on Similarity of Text Corpus where we vectorize the text and find similarity by using methods like Cosine Similarity, TF-IDF

	4. We Extracted all the Keywords row wise from Columns [director, stars, plot, genres] using NLTK Library with method word_tokenize  where movie name is index for the data frame.

	5. We also done some of the text pre-processing like lemmatization and removing other stop words.

    6. We Combined all the extracted keywords in single column with movie name as index

	7. We then used CountVectorizer to Vectorize each corpus in data frame.

	8. We saved movie name list and CountVectorizer in pickle format and uploaded to GitHub.

**3.	Colab API : (API. ipynb)**

	1. Here we loaded the Pickle files from GitHub and other necessary libraries for Flask API

	2. We defined a function that takes input as [movie name,movie_name_list,Vector_Matrix]  and predicts top 10 similar movies based on cosine similarity of vector[ corpus ]
