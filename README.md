# Analysis of Wikipedia Articles about U.S. Cities by State

## Goal of the Project

The primary goal of this project is to explore the concept of bias in data by analyzing Wikipedia articles about U.S. cities. The project combines datasets from Wikipedia and the U.S. Census Bureau to calculate two key metrics on a state-by-state and divisional basis:
1. Total articles per capita
2. High-quality articles per capita

High-quality articles are considered to be those that ORES (Objective Revision Evaluation Service) predicted to be either "FA" (featured article) or "GA" (good article).

## License and Terms

The source data comes from Wikipedia and the U.S. Census Bureau. Wikipedia data is licensed under the [CC-BY-SA](https://creativecommons.org/licenses/by-sa/3.0/) license. The terms of use for the Wikimedia Foundation REST API can be found [here](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions).

## Relevant API Documentation

- [Wikipedia API](https://www.mediawiki.org/wiki/API:Main_page)
- [ORES API](https://www.mediawiki.org/wiki/ORES)

## Data Files

### Intermediary Data Files

- `us_cities_by_state_SEPT.2023.csv`: Contains the list of Wikipedia articles about U.S. cities by state.
- `NST-EST2022-ALLDATA.csv`: Contains estimated populations of all U.S. states for 2022.
- `US States by Region - US Census Bureau - Sheet1.csv`: Contains the states in each U.S. Census regional division.

### Final Output Files

- `merged_df_final.csv`: Contains the merged data with the following fields:
  - `state`: The U.S. state
  - `regional_division`: The Census regional division of the state
  - `population`: The estimated population of the state for 2022
  - `article_title`: Title of the Wikipedia article
  - `revision_id`: Revision ID of the article
  - `article_quality`: ORES predicted quality of the article

## Known Issues and Special Considerations

1. The Wikipedia data may have inconsistencies such as duplicate articles or missing data points.
2. The ORES API occasionally may not return a quality score for an article.

## Additional Resources

- [U.S. Census Bureau Population Data](https://www.census.gov/programs-surveys/popest.html)
- [Wikipedia Content Assessment](https://en.wikipedia.org/wiki/Wikipedia:Content_assessment)
