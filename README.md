# Scalable-Summarization
Integrated Huggingface Summarization with Torch Serve. Combined other extractive methods such as Lex Ranker, TextRanker. Also have included OpenAI summarization. It also includes keyword generation for articles with query based content filtering using Cosine Similarity. Made this project for [Schlumberger's New Year Hackathon](https://unstop.com/hackathon/schlumbergers-new-year-hackathon-shaastra-2023-indian-institute-of-technology-iit-madras-572825)

# Requirement:

```
bs4
cloudscraper
torchserve
torch
scikit-learn
keybert
trasnformers
sentence_transformers
openai
fastapi
sumy
uvicorn

```

# Features:

- When a topic is searched for it scrapes from a set of websites and shows the articles that appeared in each of the website. It makes use of multi-threading for scraping

- Along with articles user can choose summary for each article from which model such as OpenAI, T5, Text Ranker, Lex Ranker.

- It also shows summarization for combined articles using any of the mentioned models.

- It generates keywords for each article using T5 as the feature-extractor. 

- It has option to search the articles using a query by making use of Cosine Similarity between the query vector and article content vector

# Architecture:
![SHAASTRA-ARTICLE drawio](https://user-images.githubusercontent.com/57902078/215549713-f48c4120-655a-46a9-b502-22a503316c95.png)

![SHAASTRA-ARTICLE-TECH drawio](https://user-images.githubusercontent.com/57902078/215549728-f813145b-b72d-4f89-8c73-12b60a8bce33.png)


# Deploy:

1) cd server
2) First save t5 pretrained model files of ```AutoModelForSeq2SeqLM``` (.bin and config.json) inside ```model``` folder
3) Run the torch serve model archiver using this command 
```torch-model-archiver --model-name "t5" --version 1.0 --serialized-file model/pytorch_model.bin --extra-files "model/config.json" --handler handler.py ```
4) Store the .mar files inside ```model_store``` folder using ```mv t5.mar model_store/t5.mar```
5) Start the torch server using ```torchserve --start --model-store model_store --models t5=t5.mar```
6) Check the serve health by pinging at port 8080. ```curl http://localhost:8080/ping```
7) Stop the serve when required using ```torchserve --stop```

8) Start Fastapi server using ```python app.py```
9) Open index.html in website folder ot view the website.


# Demo:

Watch recorded demo [here](https://drive.google.com/file/d/14tntrE3LSb9CngHxyfdgoHXkG0ah5M0q/view?usp=share_link).

![Youtube Video](https://youtu.be/ELu_LsWmmas)

![Screenshot from 2023-01-27 01-11-57](https://user-images.githubusercontent.com/57902078/215547512-6747b7bb-9443-4044-be01-7ec8fd3481dc.png)

![Screenshot from 2023-01-27 01-14-08](https://user-images.githubusercontent.com/57902078/215549165-f0c135dc-60d1-4b21-b131-31cc2cf6e44b.png)


# Contributors:


<a href = "https://github.com/FrozenWolf-Cyber/Scalable-Summarization)/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo = GitHub_username/repository_name"/>
</a>
