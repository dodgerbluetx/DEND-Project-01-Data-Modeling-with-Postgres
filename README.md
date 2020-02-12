# Data Engineering Nanodegree
## Project 01 - Data Modeling with Postgres

## Introduction

This project is an introduction to Data Modeling with Postgres. A simulated
startup called Sparkify needs data on song and user activity, which is provided
by sample data sets from the Million Song Dataset and simulated JSON logs
created by an event simulator.

The goal is to parse all song data files and JSON logs and extract data that
feeds into a Postgres database via an ETL pipeline script.

## Project Description

The basis of the project is a star schema containing song and event data.
An ETL pipeline script is used to create the necessary database tables, parse
each log file using python, and load the data into the database.

## Requirements

To run locally, a Postgres database should be running on the localhost, with a
default database "studentdb" created, and a user "student" with a password
"student".  This will allow for the creation of the new sparkifydb database and
required tables.

Additionally, a conda environment file is included to recreate the environment.
Python 3.7.6 is part of the environment.

## Data

The included dataset contains log and song data. The log data is JSON formatted
song play data, which contains data on when the songs are played.  The song data
contains JSON formatted data about the individual sings themselves.

## Database Structure

![](images/sparkifydb_erd.png)

Database: sparkifydb

Facts Table
* songplays - records in log data associated with song plays i.e. records with
page `NextSong`

Dimension Tables:
* artists - artists in the music database
* songs - songs in music database
* time - timestamps of records in songplays broken down inno specific units
* users - users in the app

## Usage

To get started, first run the following script:

`create_tables.py`

The `create_tables.py` script will execute several queries located in the
`sql_queries.py` script to create the database and tables.

Then, run the following ETL pipeline script to parse the log files and load
sample data into the tables:

`etl.py`

Finally, to test that the data load was successful, run the `etl.ipynb` notebook
in Jupyter Notebooks to confirm the database is prpoerly setup and contains data.
