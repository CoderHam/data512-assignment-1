# Data 512 (Human Centered Data Science) Assignment 1 - Data curation

## Goal of the Project

- The goal of this assignment is to construct, analyze, and publish a dataset of monthly traffic on English Wikipedia from January 1 2008 through September 30 2018. All of the analysis is performed in the [Jupyter notebook](https://github.com/CoderHam/data-512-a1/blob/master/hcds-a1-data-curation.ipynb) and the data is made available in `.json` (the naming conventio is `apiname_accesstype_firstmonth-lastmonth.json`) and `.csv` files. This ReadMe acts as the documentation.

- The purpose of the assignment is to demonstrate that I can follow the best practices for open scientific research in designing and implementing my project, and make my project fully reproducible by others: from data collection to data analysis.

- For this assignment, I have combined data about Wikipedia page traffic from two different Wikimedia REST API endpoints (Page views and Page counts) into a single dataset, performed some simple data processing steps on the data, and then analyzed the data by building a simple visualization.

## Terms of Use and License of Source Data

- Wikimedia contains their own license and terms of use as described below:

    - The Wikimedia REST API offers access to Wikimedia's content and metadata in machine-readable formats. Focused on high-volume use cases, it tightly integrates with Wikimedia's globally distributed caching infrastructure. As a result, API users benefit from reduced latencies and support for high request volumes.

    - The REST API along with its documentation is available for all major Wikimedia projects at the location /api/rest_v1/. For example, for the English Wikipedia it is available at [https://en.wikipedia.org/api/rest_v1/](https://en.wikipedia.org/api/rest_v1/).

    - While the functionality offered by most projects closely matches that on English Wikipedia, there are some noteworthy exceptions:

        - wikimedia.org offers cross-project information like page view metrics.
        - en.wiktionary.org offers an experimental definition end point, exposing Wiktionary information as structured data. Support for other languages is under discussion.

    More can be read at: [https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions)

## APIs Used for Data Collection

- Wikimedia Legacy Pagecounts API : [https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)
- Wikimedia Pageviews API : [https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews)

## Curated Data

The final data is stored in a `csv` file for easy access and the schema/description of the columns is shown below: 

| Column | Value | 
| ------ | ------ |
| year | YYYY | 
| month | MM | 
|pagecount_all_views| number of views for all clients reported by the (Legacy) Pagecounts API |
|pagecount_desktop_views | number of views for desktop clients reported by the (Legacy) Pagecounts API |
|pagecount_mobile_views	| number of views for mobile clients reported by the (Legacy) Pagecounts API |
|pageview_all_views| number of views for all clients reported by the Pageviews API |
|pageview_desktop_views| number of views for desktop clients reported by the Pageviews API |
|pageview_mobile_views| number of views for mobile clients reported by the Pageviews API |

The csv file is provided in this repository: [en-wikipedia_traffic_200712-201809.csv](https://github.com/CoderHam/data512-assignment-1/blob/master/en-wikipedia_traffic_200801-201709.csv)

## Final Results 

The data was visualized using `matplotlib` as shown below:

![Wikipedia Page Views Monthly between 2008 and 2018](https://github.com/CoderHam/data512-assignment-1/blob/master/wikipedia_pagevies_monthly.png)

The sudden dip or difference between values from pagecounts to pageviews can be attributed to the filteration of web crawlers or spiders. 

During the brief period of overlap between pageviews and pagecounts, it is possible that the pagecounts was not yet legacy even after the pageviews is introduced.
