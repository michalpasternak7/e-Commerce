# e-Commerce

## Project Overview

The project aims to create a relational database based on the contents of the provided dataset, [Sample-Superstore.csv](Sample-Superstore.csv). The primary objectives include:

- Designing an [Entity-Relationship Diagram](SuperstoreDB/superstore_erd.jpg) (ERD) to model the database schema.
- Implementing the relational [database](SuperstoreDB/superstore.db) using SQLite as the Relational Database Management System (RDBMS).
- Conducting [Exploratory Data Analysis](superstore_eda.ipynb) (EDA) to gain insights into the dataset.
- [Cluster](superstore_clustering.ipynb) customers according to their buying patterns.


## Folder Structure

- [README.md](README.md)
- [Sample-Superstore.csv](Sample-Superstore.csv)
- [superstore_db_creation.ipynb](superstore_db_creation.ipynb)
- [superstore_db_preparation.ipynb](superstore_db_preparation.ipynb)
- [superstore_eda.ipynb](superstore_eda.ipynb)
- [superstore_queries.ipynb](superstore_queries.ipynb)
- [superstore_clustering.ipynb](superstore_clustering.ipynb)

**SuperstoreDB:**
    - [superstore.db](SuperstoreDB/superstore.db)
    - [superstore_erd.jpg](SuperstoreDB/superstore_erd.jpg)

**SuperstoreTables:**
    - [Addresses.csv](SuperstoreTables/Addresses.csv)
    - [Orders.csv](SuperstoreTables/Orders.csv)
    - [Products.csv](SuperstoreTables/Products.csv)
    - [Customers.csv](SuperstoreTables/Customers.csv)
    - [OrdersDetails.csv](SuperstoreTables/OrdersDetails.csv)

**Exports:**
    - [rfm_clusters.csv](Exports/rfm_clusters.csv)

**Helpers:**
    - [states_titlecase.json](Helpers/states_titlecase.json)


## Entity-Relationship Diagram (ERD)

The ERD was created using [drawSQL](https://drawsql.app/) and is visualized in the attached image file: [superstore_erd.jpg](SuperstoreDB/superstore_erd.jpg).

## Data Transfer and Preparation

The process involves transferring data from the initial CSV file to the database and ensuring data integrity and consistency. This includes:

- Initial exploration of the Sample-Superstore.csv file to understand its structure and contents.
- Data conversion and formatting as necessary to align with database requirements.
- [Partitioning the dataset into separate tables](superstore_db_preparation.ipynb) based on relevant topics, ensuring each table has unique primary keys and eliminating unnecessary duplicated data.
- Saving the partitioned data as individual CSV files for convenience and later use.
- [Saving the data](superstore_db_creation.ipynb) in a [SQLite](https://www.sqlite.org/) [database](SuperstoreDB/superstore.db).
- Testing the database by [performing queries](superstore_db_queries.ipynb).

## EDA and Clustering

- [Explore](superstore_eda.ipynb) the e-commerce dataset focusing on orders, sales, profit, customers and typical e-commerce KPIs.
- [Cluster](superstore_clustering.ipynb) the customers by buying patterns using 3 parameters: Monetary (amount of money spent), Frequency (how frequently the customer bought something) and Recency (how many days has passed from today to their last purchase).


# Notebooks Overview

## superstore_db_preparation.ipynb

This notebook serves as the initial step in the data preparation process. Here's an overview of the tasks performed:

- Load the dataset (Sample-Superstore.csv) as a CSV file.
- Conduct an initial examination of the dataset to understand its structure and contents.
- Perform data conversion and transformation as necessary to prepare it for database insertion.
- Split the dataset into separate tables according to predefined topics, ensuring each table has a unique primary key and eliminating redundant data.
- Save the partitioned data as individual CSV files for future reference and use.

## superstore_db_creation.ipynb

This notebook focuses on the creation of the Superstore database (SuperstoreDB/superstore.db) and populating it with data extracted from the CSV files generated in the `superstore_db_preparation.ipynb` notebook. The key tasks performed in this notebook include:

- Creating the SQLite database `superstore.db` within the SuperstoreDB directory.
- Importing the structured data from the CSV files generated in the `superstore_db_preparation.ipynb` notebook.
- Ensuring data integrity and consistency during the database population process.

## superstore_db_queries.ipynb

This notebook contains a set of queries aimed at solving specific exercises based on Epic 4 from the [Code Academy Berlin LMS](https://lms.codeacademyberlin.com/content/data/Module-2/Project-5/Sprint-1). The queries are designed to extract insights and perform analysis on the Superstore database.

## superstore_eda.ipynb

This notebook focuses on the exploratory data analysis with focus on insights relevant for e-commerce. Some relevant e-commerce KPIs are included. The data is visualized using plotly express.

## superstore_clustering.ipynb

In this notebook the customers get clustered by buying patterns using 3 parameters: Monetary (amount of money spent), Frequency (how frequently the customer bought something) and Recency (how many days has passed from today to their last purchase). The results are further exported to [rfm_clusters.csv](Exports/rfm_clusters.csv).
