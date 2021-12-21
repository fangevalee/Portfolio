# Analysis on Japanese Web Novel

## Introduction
#### What is a Web Novel?
A web novel is a work of fiction published on the Internet. Web novels are written mainly by indie writers and published in a serialized format, and most of them are available to readers free of charge. An example of an English web novel platform is Wattpad. Many web novels have become published books during the past decade, and some famous works have been adapted into anime, drama, and movies.<br>
One interesting fact about web novels in Japan is that they are known for their long titles. While many people claim that they don’t like the long titles of web novels, **some people argue that longer titles can lead to more views because longer titles give the readers more context about the plot**. In this project, I will use regression analysis to estimate the effect of title length and verify if it is true that longer titles would lead to more readers.<br>

## About the Dataset
The dataset was collected from Syosetsu.com, Japan's largest web novel platform, using the Selenium package in Python on October 28, 2021. The dataset contains all 400,373 serialized web novels published from 2007 to 2020.<br>

[Click here to view the Jupyter notebook for web scraping and data cleaning.](https://github.com/fangevalee/Portfolio/blob/2dd69babdb34fc252e3a64782892da3cd874637d/WebNovel/Web%20scraping%20with%20Selenium.ipynb)

[Click here to view the Tableau dashboard of the **older version** of the dataset.(I will make one with this new dataset soon.)](https://public.tableau.com/app/profile/eva.lee3016/viz/AnalysisonJapaneseWebNovelTitles/page1)

## [Regression Analysis on Title Length's Impact](https://github.com/fangevalee/Portfolio/blob/24b47c77d160fa8c869c0edf64603aab218c2fa9/WebNovel/Analysis%20on%20Web%20Novel%20Data.ipynb)

### Robust Linear Regression with Interaction terms
#### Estimated Effect of Title Length by Genres
| Genre  | Number of Bookmarks/Readers | Average Rating |
| ------------- | ------------- |------------- |
| Fantasy  | 2.012***  | -0.002*** |
| Literature  | 1.726***  | -0.003*** |
| Romance  | 2.400***  | 0.001 |
| Sci-fi  | 2.616***  | 0.000 |
| Other  | 0.021  | 0.001* |

* Title length is positively correlated with the number of bookmarks for Fantasy, Literature, Romance, and Sci-fi novels, but it does not have a statistically significant effect on Other novels. <br>
* Title length is negatively correlated with the average rating for Fantasy and Literature novels. It does not have a statistically significant effect on Romance and Sci-fi novels, and it is positively correlated with the average rating for Other novels.<br>

### Quantile regression
#### Estimated Effect of Title Length on Bookmarks
![image](https://github.com/fangevalee/Portfolio/blob/66e0c5f4091fc10f223efff81f67ad89fe15ea21/WebNovel/plot1.png)<br>
Title length is positively correlated with the number of bookmarks. <br>The estimated effect of title length on the number of bookmarks is close to 0 for novels with fewer bookmarks, and the estimated effect is larger for popular novels with many bookmarks.

#### Estimated Effect of Title Length on Average Rating
![image](https://github.com/fangevalee/Portfolio/blob/66e0c5f4091fc10f223efff81f67ad89fe15ea21/WebNovel/plot2.png)<br>
Title length is negatively correlated with the average rating. <br>The estimated effect of title length on the average rating is smaller for novels whose rating is about the median, and the estimated effect is larger for novels with very good or bad ratings.

## K-NN and Logistic Regression
Most Web novels are published in a serialized format, and it is common for writers to stop writing in the middle of the story. The majority of ongoing novels on Syosetsu.com hasn't had any new update for over a year! In this part, I used K Nearest Neighbor and Logistic Regression to classify the novels with no update for over a year. The best accuracy score I got was 0.91454.

[Click here to view the Jupyter notebook for regression analysis and machine learning.](https://github.com/fangevalee/Portfolio/blob/24b47c77d160fa8c869c0edf64603aab218c2fa9/WebNovel/Analysis%20on%20Web%20Novel%20Data.ipynb)
