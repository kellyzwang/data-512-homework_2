# data-512-homework_2

HW2: Considering Bias in Data

### Project Goal

This repository explores the concept of bias in data using Wikipedia articles, considering articles on political figures from different countries, combines a dataset of Wikipedia articles with a dataset of country populations, and uses a machine learning service called ORES to estimate the quality of each article.

An analysis of how the coverage of politicians on Wikipedia and the quality of articles about politicians varies among countries is performed and consist of a series of tables that show:

- The countries with the greatest and least coverage of politicians on Wikipedia compared to their population.
- The countries with the highest and lowest proportion of high quality articles about politicians.
- A ranking of geographic regions by articles-per-person and proportion of high quality articles.


### License

The source data and code for this dataset is licensed under:
- [Creative Commons Attribution-ShareAlike 3.0 (CC-BY-SA 3.0)](https://creativecommons.org/licenses/by-sa/3.0/deed.en)


### Final Output Filenames and Directory Structure

```
├── output
|   └── Article_Quality_Predictions_data.csv
|   └── wp_countries-no_match.txt
|   └── wp_politicians_by_country.csv
├── source_data
|   └── politicians_by_country_AUG.2024.csv
|   └── population_by_country_AUG.2024.csv
├── LICENSE
├── README.md
├── analysis.ipynb
```


### Description of Source Data and Output Files

##### Source data
**politicians_by_country.AUG.2024.csv**:
The Wikipedia [Category:Politicians](https://en.wikipedia.org/wiki/Category:Politicians_by_nationality) by nationality was crawled to generate a list of Wikipedia article pages about politicians from a wide range of countries.

**population_by_country_AUG.2024.csv**: This dataset was downloaded from the [world population data sheet](https://www.prb.org/international/indicator/population/table/) published by the Population Reference Bureau. The data contains rows that provide cumulative regional population counts. These rows are distinguished by having ALL CAPS values in the 'geography' field (e.g. AFRICA, OCEANIA).

##### Output files

**Article_Quality_Predictions_data.csv**:
This dataset contains predicted quality scores for each article in the Wikipedia dataset using a machine learning system called [ORES](https://www.mediawiki.org/wiki/ORES). ORES is a machine learning tool that can provide estimates of Wikipedia article quality. The article quality estimates are, from best to worst:
1. FA - Featured article
2. GA - Good article (also known as A-Class)
3. B - B-Class article
4. C - C-Class article
5. Start - Start-class article
6. Stub - Stub-class article

**wp_countries-no_match.txt**: Countries for which there are no matches when combining the wikipedia data (Article_Quality_Predictions_data.csv) and population data (population_by_country_AUG.2024.csv) are stored in this txt file.


**wp_politicians_by_country.csv**: The combination of the wikipedia data (Article_Quality_Predictions_data.csv) and population data (population_by_country_AUG.2024.csv).
The CSV file includes the following columns: country, region, population, article_title, revision_id, article_quality.




### API Documentation

ORES requires a specific revision ID of an article to be able to make a label prediction. The revision ID of article pages are optained  using the [API:Info](https://www.mediawiki.org/wiki/API:Info) request to get a range of metadata on an article



### Research Implications
