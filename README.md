# Real-time Log Analysis System

## 1. Developed a web crawler to get Android app metadata based on [Apache Nutch](https://github.com/apache/nutch)
- motivation: In order to find which category of Android apps is most popular, first I have to filter out records of Google play store from logs but we still need the category information of an Android app. In this case, I extended the Nutch to crawl the app metadata from the Google play store.
- ![crawler](/Users/wenji/Downloads/pics/crawler.jpg)
- process
    + [ingect] inject a seed file (a url) into nutchdb
        + [generate] generate urls from nucthdb
        + [fetch] crawl html pages from the google play store
        + [parse] extract metadata and outlinks
        + [update] update nutchdb with new outlinks
    + repeat the last 4 steps until no more urls
- folder: googleplaycrawler

## 2. Performed data processing using Spark/Pig with custom UDFs to handle multiple use cases
- dataset: a real-world access logs from browsers and mobile apps within one month, 6G per day, total 200G
- ![data_processing](/Users/wenji/Downloads/pics/data_processing.jpg)
- folder: data, resource, pig, spark

## 3. Built a data processing pipeline
- ![data_pipeline](/Users/wenji/Downloads/pics/data_pipeline.jpg)
- folder: workflow

## 4. Implemented real-time data ingestion and data analysis
- ![data_ingestion_data_analysis](/Users/wenji/Downloads/pics/data_ingestion_data_analysis.jpg)

- real-time data ingestion

    - ![data_ingestion](/Users/wenji/Downloads/pics/data_ingestion.jpg)

    1. write a python script to continuously write sample_log to access_log
    2. write a flink program to handle realtime data

- folder: prepare, flink
