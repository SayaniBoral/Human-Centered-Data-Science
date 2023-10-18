#  Wikipedia scoring of article content of all US cities

## Project Goal
This notebook has been used to publish a single dataset of CSV format that helps in analyzing the following:
- The US states with the greatest and least coverage of cities on Wikipedia compared to their population.
- The US states with the highest and lowest proportion of high quality articles about cities.
- A ranking of US geographic regions by articles-per-person and proportion of high quality articles.


It merges dataset from Wikipedia article about the cities,ORES score of the article, population data of the state and regional division data that the state belongs to.


## Source of data
It merges dataset from Wikipedia article about the cities,ORES score of the article, population data of the state and regional division data that the state belongs to.


## License
This code example was developed by Dr. David W. McDonald for use in DATA 512, a course in the UW MS Data Science degree program. This code is provided under the [Creative Commons](https://creativecommons.org) [CC-BY license](https://creativecommons.org/licenses/by/4.0/). Revision 1.2 - August 14, 2023


## Structure of the repository

- Final_outputs - Contains the final CSV : wp_scored_city_articles_by_state 
- notebooks - Comtains the notebook code
- sources - Contains raw data files which are the data sources
- staging_outputs - Contains any intermediary output files that was staged after transformation step like joining/merging

## Research Implications

__What biases did you expect to find in the data (before you started working with it), and why?__
Before I started exploring the data, one of my assumptions was that popular cities around US (like NYC, San Francisco, Boston, Chicago, etc) will have articles with higher ORES rating. My rationale for this assumption there is likeliness of more contributions made to Wiki for these popular cities. As a Wiki consumer myself, I will go to Wiki to learn about popular cities before visiting them for example. Hence popularity of a city can lead to more information added to Wiki and hence qualifies for higher rating - thats one of my underlying biases.

The second bias is related to economy of a city. Cities that contribute to the economy of a state or the overall country are usually more populated. People settle there for jobs. That may lead to more contributirs adding to wiki.


__What (potential) sources of bias did you discover in the course of your data processing and analysis?__
I was surprised to see California as one of the bottom 10 states by articles per capita. Being the 2nd lagest state in US , I was assuming it will have good coverage in terms of articles for its cities. 
Population demographics seems to play a part in the article coverage per capita. The top 10 states by article coverage per capita have predominantly English speaking white population. This can be a contributing factor to more article coverage.





__What might your results suggest about (English) Wikipedia as a data source?__


__Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might create biased or misleading results, due to the inherent gaps and limitations of the data?__
