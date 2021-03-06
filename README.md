# RAWG Data Analysis using Spark
###### by Hemanth Ghosh


## Project Description

An analysis on **RAWG API**.

**RAWG** is the largest **Video Game Database** and game discovery service with **500,000+** games data.



## Technologies Used


* **Apache Spark [3.1.2]** 
Apache Spark is an open source unified analytics engine for large scale data
processing Spark provides an interface for programming entire clusters with implicit data parallelism
and fault tolerance

* **Python [3.8]** 
Python is an interpreted high level general purpose programming language
Python's design philosophy emphasizes code readability with its notable use of significant
indentation

* **PySpark [3.1.2]** 
PySpark is an interface for Apache Spark in Python It not only allows you to
write Spark applications using Python APIs, but also provides the PySpark shell for interactively
analyzing your data in a distributed environment

* **Spark SQL** 
Spark SQL is a Spark module for structured data processing It provides a programming
abstraction called Data Frames and can also act as a distributed SQL query engine It enables
unmodified Hadoop Hive queries to run up to 100 x faster on existing deployments and data

* **Git /GitHub** 
It is a provider of Internet hosting for software development and version control
using Git It offers the distributed version control and source code management functionality of Git

## Data Summary

### Content

Each row contains information about one game. There are several columns that have multiple values like platforms, genres, … In those cases, values are separated by double pipes ||.

#### Column definitions:

* id: An unique ID identifying this Game in RAWG Database
* slug: An unique slug identifying this Game in RAWG Database
* name: Name of the game
* metacritic: Rating of the game on Metacritic
* released: The date the game was released
* tba: To be announced state
* updated: The date the game was last updated
* website: Game Website
* rating: Rating rated by RAWG user
* rating_top: Maximum rating
* playtime: Hours needed to complete the game
* achievements_count: Number of achievements in game
* ratings_count: Number of RAWG users who rated the game
* suggestions_count: Number of RAWG users who suggested the game
* game_series_count: Number of games in the series
* reviews_count: Number of RAWG users who reviewed the game
* platforms: Platforms game was released on. Separated by ||
* developers: Game developers. Separated by ||
* genres: Game genres. Separated by ||
* publishers: Game publishers. Separated by ||
* esrb_rating: ESRB ratings
* added_status_yet: Number of RAWG users had the game as "Not played"
* added_status_owned: Number of RAWG users had the game as "Owned"
* added_status_beaten: Number of RAWG users had the game as "Completed"
* added_status_toplay: Number of RAWG users had the game as "To play"
* added_status_dropped: Number of RAWG users had the game as "Played but not beaten"
* added_status_playing: Number of RAWG users had the game as "Playing"

## Features (Problem Statements)

  1. Which is the top most rated games accross all platform.
  2. Which game developer has released the most number of games.
  3. Which game genres has most games.
  4. Number of games released per year 
  5. Games with longest updation time
  
## Getting Started
* Install pyspark, findspark.

      pip install pyspark
      pip install findspark
  
* Set the Required Spark path

      import findspark
      findspark.init()
      
* Import Libraries

      from pyspark.sql import SparkSession
      from pyspark.sql.functions import to_utc_timestamp, date_format, split, col, round, explode
      
*  Create SparkSession and SparkContext
      
            spark = SparkSession.builder.appName("app").getOrCreate()
            sc = spark.sparkContext

*  Load data into Spark DF
  
            pathToRead = r"C:\Users\heman\downloads\game_info.csv"
            raw_df = spark.read.csv(pathToRead,header=True,inferSchema=True)
      
* Create Temporary Views

      game_df.createOrReplaceTempView("filtered_games")
      
* Writing Spark SQL Queries
      
      spark.sql("""
      select name, rating, platform from (      
      select row_number() over(partition by platform order by platform) as num,      
      name, platform, max(rating) over (partition by platform) as rating      
      from filtered_games      
      where platform != '0'      
      order by rating desc) as table
      where num = 1
      """).show(truncate=False)
      
## Usage

This project can be used to analyze any API which provides an API key and have batch processing data.

## Contributors
* [Devansh Sharma](https://github.com/devanshsharma-bigdata/P2-RAWG-Data-Analysis)
* [Divya Reddy](https://github.com/Divyaredd/BIG_DATA_PROJECT2)
* [Rajkumar](https://github.com/rajoffl/Analysis-on-RAWG-Dataset)
* [Sailash R](https://github.com/Sailash/Project_2)

## Dataset Used
* [RAWG Dataset Document](https://api.rawg.io/docs/)
* [RAWG Dataset](https://www.kaggle.com/jummyegg/rawg-game-dataset)

## License
This project uses the following license:
[MIT License](https://github.com/git/git-scm.com/blob/main/MIT-LICENSE.txt)
