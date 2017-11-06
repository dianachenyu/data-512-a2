# A2: Bias in data
## Project Goal

The goal of the project is to find whether bias exists in Wikipedia articles of potical figures from countries around the world. We performed an analysis on article quality and politician coverage among various countries. 


## Data Description

### Source Data 
There are two data sources, Wikipedia dataset and population dataset.

* [Wikipedia dataset](https://figshare.com/articles/Untitled_Item/5513449) contains English Wikipedia articles under the category "Category:Politicians by nationality" and its subcategories. The dataset is found on [Figshare](https://figshare.com/).

  There are three variables in the Wikipedia dataset:

  	* page: article name
  	* country: country name
  	* rev_id: revision id

* [Population dataset](http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14) contains world population data in 2005. The dataset is found on [Population Research Bureau website](http://www.prb.org).

  There are five variables in the population dataset:
   * Location: country name
   * Location Type: the field only contains "Country" in this dataset
   * TimeFrame: the field only contains "Mid-2015" in this dataset
   * Data Type: the field only contains "Number" in this dataset
   * Data: population data

### License of Source Data
* Wikipedia dataset is licensed under the [CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

* [Wikimedia Foundation terms of use](https://wikimediafoundation.org/wiki/Terms_of_Use/en).

* The license of population dataset is unknown. There is no information found on [Population Research Bureau website](http://www.prb.org/DataFinder.aspx). Addional communication with Population Research Bureau may be necessarg before using and publishing the data.

### Relevant API documentation

* [ORES API](https://www.mediawiki.org/wiki/ORES) ("Objective Revision Evaluation Service") provides machine learning as a service to estimate arcitle quality. There are six quality categories, from best to worst: FA (featured article), GA (good article), B (B-class article), C (C-class article), Start (Start-class article), Stub (Stub-class article). In this project, we consider article in FA or GA categories as high-quality articles.


## Result (final CSV output)
In the result data file [wikipedia_ores_population.csv](https://github.com/dianachenyu/data-512-a2/blob/master/wikipedia_ores_population.csv), there are fields:

* country: country name
* article_name: name of Wikipedia article
* revision_id: revision id
* article_quality: article qualitys from ORES API. It is a categorical variable with 6 possible values: FA, GA, B, C, Start, Stub
* population: country population from population dataset


## Special Considerations and Known Issues
Both Wikipedia dataset and population dataset have fields containing country name. Values of the two fields do not overlap exactly. There are countries exist in one dataset but not the other. In this project, we only use countries found in both datasets and remove values of non-matching rows.

## References
[UW HCDS Class](https://wiki.communitydata.cc/HCDS_(Fall_2017))

[Assignment 2](https://wiki.communitydata.cc/HCDS_(Fall_2017)/Assignments)
