# Analysis on Japanese Web Novel Title Length

## Abstract
Web Novels in Japan are known to have long titles. While some people believe that longer titles lead to more clicks, there are also readers who claim that web novels with shorter titles are better than the ones with very long titles.I collected data from Syosetsu.com, the largest web novel platform in Japan, and used OLS regression to analyze title length’s effects on the number of weekly viewers, average rating, number of bookmarks, and number of written reviews. The regression results show that longer titles positively affect the number of bookmarks and written reviews a web novel receives. Title length might also have a positive effect on the number of weekly views and a negative impact on the rating of the web novels.

## Introduction
#### What is a Web Novel?
A web novel is a work of fiction that is published on the Internet. Web novels are written mainly by indie writers and published in a serialized format, and most of them are available to readers free of charge. An example of an English web novel platform is Wattpad. Many web novels have become published books during the past decade, and some famous works have been adapted into anime, drama, and movies.
#### What is interesting about web novel in Japan?
One interesting fact about web novels in Japan is that they are known for their long titles, and many people have noticed that web novel titles are getting longer and longer. Some people claim that longer titles can lead to more views because longer titles give the readers more context about the plot. Since some platforms do not show the abstract of the novel in the search result by default, titles become the only way for writers to showcase what their stories are about. 

## Objectives
The goal of this project is to answer the folling questions using data:<br>
* Is it true that web novel titles are getting longer and longer?
* Is it true that web novel titles are longer than the non-web novels that are published by major publishers?
* Which genre has the longest title length on average?
* Are web novel titles on Syosetu.com, which does not shows story abstract by default, longer than another platform that shows the story abstract?
* Is there a significant correlation between title length and number of views?
* Is there a significant correlation between title length and number of readers (number of users who have bookmarked the work)?
* Is there a significant correlation between title length and the average rating?
* Is there a significant correlation between title length and number of written reviews for the web novel?

## About the Dataset
The dataset was scraped from Syosetsu.com using the Selenium package in Python.<br>
Syosetu.com is the largest web novel platform in Japan. It has over 890,000 written works and 2,000,000 users, and many of its famous works have had manga and anime adaptations. The dataset contains 51940 popular web novels that were published on Syosetu.com between 2017 and July 2021. <br>

[Click here to view the Jupyter notebook for web scraping and data cleaning.](https://github.com/fangevalee/Portfolio/blob/73f9b22f294df776250fe9fa4c6f3c52fe65fb6d/WebNovel/Web%20Novel%20Web%20Scraping%20with%20Selenium.ipynb)

## Data Visualization

#### Web Novels on Syosetu.com

<div class='tableauPlaceholder' id='viz1630298726443' style='position: relative'><noscript><a href='#'><img alt='page2 (2) ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ja&#47;JapaneseWebNovel2&#47;page22&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='JapaneseWebNovel2&#47;page22' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ja&#47;JapaneseWebNovel2&#47;page22&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>
<br>

**Key Findings:**
* The average title length of web novels on Syosetu.com has been increasing over time
* Fantasy novels have longer titles than other genres on average
<br>

#### Comparison Between Two Web Novel Platforms

<div class='tableauPlaceholder' id='viz1630366441414' style='position: relative'><noscript><a href='#'><img alt='page4 (2) ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ja&#47;JapaneseWebNovel1&#47;page42&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='JapaneseWebNovel1&#47;page42' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ja&#47;JapaneseWebNovel1&#47;page42&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>    
<br>
In this part, I compared top web novels from Syosetu.com with web novels from another platform called Kakuyomu and light novels that are published by major publishers in Japan: <br>

**Syosetu.com**: The largest web novel platform in Japan that started in 2004. Its mobile user interface does not show the story abstract in the search result by default. The users are required to click a ‘read more’ button in order to see the story abstract and tags. <br>
**Kakuyomu**: A newer web novel platform in Japan that started in 2016. Unlike Syosetsu.com, Kakuyomu always shows the abstract and tags of the web novels in their search result.<br>
**Light novels**: Young adult fiction with anime-like graphics that are traditionally published by major publishers. The majority of the web novels that have been published and printed into printed novels are considered to be light novels.<br>

**Key Findings:**
* The average title lengths have been growing over time on all platforms.
* The average title length of web novels is longer than the average title length of all published light novels
* Web novels on Syosetu.com have a longer average title than the ones on Kakuyomu for all genres.

[Click here to view the full interactive Tableau dashboard.](https://public.tableau.com/views/AnalysisonJapaneseWebNovelTitles/page1?:language=en-US&:display_count=n&:origin=viz_share_link)

## Regression analysis

I used Robust linear regression models to estimate title length’s effect on the weekly viewers, average score, and the number of bookmarks. Each regression table contains the result of 4 regression models:<br>
1. Simple linear regression of the outcome variable (which is weekly viewers, average score, or number of bookmarks) on title length.
2. Multiple linear regression of the outcome variable on title length, genre, published year, number of parts, whether or not the work is completed, and whether or not the work is an ongoing novel with no update for over 6 months.
3. Multiple linear regression of the outcome variable on title length, **title length squared**, genre, published year, number of parts, whether or not the work is completed, and whether or not the work is an ongoing novel with no update for over 6 months.
4. Multiple linear regression of the outcome variable on title length, **title length squared**, genre, published year, number of parts, whether or not the work is completed, whether or not the work is an ongoing novel with no update for over 6 months, and **interaction terms between the genre and title length**.

### Regression result Of Model #3: 

| Independent Variables | Weekly Viewers | Average Score | Number of Bookmarks |
| ------------- | ------------- | ------------- | ------------- |
| Intercept | 151.175 | 8.46229*** | -330.036*** |
| Title_Length | 6.328*** | -0.00346*** | 9.725*** |
| Title_length_squared | -0.031*** | 0.00004*** | -0.036*** |

#### Interpretation:<br>

Outcome Variable | Estimated effect on the outcome variable when the title length increase by one
------------ | -------------
Weekly Viewers | 6.328 - 0.031 × Title Length
Average Score | -0.00346 + 0.00004 × Title Length
Number of Bookmarks | 9.725 - 0.036 × Title Length

### Regression result Of Model #4: 

| Independent Variables | Weekly Viewers | Average Score | Number of Bookmarks |
| ------------- | ------------- | ------------- | ------------- |
| Intercept | 252.979 | 8.49075*** | -262.895*** |
| Title_Length | -4.624 | -0.00688*** | 2.544*** |
| Title_length_squared | 0.089 | 0.00008** | -0.027 |
| Fantasy × Title Length | 12.148** | 0.00252 | 15.009*** |
| Literature × Title Length | 13.308** | 0.00397 | 14.419*** |
| Romance × Title Length | 11.544** | 0.00557** | 20.979*** |
| Sci-fi × Title Length | 13.186** | 0.00542 | 31.491*** |
| Fantasy × Title Length Squared | -0.124 | -0.00003 | -0.072*** |
| Literature × Title Length Squared | -0.180* | -0.00007 | -0.106*** |
| Romance × Title Length Squared | -0.137 | -0.00006 | -0.167*** |
| Sci-fi × Title Length Squared | -0.170 | -0.00005 | -0.265*** |


#### Interpretation:<br>
Estimated effect on the outcome variable when the title length increase by one for each genre:

| Genre | Weekly Viewers | Average Score | Number of Bookmarks |
| ------------- | ------------- | ------------- | ------------- |
| Fantasy  | 7.524 - 0.035 × Title Length  | -0.00436 + 0.00005 × Title Length | 17.553 - 0.099 × Title Length |
| Literature  | 8.684 - 0.091 × Title Length  | -0.00291 + 0.00001 × Title Length | 16.963 - 0.133 × Title Length |
| Romance  | 6.920 - 0.048 × Title Length  | -0.00131 - 0.00002 × Title Length | 23.523 - 0.194 × Title Length |
| Sci-fi  | 8.562 - 0.081 × Title Length  | -0.00146 + 0.00003 × Title Length | 34.035 - 0.292 × Title Length |
| Others  | -4.624 + 0.089 × Title Length  | -0.00688 + 0.00008 × Title Length | 2.544 - 0.027 × Title Length |

### Conclusion
According to the regression results, the title length of a web novel has a positive effect on weekly views, a positive effect on the number of bookmarks, and a negative effect on the average rating. These effects diminish as the title length increases. (i.g. The effect of increasing title length from 1 character long to 2 characters is larger than the effect of increasing title length from 99 to 100.)

[Click here to view the full regression results in Jupyter notebook](https://github.com/fangevalee/Portfolio/blob/18e80710dc9a78dcf875dc9d4cfddb02ed6a8c00/WebNovel/Web%20Novel%20Regression%20Analysis.ipynb)
