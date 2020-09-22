# NFL_Rookie_Running_Back_Yards
Created a Linear Regression Model to Predict Total Yards Rushing and Receiving of Rookie NFL Running Backs
# **Metis Project 2 - Summer 2020**

## About:

This project predicts the total yards of scrimmage (rushing and receiving) of running backs during their first season in the NFL.

I wanted to approach this prediction in a way that isn't typically used: simplify a model by just looking at the results of a prospective player's combine stats, height, weight, and draft pick number. Many NFL predictions take into consideration a multitude of other factors such as college conference, yards of scrimmage in college, NFL draft team, etc., however the results of those predictions are not always very accurate. 

Consider my inspiration for this project: Phillip Lindsay, a running back for the Denver Broncos who was an Undrafted Free Agent, not really even expected to play as a running back his rookie year in the NFL. He then shocked everyone by accumulating 1278 total yards of scrimmage and being selected to the Pro Bowl his rookie year.

This led me to thinking that maybe current NFL projections of rookie running backs are too specific, maybe it would be better to simplify a model by only taking into consideration factors that are standardized across the board (like height, weight, and combine stats). Factors such as college stats and college conference are really dependent on how a player's team is, not necessarily on the athletic capabilities of that athlete. By creating a model with just a prospective player's standardized statistics (combine results, height, weight, and draft pick number) that don’t depend on the college team or conference that a player played for, my hope was to create a model that would predict an athlete's ability without over-fitting a model with non-standardized information. 

My hope is that this simplified model of projecting NFL rookie running back success as measured by total yards of scrimmage will help to make more accurate draft decisions of NFL teams seeking new running backs. Additionally, this model can be used to predict whether a rookie running back would be a good choice for sports betting purposes.

## Process:

Using BeautifulSoup, I scraped data from [Pro Football Reference.com](https://www.pro-football-reference.com/) to get information on 333 Running Backs who play(ed) in the NFL and had NFL Combine Results from years 2000 to 2020.

After creating a dummy model, I found that my data was highly skewed to the right, the residual plot was not random, and the QQ plot was not very straight, which indicated the need for a Logarithmic transformation of my target variable. After the log transformation, dropping multicollinear features, and feature engineering a weight-to-height ratio, I increased my R-squared value from 0.325 to 0.341. This process also allowed for a more normal distribution, a more random residual plot, and a straighter QQ plot.

## Results:

When applying my model to my inspiration for this project, Phillip Lindsay, my model predicted he would have 209 total yards his rookie year. In actuality, he ran 1278 yards, so the residual for my model was 1069. Considering that most models predicted him to have 0 yards and not even play as a Running Back his rookie season, my model performed better than expected.

## Files:

In this project, you will find the code files I used to scrape the data, clean the data, and create a Linear Regression model on the data. You will also find a PDF of the Google Slides I presented to my class.

### Slideshow PDF:

- Lindsay_project_3.pdf

### Code Files:

1. Code file for scraping data and creating initial DataFrame:

Proj2DataFrame.ipynb

2. Code file for EDA and Linear Regression Modeling:

EDA_and_modelling.ipynb

## Data:

[Pro Football Reference](https://www.pro-football-reference.com/)

## Skills:

- Web scraping using BeautifulSoup
- Regex
- Pandas, Numpy
- Matplotlib and seaborn visualizations
- Stats & sklearn
- Logarithmic transformations

## Analysis:

- Exploratory Data Analysis
- Linear Regression (analyzed with Oridinary Least Squares (OLS), basic linear regression, LASSO Regularization, and Ridge Regularization).
- Verified model with cross validation
