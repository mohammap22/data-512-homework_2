# Analysis of Wikipedia Articles about U.S. Cities by State

## Goals 

The goal of this project is to analyze Wikipedia articles and try to determine if there was bias in them. The project combines data from Wikipedia and the U.S. Census Bureau to calculate total articles per capita and high-quality articles per capita, our key metrics.  We determine an article to be "high quality" based on the ORES (Objective Revision Evaluation Service) score. 

## Relevant API Documentation

- [Wikipedia API](https://www.mediawiki.org/wiki/API:Main_page)
- [ORES API](https://www.mediawiki.org/wiki/ORES)

## Data Files

### Pre-Loaded Data Files

- `us_cities_by_state_SEPT.2023.csv`: list of Wikipedia articles about U.S. cities
- `NST-EST2022-ALLDATA.csv`: estimated populations of all U.S. states for 2022
- `US States by Region - US Census Bureau - Sheet1.csv`:  states in each U.S. Census regional division

### Final Output Files

- `merged_df_final.csv`: Contains merged data with the fields:
  - `state`: The U.S. state
  - `regional_division`: regional division of the state
  - `population`: estimated population of the state for 2022
  - `article_title`: title of the wiki article
  - `revision_id`: the Wikipedia revision ID of the article
  - `article_quality`: ORES predicted quality of the article

## Known Issues and Special Considerations

1. The Wikipedia data may include duplicate articles or missing rows.
2. It takes a significant amount of time to load the ORES quality data for the entire dataset.

## Additional Resources

- [U.S. Census Bureau Population Data](https://www.census.gov/programs-surveys/popest.html)
- [Wikipedia Content Assessment](https://en.wikipedia.org/wiki/Wikipedia:Content_assessment)

## Research Implications

### General Findings
Upon looking at the different tables, we can start seeing a pattern. It looks like smaller states, like Vermont or Maine, tend to have both higher-quality Wikipedia articles and more articles per capita. While the larger states, Like California or Nevada, have worse articles. By smaller I actually mean in land mass and not population. I expected states like California to have higher article quality, but I also expected smaller states to have high quality as well. I learned how long API calls take, and in order to do this project, one needs to be prepared to wait near **DAYS** for the data. 
### Wikipedia as a Data Source
Wikipedia, at its core, is a flawed data source. The people creating and modifying these articles are not trained professionals or experts. They are simply people online. Thus, running an analysis on articles will always be difficult, due to the fact that one article may be written and edited by hundreds if not thousands of people. With that being said, acquiring Wikipedia data through their API is not very difficult, and is well documented. Meaning it is a good place to practice using API calls and running analysis. 

### Biases and Accounting for Them
As mentioned before, we have no idea who edits and writes these articles on Wikipedia, thus it is hard to run an analysis on them. But we can attempt to make some deductions. States like Vermont having more articles per capita could be because the state is small, meaning there are not a lot of towns to create documents on. This means these documents are probably high quality. Also, since Vermont is an **old state** there is a lot of history behind it, leading to better articles. To account for these biases, a researcher could attempt to take into account the number of revisions to an article. This could help explain the differences in ORES grades. 


