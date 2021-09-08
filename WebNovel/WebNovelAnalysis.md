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
* Is it true that web novels are getting longer and longer?
* Is it true that web novel titles are longer than  the novels that are published by major publishers?
* Which genre has the longest title length on average?
* Are web novel titles on Syosetu.com, which does not shows story abstract by default, longer than platform that shows the story abstract?
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

* The average title length of web novels on Syosetu.com has been increasing over time
* Fantasy novels have longer titles than other genres on average
<br>
<br>

#### Comparison Between Two Web Novel Platforms

<div class='tableauPlaceholder' id='viz1630366441414' style='position: relative'><noscript><a href='#'><img alt='page4 (2) ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ja&#47;JapaneseWebNovel1&#47;page42&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='JapaneseWebNovel1&#47;page42' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ja&#47;JapaneseWebNovel1&#47;page42&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>    

In this part, I compared top web novels from Syosetu.com with web novels from another platform called Kakuyomu and light novels that are published by major publishers in Japan: <br>
<br>
**Syosetu.com**: The largest web novel platform in Japan that started in 2004. Its mobile user interface does not show the story abstract in the search result by default. The users are required to click a ‘read more’ button in order to see the story abstract and tags. <br>
**Kakuyomu**: A newer web novel platform in Japan that started in 2016. Unlike Syosetsu.com, Kakuyomu always shows the abstract and tags of the web novels in their search result.<br>
**Light novels**: Young adult fiction with anime-like graphics. The majority of the web novels that have been published and printed into printed novels are considered to be light novels.<br>

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

#### Weekly Viewers
Title length has a **statistically significant positive effect** on the number of unique viewers who have viewed the web novel in the past week. <br>
In the third model, the coefficient on title length is 6.328 while the coefficient on title length squared is -0.031. A positive coefficient on title length and a negative coefficient on the squared term means that the additional effect of increasing your title **diminishes** as the title gets longer and longer.<br>
The forth model with interaction terms shows how the effect of title length on the number of weekly viewers is different for each genre. The effect is the **largest on Fantasy novels**; increasing the title of a Fantasy novel by one Japanese character is expected to increase the estimated weekly viewers by 8.3. On the other hand, the effect on Other novels is not statistically significant, meaning that the effect is very small and we cannot reject the possibility that title length has no effect on the weekly viewers of Other novels.<br>
<br>
*The coefficient on title length in the forth model represents the effect of increasing title length by one character on the weekly viewers of Other novels.*<br>
*The coefficient on title length x Fantasy novels in the forth model represents the difference between the effect on Fantasy novels and the effect on Other novels.The effect of title length on the weekly viewers of Fantasy novels would be the sum of the coefficient on title length and the coefficient on title length x Fantasy.*<br>

#### Average Score


#### Number of Bookmarks

[Click here to view the Jupyter notebook for regression analysis](https://github.com/fangevalee/Portfolio/blob/6b05fbc6abf824dd1ded2be0ffdd20fae3d3c0d2/WebNovel/Web%20Novel%20Regression%20Analysis.ipynb)
## Conclusion
