# data-512-a1
512hw1

The goal of this assignment is to construct, analyze, and publish a dataset of monthly traffic on English Wikipedia from January 1 2008 through August 30 2021.
The steps and code are in a single jupyter notebook. (hcds-a1-data-curation.ipynb)

This assignment has the following 3 steps.

Step1 : Gather data from the Legacy PageCounts API (https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts) and the PageViews API (https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews). The resulted 5 JSON files are collected from the 2 APIs.
1.pagecounts_desktop-site_200712-202108.json
  (Desktop traffic data from Legacy PageCounts API from 2008-2021)
2.pagecounts_mobile-site_200712-202108.json
  (Mobile traffic data from Legacy PageCounts API from 2008-2021)
3.pageviews_desktop_200712-202108.json
  (Desktop traffic data from PageViews API from 2008-2021)
4.pageviews_mobile_app_200712-202108.json
  (Mobile App traffic data from PageViews API from 2008-2021)
5.pageviews_mobile_web_200712-202108.json
  (Mobile Web traffic data from PageViews API from 2008-2021)

Step2 : Clean and merge the API data (the detailed steps are described in the jupyter notebook) into a single csv file (en-wikipedia_traffic_200712-202108.csv).
In this CSV file containing all traffic data from English Wkikpedia, the columns are year (YYYY), mont (MM), pagecount_all_views, pagecount_desktop_views, pagecount_mobile_views, pageview_all_views, pageview_desktop_views, and pageview_mobile_views.

Step3 : There are two plots in this repo. The 'traffic data plot.png' is my original plot. After seeing the slack message just before the DDL, I created the 'traffic data plot(modified).png' to match the newest instructions (6 lines).

(Original Thought Process)
Plot mobile traffic, desktop traffic and all traffic data for the English Wikipedia from 2008 to 2021.
The plotting data comes from both the Legacy pagecounts API and pageviews API. The PageCounts API includes data from 2008/01 to 2016/08 (there is no mobile traffic data before 2014/10) while the PageViews API includes data from 2015/07 to 2021/08.

I used the PageCounts API data for plotting the traffic from 2008/01 to 2015/06 and the PageViews API data for plotting the traffic from 2015/07 to 2021/08. Note that there is overlapping data from both API from 2015/07 to 2016/08. For this assignment, I chose to use the PageViews API data for this period of time. My reasoning is that the data from Legacy API is probably not as up-to-date as the data from PageViews API. In addition, the PageViews API have the function of filtering views by user access. Since we're only interested in user views (not spiders/crawlers), we should use the PageViews API data.

I used Seaborn Lineplot funciton to produce the plot.
