## About The Project

Data modelling with Postgres for the first project submission on the Udacity 'Data Engineering' nano-degree.

The premise of the project is that a start-up called 'Sparkify' wants to analyse the data they've been collecting on songs and user activity on their new music streaming app.

The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis.

### Repo Contents

README.md : This file, explaining the purpose and usage of the Repo

create_tables.py : Creates the required tables within a local Postgres database

etl.ipynb : A notebook used to explore the stages of the ETL pipeline, for troubleshooting or development

etl.py : The pipeline itself; this loads the datafiles into the postgres database

sql_queries.py : A list of the SQL queries to be used to create tables and load data

test.ipynb : A notebook used to test the ETL pipeline

### Built With

* Python, inc. pandas, psycopg2

* Postgres
* Jupyter Hub

## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites

* psycopg2
* Postgres
* pandas

### Installation

1. To clone the repo:
   ```sh
   git clone https://github.com/sama26/Project1-Million_Songs.git
   ```

## Usage

1. Ensure the json files to be processed are present in a ./data folder

2. Ensure a local postgres server is running

3. Run 'create_tables.py' to create the postgres create_tables

4. Run etl.py to initiate the ETL pipeline

Note - To use this code you will need to have locally saved copies of the test song data provided by Udacity:

###### Song Dataset

The first dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID.

###### Log Dataset

The second dataset consists of log files in JSON format generated by this event simulator based on the songs in the dataset above. These simulate activity logs from a music streaming app based on specified configurations.

###### Sample query

An example query that can be used on this dataset would be  the following, which returns a list of all paid users who have used the service, and their location:

   ```sh
SELECT u.first_name, u.last_name, s.location FROM songplays s
JOIN users u
ON u.user_id = s.user_id
WHERE s.level = 'paid'
GROUP BY u.first_name, u.last_name, s.location
   ```

## Contributing

Feel free to contribute if you really want, but I have no plans to come back to this project:

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/FeatureName`)
3. Commit your Changes (`git commit -m 'Add some feature'`)
4. Push to the Branch (`git push origin feature/FeatureName`)
5. Open a Pull Request
