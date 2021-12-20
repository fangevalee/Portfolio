# Analysis on Japanese Web Novel

## Part 1: Regrssion Analysis on Title Length

## Introduction
#### What is a Web Novel?
A web novel is a work of fiction that is published on the Internet. Web novels are written mainly by indie writers and published in a serialized format, and most of them are available to readers free of charge. An example of an English web novel platform is Wattpad. Many web novels have become published books during the past decade, and some famous works have been adapted into anime, drama, and movies.
#### What is interesting about web novel in Japan?
One interesting fact about web novels in Japan is that they are known for their long titles, and many people have noticed that web novel titles are getting longer and longer. Some people claim that longer titles can lead to more views because longer titles give the readers more context about the plot. Since some platforms do not show the abstract of the novel in the search result by default, titles become the only way for writers to showcase what their stories are about. 

## About the Dataset
The dataset was scraped from Syosetsu.com using the Selenium package in Python.<br>
Syosetu.com is the largest web novel platform in Japan. It has over 890,000 written works and 2,000,000 users, and many of its famous works have had manga and anime adaptations. The dataset contains all web novels that were published from 2007 to 2020.<br>

[Click here to view the Jupyter notebook for web scraping and data cleaning.](https://github.com/fangevalee/Portfolio/blob/2dd69babdb34fc252e3a64782892da3cd874637d/WebNovel/Web%20scraping%20with%20Selenium.ipynb)

## Key Finding
#### Estimated effect of title length on bookmarks
1. Title length has larger impacts on bookmarks for Sci-fi and literature novels, but it does not have a statistically significant effect on Other novels.
2. Title length has little or no effect on web novels with a small number of bookmarks. The estimated impact of title length on bookmarks is larger for the popular novels with many bookmarks.

#### Estimated effect of title length on the average score
1. Title length negatively impacts the average rating of Fantasy and literature novels while it does not have a statistically significant effect on all other genres
2. Title length has a negative effect on the average score of a web novel. The estimated impact of title length is stronger for novels with very bad ratings and novels with a good rating, and it is smaller for the novels that are in between.

[Click here to view the Jupyter notebook for regression analysis.](https://github.com/fangevalee/Portfolio/blob/2dd69babdb34fc252e3a64782892da3cd874637d/WebNovel/Analysis%20on%20Web%20Novel%20Data.ipynb)
