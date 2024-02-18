# Youtube Analysis

## Introduction
In this project, we leverage Amazon Web Services (AWS) to build a YouTube trending video analytics service. The goal is to extract insights from daily statistics of trending YouTube videos across major nations such as the USA, Great Britain, Germany, Canada, Japan, India, and France. The project encompasses various aspects of data engineering, analysis, and reporting, all implemented on the AWS Cloud platform.

## Problem Definition
The objective of this project is to create a comprehensive analytics solution for YouTube trending videos. This involves:

Data Ingestion: Establishing a pipeline to extract new data into the AWS data lake.

Data Lake: Setting up a centralized repository to store data from diverse sources and formats.

Data ETL (Extract, Transform, Load) Jobs: Developing jobs to preprocess raw data into usable formats.

Data Analysis: Utilizing SQL queries to derive key insights from the data.

Data Reporting/Analytics: Generating dashboards to communicate insights effectively to stakeholders.

## Data Overview
Dataset: https://www.kaggle.com/datasets/datasnaek/youtube-new
The dataset comprises daily statistics for trending YouTube videos, with each region's data stored in separate CSV files. The data includes various attributes such as video title, channel title, publish time, tags, views, likes, dislikes, description, and comment count. Additionally, each video is associated with a category, stored in separate JSON files specific to each region.

## ETL Pipeline and Data Warehouse
Data Ingestion: Data is ingested into Amazon S3 buckets from Kaggle, with files stored as objects in buckets for each region in both CSV and JSON formats.

Central Repository of Metadata: AWS Glue crawler iteratively traverses data sources, inferring schema, structure, and formats. Metadata is stored in the AWS Glue Catalog, providing a logical structure for managing metadata and essential column information.

AWS Lambda Data Processing: A Lambda function processes incoming data, converting JSON to Parquet format for efficiency and consistency. Updated data catalog with schemas and column datatypes is created in the AWS Glue Catalog.

ETL Jobs: ETL jobs automate data processing and delivery, extracting data from S3 buckets, performing join transformations, and loading cleaned data for further analysis. Joining datasets based on category ID facilitates the creation of a final cleaned dataset ready for analysis.
  
## Conclusion
This project demonstrates the implementation of a comprehensive YouTube trending video analytics solution on AWS. By leveraging various AWS services such as S3, IAM, Glue, Lambda, Athena, and QuickSight, we establish an end-to-end pipeline for data ingestion, storage, preprocessing, analysis, and reporting. The solution enables stakeholders to derive valuable insights from YouTube trending video data, facilitating informed decision-making and strategic planning. Additionally, the use of efficient data formats and automation streamlines data processing and enhances scalability and efficiency.
