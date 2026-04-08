| [home page](https://cmustudent.github.io/tswd-portfolio-templates/) | [data viz examples](dataviz-examples) | [critique by design](critique-by-design) | [final project I](final-project-part-one) | [final project II](final-project-part-two) | [final project III](final-project-part-three) |

My project will be about the impact of the transfer portal on women’s college basketball. The idea for the project came from this [article](https://herhoopstats.substack.com/p/breaking-down-the-transfer-portal) that does an analysis of transfer patterns among the high school class of 2019. I plan to do a similar analysis but it will be more comprehensive and include some additional elements. The main goal of this article is to provide information and highlight some interesting trends.

# Outline
- **Introduction:** This section will start with a picture of the UCLA women’s basketball team and a short description of how they won the most recent women’s college basketball championship this month and how they are an example of the evolving nature of the sport. The core group of players that played the vast majority of their games were 2 players recruited to UCLA from high school and 4 players who transferred to UCLA from other colleges. Then, the article will go briefly into the article layout. It will mention that you can skip to a specific section if you have existing women’s college basketball knowledge, as I see this article aimed at 2 audiences: 1) people who are interested in and knowledgeable about women’s college basketball and 2) those who are not.
- **What is the transfer portal?:** This section will provide some background information about collegiate transfer portal. It will also include some information about how it has changed over time. There will be a line chart that will have the season on the x-axis and the number of transferring athletes on the y-axis. It will include a vertical line indicating the year the rule change that created transfer portal was implemented. See the image below for an example.
<img width="750" height="500" alt="image" src="https://github.com/user-attachments/assets/bf3b4c53-7a34-4bc5-aa32-cc412e9fe8f2" />

- **Why do players transfer?:** This section will explain a few of the key reasons players transfer. I plan to show this primarily through a visualization like the one below with a series of icons, each representing a reason and some text further explaining the reason.
<img width="3506" height="1000" alt="image" src="https://github.com/user-attachments/assets/1a0ccf12-dbfc-40ff-85bb-d3789f4afe0a" />

- **Deep Dive into Elite Athletes:** This section will present the primary analysis of the article. It will look into two classes of athletes: one before and one after the start of the transfer portal. The high school graduating classes I am considering are 2013 or 2014 (pre-portal) and 2020, 2021, or 2022 (post-portal). The ultimate decision will depend on the data. Drawing from the original analysis article, I may make a visualization like this one. I will probably use different colors for the two different classes.
<img width="1726" height="1000" alt="image" src="https://github.com/user-attachments/assets/bc5aaa50-43e8-4441-9303-d39bdd435d39" />

- **Additional Analyses:** I am still trying to figure out what additional analyses I want to do, but here are some ideas:
  - Another visualization I might do is one that has 10 rows of 5 jerseys (similar to the previous visualization) each representing the starting lineup for the 10 teams that won the most recent championships and use two different colors to represent the athletes that were transfers and those that were original recruits.
  - Do transfers perform better at their new schools?
  - Clustering analyses to classify different athletes into different transfer profiles (i.e. elite performers going to teams that are more likely to win a championship, role players who want to get more playing time, etc.)
- **Conclusion:** This will provide some information about ideas for future analyses and links to other resources/analyses.

# The data
There are four primary data sources for this project:
- **[ESPN Sports Center NEXT 100](https://www.espn.com/high-school/girls-basketball/recruiting/rankings/scnext100girls/_/class/2026):** This is a list of the top 100 women’s high school basketball players ranked. I have created an R file that scrapes the tables for the 2013 – 2025 high school classes. The women in these tables will be the athletes I will track for the elite athlete analyses.
- **[wehoop](https://wehoop.sportsdataverse.org/index.html):** This is an R package that provides play-by-play and box score data for women’s college basketball. I will be using the box score data to get game and player records for the 2014 – 2026 seasons. 
- **[Sports Reference](https://www.sports-reference.com/cbb/)** I may gather advanced player and team statistics and information from this website. 
- **[Women’s Basketball Blog](https://wbbblog.com):** This website contains a lot of useful information about who transfers and for what reason. It also documents coaching changes which are a key factor in transfer decisions and is not reflected in the box score data.

I have already joined the ESPN SC NEXT 100, wehoop, and Sports Reference data in R. 

# Method and medium
I plan to use Shorthand. If I find there are limitations in Shorthand for the types of visualizations I want to do, I may use R or Python to generate the visualizations and then put them in Shorthand. For the analysis, I have been doing it in R because it builds on some initial work I did in R but I may switch to Python, which I am more proficient in if the analysis is more intensive.

## References
All referenced material is linked in the text above.

## AI acknowledgements
I did not use AI for this assignment.
