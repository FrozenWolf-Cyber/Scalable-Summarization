# Scalable-Summarization
Integrated Huggingface Summarization with Torch Serve. Combined other extractive methods such as Lex Ranker, TextRanker. Also have included OpenAI summarization. It also includes keyword generation for articles with query based content filtering using Cosine Similarity. Made this project for [Schlumberger's New Year Hackathon](https://unstop.com/hackathon/schlumbergers-new-year-hackathon-shaastra-2023-indian-institute-of-technology-iit-madras-572825)

# Features:

- When a topic is searched for it scrapes from a set of websites and shows the articles that appeared in each of the website. It makes use of multi-threading for scraping

- Along with articles user can choose summary for each article from which model such as OpenAI, T5, Text Ranker, Lex Ranker.

- It also shows summarization for combined articles using any of the mentioned models.

- It generates keywords for each article using T5 as the feature-extractor. 

- It has option to search the articles using a query by making use of Cosine Similarity between the query vector and article content vector

# Demo:

![Screenshot from 2023-01-27 01-11-57](https://user-images.githubusercontent.com/57902078/215547512-6747b7bb-9443-4044-be01-7ec8fd3481dc.png)

![Screenshot from 2023-01-27 01-14-08](https://user-images.githubusercontent.com/57902078/215549165-f0c135dc-60d1-4b21-b131-31cc2cf6e44b.png)
