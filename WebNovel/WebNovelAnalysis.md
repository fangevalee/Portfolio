# Analysis on Japanese Web Novel Title Length

## Abstract
Web Novels in Japan are known to have long titles, and some people believe that longer titles lead to more clicks. I collected data from Syosetsu.com, the largest web novel platform in Japan, and used OLS regression to analyze title length’s effects on number of weekly viewers, average rating, number of bookmarks, and number of written reviews. The regression results show that longer titles have a positive effect on the number of bookmarks and written reviews a web novel receives. Title length might also have a positive effect on the number of weekly views and a negative effect on the rating of the novels.

## Introduction
#### What is a Web Novel?
A web novel is a work of fiction that is published on the Internet. Web novels are written mainly by indie writers and published in a serialized format, and most of them are available to readers free of charge. An example of an English web novel platform is Wattpad. Many web novels have become published books during the past decade, and some famous works have been adapted into anime, drama, and movies.
#### What is interesting about web novel in Japan?
One interesting fact about web novels in Japan is that they are known for their long titles, and many people have noticed that web novel titles are getting longer and longer. Some people claim that longer titles can lead to more views because longer titles give the readers more context about the plot. Since some platforms do not show the abstract of the novel in the search result by default, titles become the only way for writers to showcase what their stories are about. 

## Objectives
The goal of this project is to answer the folling questions using data:<br>
* Is it true that web novels are getting longer and longer?
* Is it true that web novel titles are longer than  the novels that are published by major publishers?
* Which genre has the longest title length on average?
* Are web novel titles on Syosetu.com, which does not shows story abstract by default, longer than platform that shows the story abstract?
* Is there a significant correlation between title length and number of views?
* Is there a significant correlation between title length and number of readers (number of users who have bookmarked the work)?
* Is there a significant correlation between title length and the average rating?
* Is there a significant correlation between title length and number of written reviews for the web novel?

## About the Dataset
The dataset was scraped from Syosetsu.com using the Selenium package in Python. [Click here to view the codes for web scraping and data cleaning.](https://github.com/fangevalee/Portfolio/blob/73f9b22f294df776250fe9fa4c6f3c52fe65fb6d/WebNovel/Web%20Novel%20Web%20Scraping%20with%20Selenium.ipynb)


## [Data Visualization](https://public.tableau.com/views/JapaneseWebNovel2/Dashboard2?:language=en-US&:display_count=n&:origin=viz_share_link)


## [Regression analysis](https://github.com/fangevalee/Portfolio/blob/94a72217387f805eff18f29bd42f0c5fb78a381e/WebNovel/Web%20Novel%20Regression%20Analysis.ipynb)


## Conclusion
