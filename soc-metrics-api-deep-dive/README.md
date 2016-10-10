
## About this folder/project

Austin's [open data portal](https://data.austintexas.gov) provides lots of public data about the City of Austin. It also provides portal administrators with behind-the-scenes information about how the portal is used... but that data is mysterious, hard to handle in a spreadsheet, and not located all in one place. 

Until now! Authorized city staff used admin credentials to grab some of this usage data and share it the public. The City of Austin wants to use this data to inform the development of its open data initiative and manage the open data portal more effectively.

This project contains related datasets for anyone to explore. These include site-level metrics, dataset-level metrics, and department information for context. A detailed detailed description of how the files were prepared (along with code) can be found on github [here](https://github.com/cityofaustin/data-portal-analytics/tree/master/soc-metrics-api-deep-dive).

## Example questions to answer about the data portal

1. What parts of the open data portal do people seem to value most?
2. What can we tell about who our users are?
3. How are our data publishers doing? 
4. How much data is published programmatically vs manually?
5. How data is super fresh? Super stale?
6. Whatever you think we should know...

## About the files

#### `all_views_20161003.csv`

There is a resource available to portal administrators called "Dataset of datasets". This is the export of that resource, and it was captured on Oct 3, 2016. It contains a summary of the assets available on the data portal. While this file contains over 1400 resources (such as views, charts, and binary files), only 363 are actual tabular datasets. 

#### `table_metrics_ytd.csv`

This file contains information about the 363 tabular datasets on the portal. Activity metrics for an individual dataset can be accessed by calling Socrata's views/metrics API and passing along the dataset's unique ID, a time frame, and admin credentials. The process of obtaining the 363 identifiers, calling the API, and staging the information can be reviewed in the python notebook [here](https://github.com/cityofaustin/data-portal-analytics/blob/master/soc-metrics-api-deep-dive/dataset-metrics.ipynb).

#### `site_metrics.csv`

This file is the export of site-level stats that Socrata generates using a given time frame and grouping preference. This file contains records about site usage each month from Nov 2011 through Sept 2016. By the way, it contains 285 columns... and we don't know what many of them mean. But we are determined to find out!! For a preliminary exploration of the columns and what portal-related business processes to which they might relate, check out the notes in this python notebook [here](https://github.com/cityofaustin/data-portal-analytics/blob/master/soc-metrics-api-deep-dive/site_metrics.ipynb)

#### `city_departments_in_current_budget.csv`

This file contains a list of all City of Austin departments according to how they're identified in the most recently approved budget documents. Could be helpful for getting to know more about who the publishers are.

#### `crosswalk_to_budget_dept.csv`

The City is in the process of standardizing how departments identify themselves on the data portal. In the meantime, here's a crosswalk from the department values observed in `all_views_20161003.csv` to the department names that appear in the City's budget

