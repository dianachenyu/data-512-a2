# A2: Bias in data
## Project Goal

The goal of the project is find whether bias exist in Wikipedia articles. 


## Data Description

### Soure data
Data is collected from two different API endpoints, the Pagecounts API and the Pageviews API.

* [Pagecounts API](https://wikimedia.org/api/rest_v1/#!/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end) provides desktop and mobile traffic data from January 2008 through July 2016.

* [Pageviews API](https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end) provides desktop, mobile web, and mobile app traffic data from July 2015 through September 2017.

License
* Source data is licensed under the [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/) and [GFDL licenses](https://www.gnu.org/copyleft/fdl.html)

* [Wikimedia Foundation terms of use](https://wikimediafoundation.org/wiki/Terms_of_Use/en)

Relevant API documentation

* Pagecounts API ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts), [endpoint](https://wikimedia.org/api/rest_v1/#!/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end)) 

* Pageviews API ([documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews), [endpoint](https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)) 

## Result
In the [final data file](https://github.com/dianachenyu/data-512-a1/blob/master/en-wikipedia_traffic_200801-201709.csv), there are fields:
* year:	year of data in YYYY format, from 2008 to 2017
* month: year of data in MM format, from 01 to 12
* pagecount_all_views: total of desktop and mobile traffic data from Pagecounts API  
* pagecount_desktop_views: desktop traffic data from Pagecounts API  
* pagecount_mobile_views: mobile traffic data from Pagecounts API  
* pageview_all_views: total of desktop and mobile traffic data from Pageviews API
* pageview_desktop_views: desktop traffic data from Pageviews API
* pageview_mobile_views: mobile traffic data from Pageviews API, including both mobile-app and mobile-web traffic


## Issues
The Pageview API allows filter by agent=user; thus data from the Pageview API excludes spiders/crawlers. While data from the Pagecounts API does not provide this function; thus data from Pagecounts API includes both user and spider traffic.

There is about a 13 month period in which both APIs provide traffic data. 

All values of pagecount_mobile_views for months before October 2014 is 0. Mobile traffic data is not available before that month.

## References
[UW HCDS Class](https://wiki.communitydata.cc/HCDS_(Fall_2017))

[Assignment 1](https://wiki.communitydata.cc/HCDS_(Fall_2017)/Assignments)
